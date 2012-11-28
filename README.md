
Conceptual view of Identity Management Systems implementation

Introduction
Identity is a personality. Identity is all about a real person: name, gender, position, date of birth. Processes and systems of a personal data management are called Identity Management (IDM). 
Personal information is used by many applications such as billing systems, network access systems, mail/file servers, accounting systems and so on. All these applications may store personal information independently. Moreover these information can be inconsistent since it is doubled and source can not guarantee correctness for it. So the main task for IDM is creation of integral catalog with personal information that is going to be used for the future in management processes.
User accounts and its attributes (e.g. access permissions) are part of the personal information as well as postal codes, emails, names. It is stored in the same base and in the same way. So it would be logical to include the functions of access management into Identity Management (IDM) process. Often when we say IDM we mean Identity and Access Management (IAM).
The results of successful IDM implementation can be divided into "static" and "dynamic". Static results answer the question - "what have been achieved?". And dynamic ones answer the question - "how is it working?".
It is typical of static results:
all accounts are personalized. it applies not only for system accounts but also for auxiliary processes.
all attributes of account are compatible and atomic. (i.e. values must be the same)
it is defined which permissions are allowed for each account.
Dynamical results of the successful IDM implementation:
stable working account management process
very flexible accounts updating, their attributes and dependences.
homogeneity of accounts, some patterns exists for just created accounts.
in case of account removing all permissions must be blocked.
sufficiency of permissions for each account must be enough - not more, not less.
The most time consumption question for the process of implementation IDM is the permission setting. Basically user permissions depends on user duties. The wider duties the more permissions and more difficult their assignment.
Structure of Identity Management.
The content of the Identity Management systems could be described as a standardized relations between various information systems of organization and persons.
The matter is not only about employees of the organization but about all existing and potential users: partners, clients, consultants, auditors and even temporary employee.
Identity management can be divided into several subgroups:
authentication system implementation
authorization system deployment
personalization system development
internal audit access system creation
implementation of user data management system with privilege delegation
data unification in personal information management
The list above is based on the reviews made by Net2S consulting group. In fact there is no common view and common definition of this list. Some software companies solve only part of the questions above when they release IDM application.
We should say that mentioned questions do not solve tasks of automation but solve tasks of integration into existing (or developing) automation systems.
Single Sign-on Registration
Corporate Information systems handle huge amount of users moreover relations between user and system is unequal. So user authentication is the first step in the connection establishment with the system.
Usually Single Sign-On(SSO) system means by authentication system. The aim of the SSO systems is avoid the necessity of re-entering passwords. It also reduces phishing success, reduces password fatigue.
With this property a user logs in once and gains access to all systems without being prompted to log in again at each of them. Any physical authentication mechanisms can be used here instead of passwords. For example, smart cards, finger prints, encryption calculator.
As we mentioned above SSO implementation allows to reduce time spent re-entering passwords for the same identity. Then you don't need keep many passwords in mind and spend time to change it regularly. But that are not all benefits.
Successfully deployed SSO increase security level. Usual user prefers set the same password everywhere, in all applications. So if an intruder cracks the weakest system he gets an access to all systems. SSO systems have good secure background and some physical authentication properties only increase it.
Then single sign-on authentication is not only easy and feasible way to log-in but also allows reducing IT costs due to lower number of IT help-desk calls about passwords.
There are many single sign-on configurations but three of them are commonly used:
First is one-time password token. Two-factor authentication with OTP tokens follows industry best practices for authenticating users. This OTP token method is more secure and effective at prohibiting unauthorized access than the other authentication methods. 
Kerberos based approach is a modification of One-time password token approach. Initial sign-on prompts the user for credentials, and gets a Kerberos ticket-granting ticket (TGT). It takes additional server (and client application) configuration for token using authentication.
The second one is initial sign-on prompts the user for the smart card. Additional software applications also use the smart card, without prompting the user to re-enter credentials. Smart card-based single sign-on can either use certificates or passwords stored on the smart card.
The third one is an XML-based solution for exchanging user security information between an enterprise and a service provider. It supports W3C XML encryption and service provider initiated web single sign-on exchanges. 
Actually it is not necessary strict one time registration. When user are asked only once to prove his permissions. Real authentication process must be controllable. For example, the idea could be reasonable to ask users for re-entering password when they are performing important operations or just from time to time.
Directory Services
SSO solves user side problems usually. But administrators are still in need of access to manipulate user accounts. General directory service of company does that.
Directory services is a big data storage contained all user information (and necessary data for authentication process also). All modern software implementations of Directory services support application protocol LDAP. LDAP is used in asynchronous way - reading operation is more frequently used than an updating operation.
LDAP becomes a standard of user data storing. Nowadays many applications use LDAP for user authentication. 
It mostly because of popularity of MS Windows operating systems. Microsoft Active Directory and Novell eDirectory are used for logging in user authentication and other software application. 
Centralized Directory Service allows user to work on any computers where they have an access. It doesn't take any additional configuration for these computers.
Many enterprise solution from other software developing companies support LDAP standard also. It is valid for Web services: all web servers, application servers support authentication through LDAP protocol.
Centralized Directory Service allows some (ideally, all) enterprise applications to use the same account in directory for authentication process. Because of that there is no need to maintain user data in many systems separately.
Unfortunately not all the applications supports external LDAP server. Moreover in the same company could be used many different LDAP servers. In these cases Meta-directory systems help.
A meta-directory system provides for the flow of data between one or more directory services and databases, in order to maintain synchronization of that data. The data being synchronized typically are collections of entries that contain user profiles and possibly authentication or policy information. The most meta-directory deployments synchronize data into at least one LDAP-based directory server, to ensure that LDAP-based applications such as single sign-on and portal servers have access to recent data, even if the data is mastered in a non-LDAP data source.
Meta-directory system merges existing user data storage and allows to control it directly in one operation.
Unfortunately it's not possible synchronize passwords in directory systems because they are encrypted with one-way function.
In addition to mentioned software application Directory servers some more are used: Sun ONE Directory Server, IBM SecureWay и OpenLDAP. The most successful players on the media-directory software market are Novell DirXML, MaXware DSE и Critical Path Meta-Directory. 
User provisioning is an alternative to media-directory systems. User provisioning refers to the creation, maintenance and deactivation of user objects and user attributes, as they exist in one or more systems, directories or applications, in response to automated or interactive business processes. User provisioning software may include one or more of the following processes: change propagation, self-service workflow, consolidated user administration, delegated user administration, and federated change control.
Federated Authorization Systems
After authentication phase user can start his work with information contained in the system. Obviously an access to information must be limited for some security reasons and unforced errors.
Access permissions to information resources are stored with other user attributes and user profiles together.
This method is becoming inconvenient when amount of data is growing.
Administration of access permissions could be simplify by sorting user into groups by roles. Terms of groups and roles are quite similar but have some very important differences. Group is a list of specified users, but role is a dynamically assigned property by current duties of user.
It allows preventing duplication users in the system. In order to delegate authority to user we need just add a role for him or put him into a group. Groups and roles can be structured hierarchically. Sub-groups and sub-roles can be created and privilege inherited.
Information resources must be organized hierarchically by analogy (compare with folder in file system). It allows assign privileges for the whole class of resources. 
Installed permissions can be graphically represented as a matrix with rows for groups, roles, standalone users and columns for information resources. A cell in the matrix contains an information for privileges.
The simplest case is a binary matrix - "1" if access granted and "0" if access forbidden. But usually it's a bit more complicated.
First, semantics for designating how access privileges are applied to a resource have a bit more complicated structure. For instance, user could have an access to file for reading only. Or user can be able operate limited deposit account in financial application.
Second, the answer to authorization question depends on:
authentication method. (by smart card, by password, by temporary token)
time of day and day of the week.
other conditions that depend on external information.
We should mention also priority of privileges. Priorities must be defined a priori in order to understand behavior of the system if user belongs to two different groups with different access level to information.
Coordination of all authorization methods is very complicated task. Here is just main aspects of it:
standalone systems must have some remote management controls. It could be implemented by plug-in or application programming interface.
master system (with authorization management function) must support and understand semantics for access privileges of slave systems.
In practice developing such an authorization system can use Kerberos protocol or software application like Baltimore SelectAccess, Sun ONE Identity Server or Evidian AccessMaster.
Federated Personalization System.
Implementation of User interface personalization is a task very similar to federated authorization system creation. Indeed, grant user access to some resources is important task but this access must be convenient for the user. On the other hand access to the forbidden resources must be prohibited and user can not be able to see it (what is not allowed must be hidden, no message like "you do not have an access to this function").
It could be good idea allow user to choose preferred view, he can choose suitable and usual interface.
Usually client applications are developed in order to solve the task of personal system implementation. Client applications are adapted for certain conditions: some access levels, users computers, software applications. Obviously that is not the easiest way and provide personalization of a workstation not a user interface.
Modern requirements dictate mobile functionality for user interface. User must have the same view, privileges and functions in any point of corporate network and even outside of the network. So user can do his work independently of his location.
Web browser could be a good solution to achieve mobility functionality. In this case some kind of enterprise web system must be deployed.
Alternative to web-browser solution is an application for workstation management like Microsoft Systems Management Server or Novell ZENWorks. These applications control workstations and configure them depends on who is sitting there.
Audit systems
All user activities must be logged into journals (logs) to make information system more secure. Later it can be used for investigations process or improving functionality.
All enterprise systems allow create and read logs. The task of the audit systems implementation is merging all such logs in way to later feasible analyzing. It must be easy to find all information about user activities, requests to a resource, states of resource at any time.
In practice these systems are implemented as a part of federated authorization system.
User data unification
Enterprise systems contain some useful user data in addition to the data for authentication phase and information about membership of a group or role. That is name, surname, email, mobile number, position etc.
If such data is administered separately it can lead to information inconsistency, mismatching, integrity loosing and even data loss. Here task of unification is appeared. Unification of descriptive user data within information system is needed.
Implementation of this unification is very similar to mention above directory service technique.
User data storages consolidate (one account for each user with valid values of all descriptive attributes) or synchronize by meta-directory service. In case of using meta-directory service different attributes can have different data sources, i.e. email can be taken from mail server and position can be taken from accountant system.
Delegating User Data Management System
The system that allows to manage users data and their privileges let unify all operations with user account. But it doesn't mean that only one administrator have managed to perform all these functions.
If a company has distributed structure with many offices in different locations then local administrators perform of user data administration. And if federated directory service are implemented then such functionality will be easy to achieve due to replication mechanism and privileges delegation mechanism. In this case we can say about delegated administration method: administrator delegates some management functions to other persons.
Delegated administration is a more secure method for providing delegated user management access as it allows to assign limited administrative privileges to the selected non-administrator users in organization.
Delegated administrators can perform some administrative tasks: creating and editing users and resetting passwords for users in specified roles and all subordinate roles; assigning users to specified profiles; logging in as a user who has granted login access to their administrator.
Application of Identity Management
Mentioned list of the branches represents highest point in IDM development process. In which order and which tasks should be solved is the main question for developers. 
First of all necessity level of all aspects must be estimated for a specific company under specific conditions. Decision making process is based on strategic plans also. As we can see almost all services refer to infrastructure and their implementation and updating can lead to high-level applications reconfiguring.
Problem of privileges ordering to unstructured information (files, email) is very actual problem for companies. Some kind of Electronic data interexchange systems (EDI) exists to perform such functionality. But hierarchy of groups and roles must be specified in advance in order to implement such system.
Having such hierarchy is very useful even if implementation of authorization system is postponed for a while.
Need in uniform user data management systems is appeared at a moment when administrators have not managed to process all information about users. If bigger company then bigger IT infrastructure and more employers are there. They perform huge volume of work and do many operations. To control all these transactions and data transfers administrators need an effective automatic system. Universities are one of the most interested organizations. They have huge data-flow at the beginning of the school year when new students enter the university.
Also security requirements exert influence on decision making process. Implementation of authentication and authorization systems with audit functionality leads to flexibility in privilege management process. Delegated administration systems get rid of system administrators monopoly for user permissions management and distribute it within responsible managers (particularly, information security engineers)
Identity Management is a long term project that yields benefits in the future. It must be well thought-out before its implementation.

