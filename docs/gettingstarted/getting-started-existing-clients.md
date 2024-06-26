# Overview
This document is an introduction and quick access, how-to guide when learning to use the Fiserv Developer Studio©: Card Developer©. Companies can use the Fiserv Card Developer API solutions for company-branded digital applications to embed services and capabilities for their customers. You can create, update, and control the financial services provided by Fiserv APIs for your clients under your company branding.

## Developer Studio Highlights
Card Developer includes the following features:
*	Create Account—Used to create an account, in the Card Developer Workspace. Located in the top menu area prior to signing into Studio Developer.
*	API explorer—An interactive research tools for technical information, key management, and credentials. Located in the lower half of the left-side panel.
*	Create Workspace—Clients create Card Developer Workspace(s). The Card Developer Workspace contains the API keys/Credentials of the Client's company. You can create more workspace types for other purposes.
*	Add API Keys—Clients add API keys to the workspace. The API key and Secret are used to obtain an access token. You must register with Fiserv as a client before you can create API keys for Production environment. Then you must get the API keys approved for Fiserv Production environment. See also, New clients.
  
*Note: We used to refer to the previous API Card Developer portal simply as “app”.*

The following graphics show you a visual representation the highlights outlined above. 

![](assets/images/getStarted/CardDev-top.png)

![](assets/images/getStarted/Add-an-API-key-button.png)

In the Card Developer Workspace, Clients can establish two roles with differing capabilities. The two 
roles are as follows:
**Company Administrator**—The Card Developer Workspace creator is the default Company 
Administrator. The Company Administrator is the designated organization representative with all 
administrative privileges:

* Manage the Card Developer Workspace.
* Invite Company Developers.
* Designate secondary Company Administrators. 
* Delete a Card Developer Workspace.

**Company Developer**—This role type is a subset of the Company Administrators account type with the 
following privileges:

* Can view and use Sandbox API Keys created by Company Administrator
* Get access to the Company Production API Keys created by the Company Administrator.
* Can test API Keys in the Sandbox environment.
* View/read privileges to the Company API products and features.

### Limitations
* The Card Developer Workspace is not a server endpoint and API keys cannot be staged or tested 
directly on the Card Developer Workspace. 
* Developers must use an independent method, such as Curl or Postman, pointed at the Sandbox 
endpoints to test API keys.

### Sandbox environment
The sandbox environment is a safe testing ground that isolates code for developers. Clients can mimic 
the production environment and create simulated responses. The simulated responses are based on test 
cases and data. The sandbox environment is identical to production but points to a simulated API 
environment for API responses.

# Workspace and API keys
This section describes how to set up and use a Card Developer Workspace. 

## Existing clients
If you have existing API keys and Company Developers, you can migrate your API Keys (apps) to the Card 
Developer Workspace.

##Migrate existing API keys and Company Developers
When the Company Administrator creates a Card Developer Workspace, the Company Administrator 
must use the same email address used previously to create a new account on Developer Studio. 

### Create new account and a workspace
1. In the upper-right corner, select **Create account**.
   
![](assets/images/getStarted/Create-account.png)

*Note: use the same email address used in Developer Portal as administrator.*

2. Follow the pop-up directions to sign into your account as an existing Fiserv client.
3. Select **Migrate API keys** and click **next**.
   
 ![](assets/images/getStarted/Migrate-API-keys.png)
   
5. Select **Create** to confirm.

 ![](assets/images/getStarted/Display-workspc-w-migrtd-API-keys.png)   

A pop-up appears to display your migrated API keys; they now populate your workspace.

### View and manage your API keys
1. From the menu bar, select **Credentials** to see add new or manage your existing API keys.
2. Select **Add API key**.
   
  ![](assets/images/getStarted/Credential-Add-API-key.png)

# Appendix
## Card Developer terms

The Fiserv Card Developer API environment defines the following terms as: 

* Trusted endpoints—Fiserv API suites supports communication between two trusted endpoints.
* Server—One or more endpoint Servers residing at Fiserv datacenters. These servers integrate 
with the financial back end. 
* Client—An application built by any registered company, such as Digital Providers, Account 
Processors, Application Service Providers (ASP) or a Financial Institution. 
* Two-way communication—Mutually authenticated HTTPS traffic for transport security. Clients 
must obtain time-limited tokens to make requests. 
* Card Developer Workspace—Fiserv’s previous API Card Developer portal concept terminology 
was referred to as “Company”.

## Workspace highlights

The following images highlight Company Administrator common requests and actions.
Review and create the Card Developer Workspace
Once you set up and are working in a Workspace mode, Workspace page contains the following tabs:

* Summary
* Credentials
* Members
* Settings
