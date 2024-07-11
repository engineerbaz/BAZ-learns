# AZ104 Exam Prep


## AZ104 Cheat Sheet
AAD (Azure AD) is cloud based verison of AD. IDaaS (Identity As A Service).
AD comes in 4 edition
1. FREE - MFA, SSO, Basic Security and Usage Report, User Management
2. OFFICE 365 Apps - Company Branding, SLA, Two-Sync between On-Prem and cloud
3. PREMIUM 1 (P1) - Hybrid Architecture, Advanced Group Access, Conditional Access
4. PREMIUM 2 (P2) - Identity Protection, Identity Governance

Azure AD can authorize & authenticate to multiple sources
- On-Prem AD via **Azure AD Connect**
- Web Application via **App Registrations**
- Allow users to login with their IpD i.e Facebook, Google via **External Identities**
- To OFFICE 365 or **Azure Microsoft**

## Active Directory Terminology
- Domain 
  - An area of network organized by a single authentication database
- An Active Directory Domain
  - A logical grouping of AD object on a network
- Domain Controller (DC)
  - A server that authenticates user Identities and authorizes their access to resources
- Domain Computer
  - A computer that registered with a central authentication database (would be an AD object)
- AD object
  - Basic element of Active Directory such as User, Groups, Printer, Computers, Shared Folders.
- Group Policy object (GPO) 
  - A virtual collection of Policy settings, It controls what AD object have access to.
- Organization Units (OU)
  - A subdivision within an AD into which you can place user, groups, computer and other Organizationak Units.
- Directory Service
  - Such as Active Directory Service (ADS), provides the methods of storing Directory data and making this data available to network user and administrator. A Directory Service runs on Domain Controller


A **Tenant** represents an Organization in Azure Active Directory. It is dedicated Azure AD Service Instance. It automatically created when you sign up for either
- Microsoft Azure 
- Microsoft Intune
- Microsoft 365

Each Azure AD tenant is disticnt and seprate from other Azure AD tenants
When performing lift and shift of AD to Azure, not all AD features are supported and in that case you need to use AD DS 

**Azure Active Directory Domain Service (AD DS)** provides managed domain Service features as 
- Domain Joins
- Group Policies
- Lightweight Directory access protocol (LDAP)
- Kerberos
- NTLM authentication

Azure AD Connect has following features
- Password Hash Synchronization
  - Sign-in method, Synchronizes a hash of a user on-Premises AD Password with Azure AD
- Pass-through authentication
  - sign-in method, allows users to use the same Password on-Prem and in the cloud
- Federation Integration
  - Hybrid enviornment using an on-Prem AD FS Infrastructure, for certificate renewal
- Synchronization
  - Responsible for creating users, groups, and other objects, ensure on-Prem and cloud data matches
- Health Monitoring
  - Robust Monitoring and provide a central location in the Azure Portal to view this activity

**Users** represents an Identity for an employee or person in your domain, A user has a login credentials and can use them to log into the Azure Portal. 
Azure AD has two kids of Users
1. Users - belongs to your Organization
2. Guest User - belongs to other Organization

**Groups** Let the resource owner (or AzureAD Directory owner), assign a set of access permissions to all the members of the group, instead of having to provide the right one-by-one. Group contains
1. Owner - Has permission to add an removed member
2. Members - Have permission to do things


Request to Join Groups - The group owner can let users find their own groups to join, instead of assigning them. The Owner can also set up the group automatically accept all user that join or to require approval, Four way to assign resource access rights to your users
1. Direct Assignment - resource owner directly assigns the user to the resource
2. Group Assignment - resource owner assigns an Azure AD group to the resource, which automatically gives all th egroup members access to the resource
3. Rule Based Assignment - the RO creates a group and uses a rule to define which users are assigned to a specific resource 
4. External Authority Assignment - Access comes from an External source, such as an on-prem directory or a SaaS App.

---------------

- Active Directory provides the core service of identity management.
- AD DS is the traditional on-premises solution, whereas Microsoft Entra ID is the cloud-based solution. 
- Microsoft Entra ID is frequently adopted at first to facilitate authentication for cloud-based apps, but is capable of providing authentication services for the entire infrastructure. While they provide similar solutions, each offer different capability and are often used together to provide a best-of-breed solution. 
- Microsoft Entra ID is offered as a free service, with paid tiers for additional capabilities, depending on an organization's needs.

Entra ID has three types of User Accounts
1. Cloud Identity (includes administrator account and users who managed as a part of your organization, Ifit is deleted  from primary directory, user account will be removed too)
2. Directory Synchronized Identity (Its defined in on-prem Active Directory, Synchronization occurs vi Microsoft Entra Connnect to bring user to Azure, The source is Windows Server AD)
3. Guest User (Outside Azure, UA from other cloud providers and Microsoft accounts like xbox, Its Invited user)

----

The main takeaways for this module are:

1. Microsoft Entra ID supports three types of user accounts: cloud identities, directory-synchronized identities, and guest user identities.

2. Cloud identities have profile information such as job title and office location. This information can be customized for your organization's needs.

3. You can bulk create user and group accounts. The process uses a template file managed through the portal.


There are two types of group accounts: Security and Microsoft 365.

- Administrative units help you control administrator access to resources.