References
2012 
Wikipedia. Identity Access Management. From http://goo.gl/vjRxF.
Wikipedia. Single sign-on. From http://goo.gl/ZecAk.
Identity Management Group at LinkedIN. From http://goo.gl/S0cIr.
Wikipedia. Lightweight Directory Access Protocol. From http://goo.gl/el8Ke.
Wikipedia. Metadirectory. From http://goo.gl/fNRbH.
Wikipedia. Electronic data interchange. From http://goo.gl/tiLh0.
2010
Janis Wong. Identity and Access Management Continually Rank High in Lists. AICPA. Retrieved from http://goo.gl/Ak4jW.
2009
David Griffeth. Identity and access management 2009: Staff cuts, insider threats. Search Security. From http://goo.gl/S1UvF.
2008
Andras Cser and Jonathan Penn. Identity Management Market Forecast: 2007 to 2014. Forrester. From http://goo.gl/n1jdg. 
2007
Nelson Cicchitto. Evaluating Your Identity and Access Management Options. Avatier Corporation. From http://goo.gl/ElLoa.
IBM. Identity and access management: uncovering the secrets to successful implementations. IBM Corporation. From http://goo.gl/ZMBZC.
John K. Waters. ID Management Definition and Solutions. From http://goo.gl/OBHT1.
2005
Sari Kalin. How to Tackle Identity and Access Management. CIO. From http://goo.gl/CYY20.
Linares, M. Identity and Access Management Solution. SANS Institute. From http://goo.gl/DjR3F.
Roberta J. Witty,  Ant Allan,  John Enck,  Clare Hirst,  Barry Runyon,  Ray Wagner,  Earl L. Perkins,  
John Pescatore,  Vic Wheatman. Hype Cycle for Identity and Access Management Technologies. Gartner. From http://goo.gl/NLeZL.
2004
Frederick Chong. Identity and Access Management. Microsoft Corporation. From http://goo.gl/ELaLt.
2003
Vasily Shabat. Strategicheskiy vzglyad na Identity Management. [RUS] From http://goo.gl/S8oVe
