
## Azure Resource Manager

Azure Resource Manager is the deployment and management service for Azure.

ARM can be used via 
- Azure Portal
- Azure CLI 
- PowerShell
- SDK
- Rest API 

There are few IaC 
- Terraform
- ARM template
- Bicep

ARM laverage RBAC for resource, RG and  subscription

- Resource can only exist in one Resource Group (RG)
- RG cant be renamed
- RG can have resources of many different types
- RG can have resources from different regions 

Only the Owner and User Access Administrator roles can create or delete management locks.

- Removing Resource Group 
`Remove-AzResourceGroup -Name "ContosoRG01"`


Management Group --> Subscription --> Resoource Group --> Resources


## Cloud Shell 
Azure Cloud Shell is a browser-accessible command-line experience for managing Azure resources

- Cloud Shell sessions terminate after 20 minutes of inactivity. When a session terminates, files on your CloudDrive are persisted, but you need to start a new session to access the Cloud Shell environment.

Azure Cloud Shell can be used to:

- Open a secure command-line session from any browser-based device.
- Interact with Azure resources without the need to install plug-ins or add-ons to your device.
- Persist files between sessions for later use.
- Use either Bash or PowerShell, whichever you prefer, to manage Azure resources.
- Edit files (such as scripts) via the Cloud Shell editor.
  

## Bash
BASH is Bourne Again Shell

#### note:
One reason for Bash's success is its simplicity. Bash, like the rest of Linux, is based on the Unix design philosophy. As Peter Salus summarized in his book A Quarter Century of Unix, three of the "big ideas" embodied in Unix are:

- Programs do one thing and do it well
- Programs work together
- Programs use text streams as the universal interface

#### Wild Cards

The * wildcard matches on zero or more characters, but the ? wildcard represents a single character. If the current directory contains files named 0001.jpg, 0002.jpg, and so on through 0009.jpg, the following command lists them all:

`ls 000?.jpg`

Yet another way to use wildcards to filter output is to use square brackets, which denote groups of characters. The following command lists all the files in the current directory whose names contain a period immediately followed a lowercase J or P. It lists all the .jpg, .jpeg, and .png files, but not .gif files:

`ls *.[jp]*

`Expressions in square brackets can represent ranges of characters. For example, the following command lists all the files in the current directory whose names begin with a lowercase letter:

`ls [a-z]*`


--
clouddrive is a subdirectory of your current directory. It's a mounted file share that persists if you're using Cloud Shell on your own account. 
--


Some are behind-the-scenes files to make Cloud Shell work.

`.` refers to your current directory, and `..` refers to your parent directory. Wherever you are, if you print all hidden files and directories, you'll see `.` and `..` printed.
`.bash_history` is a special Bash file where all commands that you enter into the shell are stored. Bash remembers your command history, which, as we'll see later, is useful.
`.bash_logout` is another special Bash file that is read and run every time a login shell exists. Linux superusers can modify it to customize your environment.
`.bashrc` is an important Bash configuration file that runs whenever you start a new shell. If you decide to open this file to look at it, be careful about making changes, because they can have unintended consequences.


---
`cat` (short for "catenate")
---

`az vm list-sizes --location westus --output table` up-to-date list of the VM sizes available in the westus region of Azure



## PowerShell
PowerShell is a command-line shell and a scripting language all in one.


- Interacting with a console is often faster than using a graphical interface.
- In a console, you can run batches of commands, so it's ideal for task automation for continuous-integration pipelines.
- You can use a console to interact with cloud resources and other resources.
- You can store commands and scripts in a text file and use a source-control system. 
  
PowerShell differs from a traditional command-line shell in a few ways:

- It operates on objects over text
- It has cmdlets. Commands in PowerShell are called cmdlets (pronounced commandlets). 
- It has many types of commands. Commands in PowerShell can be native executables, cmdlets, functions, scripts, or aliases.

Run the following command in Cloud Shell, and then press Enter to verify that your system is set up to use PowerShell. The `$PSVersionTable` verifies your installation.

`$PSVersionTable.PSVersion` for version of PowerShell

## regions
- Azure is generally available in more than 60 regions in 140 countries.
- Most Azure regions are paired with another region within the same geography to make a regional pair (or paired regions). Regional pairs help to support always-on availability of Azure resources used by your infrastructure. 
- Some services don't require regions. Identify services that don't need region support. Some global Azure services that don't require you to select a region. These services include Microsoft Entra ID, Microsoft Azure Traffic Manager, and Azure DNS.

## Costing 
The main takeaways from this module are:

- Azure regions provide flexibility, data residency, compliance, and resiliency options.
- Azure subscriptions are essential for managing access to Azure resources and billing.
- Azure offers various subscription options such as Free, Pay-As-You-Go, Enterprise Agreement, and Student.
- Azure offers cost-saving options such as reservations, Azure Hybrid Benefits and Azure credits.
- Resource tagging allows for organizing and analyzing resources in Azure.
- Microsoft Cost Management helps monitor and control Azure spending.
- The Pricing Calculator provides billing estimates for different usage cases.

# Azure Policy
- Enables you to enforce rules and ensure compliance with corporate standards adn SLA
- Managemnet Group provide a way to efficently manage access, polices, and compliance across multiple subscription allowing for unified policy and access managemnet. 
- Creating Policy defination and intiative defination allows you to define conventions for resource and contral the scope ofpolices , ensuring resource compliance. 
- The compliance feature is Azure policy helps in determining compliance state of resource and evaluate wheather they're compliant or not.