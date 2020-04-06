# Cracking the Azure. AZURE TRAININGS & CERTIFICATION. Preparation and Overview guide

## Table of content and description

Book AZ-900T01-A - Microsoft Azure Fundamentals at skillpipe
Started as of April of 2020th

### Certifications

- AZ-900 - Fundamentals. AZ-900T00 is two days course with labs, AZ-900T01 is one day without labs.
- AZ-103 - Administrator - devops engineers, deploy and operate. Require about ~20-30 hours.
- AZ-203
- AZ-500
- AZ-400 - DevOps Engineer Expert -> required AZ-103 or AZ-203 and AZ-400. Tricky, you should know also devops azure service - pipeline, etc. Require about ~60hours.
- AZ-301 - Azure solutions architect expert -> require AZ-300 and AZ-301

### AZ-900 overview

- Understand cloud concepts
- Understand core azure services
- Understand azure prices
- Understand security, privacy, compliance and trust
- ...

### Plan

AZ-900 -> AZ-103 -> AZ-400


---
CapEx - Capital Expenditure (Expenses) - upfront costs. and predictable fixed costs. value decrease over time. resources can be a loss. In other words, spend on physical infrastructure up front. From accounting side of view like investments in the company (whole company cost grows)
OpEx - Operational Expenditure - ongoing billing costs, pay as you use it. test before commiting. fantastic for agile and small business. resource can be deleted. In other words, spend on services as needed and get billed immediatly. From accounting side of view like operational expenses and non-investments (company just spend the money).
Consumption based model - only pay for what is used, no upfront costs. You consume - you pay.
	- Enterprise agreement...
	
Azure and Azure Stack is not the same. They looks similar, but it is not. Azure stack is not good idea without Azure. Example: You have ship without internet, but you need to collect metrics while crouise. You buy Azure Stack on that ship, and when it in Port, you connect that Azure Stack to Azure and collect all the data in the cloud. Azure stack without Azure itself will be waste of money and resources.

IaaS - infrastructure as a service - uses computer services, that hosted on cloud provider. Service provider is responsible for everything, except: OS, configs and backups - that's is customer responsibility. (Your responsibility are: OS, middleware, runtime environment, data, applications). Most flexible.
PaaS - platform as a service - we are responsible only for our application and data. Provider will take care about infrastructure, os, management and backups, etc. Better productivity, as you focus only on your app.
SaaS - software as a service - provider responsible for everything, like MS teams, office 365, GMail, etc. Pay only for subscription, as example.
BaaS - backup as a service
DaaS - database as a service
IDaaS - Identity as a service

On-premises envs - we are responsible for everything: hardware, infrastructure, building, temperature, security, personal, etc. (networking, storage, servers, virtualization, OS, middleware, runtime environment, data, applications)


Public, Private, Hybric clouds:

Private = as your house, you responsible for everything, even grass outside. Owned and operated only by organization that uses resources. Full control as advantage, but you need workers.
Public = as rented appartment, you responsible only for furniture inside, but does not care about everything outside. Owned by cloud services, which provides resources to multiple organizations and users. Typical access via secure, but internet connection. No CapEx, only OpEx.
Hybric = as condo, you have flat inside building, you are owner of the flat, but other things inside or outside building is not your responsibility. Combines public and private to allow application use resources in most appropriate way.

## Core Azure Services

### Regions

Region contains at least one datacenter. Different regions has different price per virtual machine, traffic, etc.

Five geographies: Americas, Europe, Asia Pacific, Middle East, Africa

Each geography has **Region** pair of region data center: Data resides in the same geography, for example Canada East and Canada Center.

Datacenters in Azure can be Public or Special.
Special reigions:

- US Government (North America, DoD - Department of Defense)
- China 21 Vianet (East and North)
- Germany T-Systems data trustee (Central and NorthEast)

Availability zones (Region pairs): phisically separates location within an Azure region
Each zone has independent cooling, power and networking
Three zones per region.
It helps with protection against datacenter failures, it is also an optional service

Availability Sets: Ensure that a virtual machine is online during maintenance or failure
A virtual machine is assigned to an Update Domain and Fault Domain. Only one Update Domain would be updated at a time. Fault Domain provide physical isolation of data center

Resource group - another core component of Azure
Allow to deploy, manage and monitor resources in a group
Resources in the same resource group should be the same lifespan
When you provision resource, it can only exist in a single resource group
Not all, but most of the resources can be moved across/between resource groups
Rsource can be assigned to different regions within a resource group
Deleting of resource group will also delete all associated resources

Azure account
	Azure subscription
		Azure Resources in Resource Groups
		
		
You can manage with Azure Resouce Manager, using: Azure portal, Azure PowerShell, Azure Command Line Interface (CLI) or REST Clients
With that Azure Resource Manager we can manage our resources, such as: virtaul machines, web apps, storages, databases, etc.


Azure Marketplace - it is not a core component - there are customers can provide custom solutions


Azure Compute - core product: VMs, VM Scale Sets, Azure App Service, Serverless Computing
Azure Compute: common resources are Disk, Processor, Memory, OS, Networking
Azure Compute provides an on-demand service for running cloud-based apps

Azure VMs:
	Infrastructure as a Service
	
Azure VMs Scale Sets:
	bunch of the same VMs, running at the same time. Provides HA, automatic scalability and load balancing
	Used in large scale instances, Season events (black friday, sport events, etc.)
	
Azure App Service:
	Platform as a Service
	
Azure Functions - app service
	Run small piece of code, instead of full app. Triggered by events. IoT or processing of data.
	
Azure Containers:
	Do not include an OS that can be managed, but the OS files can be refferenced to run an application. Libraries can be added.
	
Container consists of:
	Azure Platform
		Virtual Machine
			OS (Win or Linux)
				Container Services (Docker)
					Container

Azure has two container services:
	Azure Container Instances - allow upload of your container to Azure for Execution, platfor as a service offering.
	Azure Kubernetes Service - an orchestration service, used to manage and update large numbers of containers
	
	
Azure Networking: - also core network. Azure Virtual Network (VNet) isolates and segments azure resources
	VNet securely connects various Azure resources and on-premises
	Provides filtering and routing of network traffic
	By default contained to one region. Virtual network peering can be used to connect different regions (Peering or VPN Gateway)
	VPN Gateway can be used to connect on-premises resources to Azure or to connect to another Azure network via public internet. Traffic is Encrypted.
	Only one VPN gateway allowed per VNet. Number of connection is based on SKU.
	
Azure Load Balancer:
	Distibutes traffic in, out and within the network
	Private and Public. For public or internal traffic.
	
Application Gateway - load balances web traffic only to web applications.
	Routes traffic based on source/destination IP and port
	Supports URL-based routing (traffic is directed, based on URL, /pics/ or /videos/*)
	etc.
	
CDN - Content Delivery Network.
	Globally distributed servers used to efficiently deliver web content in the user's region
	Content cached to minimize latency
	
Azure Storage:
	Stores files, messages and tables.
	Mssively scalable, Durable and High available, secure.
	Supports Structured data, semisturctured data, unstructered data.
	
	Structured data:
		Has a schema, rigid format, relational data, uses keys to relate row in one table to a row in another table. Typical use - Database
		
	Semistructured data:
		Ad-hoc schema
		Nonrelational format
		Known as NoSQL data
		Uses tags for data location
		Typical usage: tab-delimited, files, .csv, XML, JSON
		
	Unstructed data:
		No schema or data structure: PDF, Doc, JPG, AVI, etc.
		
Storage Type in AZURE:
	Blob, Disk, File, Archive
	
	Blob - used for unstructured data, highly scalable, recommended for most scenarios. Common use case: streaming audio, video, store backups, images, docs.
	Disk - persistent storage for VM. Storage for OS and Storage for Data (two disks in sum). You must attach your data disk to your Virtaul machine and to not store data at temporary disks.
	File storage - file share in the cloud. accessed using SMB. Shares can be mounted to a system providing direct access to the files of the cloud. Even from your lapton. Support multiple connections.
	Archive - for long-term backups or data, which is required unfrequently. stored offline. low storage costs. required more time to access.
	
Azure Databases:
	Platform as a Service.
	Fully managed databases, High Availabile.
	Databases: Cosmos DB, SQL Database, SQL Warehouse, Azure Database Migration Service (DMS)
	
	CosmosDB:
		Globally distibuted, multimodel database service.
		Scale agross azure regions
		Highly responsive (less than 10 ms) and HA (99.999%)
		Automatically replicate data closes to the user.
		Typical usage in web, mobile, gaming or IoT apps.
		
	Azure SQL Database:
		Relational Database Service (DaaS)
		Fully managed SQL database and HA with automatic backups. Typical usage as corporate database.
		
	Azure SQL Warehouse:
		Runs complex queries on petabytes of data
		Uses massively parallel processing (MPP)
		Used for big data
		
	Database Migration Service (DMS):
		Migrate database to Azure with little downtime
		Uses the Data Migration Assistant to provide reports and guides to step you into migration
		
		
Popular AZURE Solutions:
	- IoT Hub: Central message hub for bidirectional communication between IoT Devices and the application.
	- IoT Central: Globally managed SaaS solution to monitor and manage IoT devices
	- Big Data and Analytics: SQL Warehouse
		* HDInsight - Service for open-source analytics such as Apache Spark or Apache Hadoop
		* Data Lake Analytics: on-demand analytics job service, no hardware required.
	- Artificial Intelligence (AI)
		* Azure Machine Learning Service - Build, train, deploy, manage and track models. ML Studio Service - Visual interactive workspace to build and deploy ML Solutions. No code required, drag and drop. Models, created in ML Studio, can not be deployed or managed via ML Service.
	- Serverless computing: Runs code only on the host. Respond to an Event, such as trigger from IoT Device. Typically used for processing incoming data.
		* Logic Apps: Automate tasks, processes and more for integration with other services, apps, data, system and devices. No code required. Integrate on cloud or with on-prem solutions.
		* Event grid: Event routing service. Take and event source (IoT Hub or Storage for example) and sends the event handler for processing.
	...
	
Azure Management tools:
	Azure Portal
	PowerShell
	CLI
	Azure Cloud Shell - is Browser-based scripting env: bash or powershell. launched from the portal and required storage account.
	Advisor - recommendations
	
Azure Security
	Identity and Tools
	Azure Identity service:
		- Authentication (who you. like vehicle license/driver permit)
		- Authorization (what, when and where you can drive, what type of vehicle)
	Azure Active Directory: Cloud-based identity and access management solution. Provides Authentication, SSO (Single sign-on), App management, B2B and B2C identity services, Device management.
	Azure Multi-factor Authentication: two or more methods. Something you know (password), you have (phone), you are (fingerprint).
	Azure Security Center: - Security management system for both, cloud and on-premises workloads. Evaluates the security of current resources. Provide recommendations and threat detection alerts.
	Azure Key Vault: Central Repository to store applications secrets. Supports tokens, passwords, certs, and etc. Create and Control encryption keys. Provision, manage and deploy public and private SSL/TSL Certs. Storing secretcs backed by hardware security modules (HSMs).
	Azure Information Protection (AIP): Organize and classify documents and e-mails (confidentialm for internal use only, etc.). Automatic when using rules. Manual for users.
	Azure Advanced Threat Protection (ATP): Identify compromised identities, advanced threats, insider actions, malicious attacks, etc.
	
Network Security:
	Azure DDoS Protection: - Distributed denial access of service. Basic protection included by default
	Azure Firewall: - Control access to Azure resources
	NSG: Network Security Groups: Allow or Deny network traffic to and from resources in an Azure VNet subnet. Rules are processed in priority order. Lower processed first.
	ASG: Application Security Group: Group virtual machines across virtual networkds. It allows to filter traffic to the virtual machines in the security group, not the network. Allows to segment virtual machines, based on applications.
	
Azure Governance Methodologies, Monitoring and Reporting.
	Azure Policies: Policies enforce rules over azure resources, ensures the resource is compliant.
	Initiatives: group of policies, that manages as single unit. It reduces the complexity of multiple policies.
	Role-Based Access Control (RBAC): Default are: Owner, Contributor, Reader. You can create your own custom roles.
	Azure Locks: prevents deletion or modification of a resource. CanNotDelete; ReadOnly.
	Azure Advisor Security Assistance: provide a list of security recommendations.
	Azure Blueprints: Applies the same scope to a set of Resources to be compliant. Blueprint contains: role assigment, policy, ARM templates (Azure Resource Manager) and Resource Groups.
	
Monitor and Reporting:
	Azure Monitor: to monitor availability and performance of resources using metrics and logs. (app monitoring data, guest os metrics, azure resource metrics, etc)
	Azure Service Health: dashboard, which provides insight into Azure and your resources, Azure Status, Azure Service and Resource Health.
	Tags: Group related resources. A Tag contains a name and pair value
	
Privacy, Compiance and Data Protection
	Industry Compliance Terms:
		GDPR: General Data Protection Regulation
		ISO: Information Standards Organization
		NIST CSF: National Institute of Standards and Technology Cybersecurity Framework
		
	Microsoft Privacy Statement: What personal data is collected, How it is processed or used, What it will be used for, including sharing.
	Azure Trust Center
	Service Trust Portal
	Compliance Manager
	Azure Governance Services: US, Germany, China.
	
Azure Subscriptions:
	Allows resources to be created and managed. Linkds to Azure AD for authentication and authorization. Multiple subscriptions can be created by one account holder.
	Options: Pay-As-You-Go; Free account; Member offers;
	Limits: Service limits for each subscription type. Some Service limits can be increased, some not.
	Subscription Billing Boundary
	Subscription Access Control Boundary (to organization departments)
	Management groups - Group of Azure objects in a collection. Allow us to manage policies, access, and compliance for the entire group.
	
	See pics/
	
Azure Planning and Management Costs:
	- Web Direct: required credit card, purchase directly from Azure web site.
	- CSP (Cloud Solution Provider)
	- Enterprise Agreement
	
Factors, affecting costs of Azure:
	Resource Type, size, limits
	Services
	Locations
	
Billing Zones:
	Don't charge for ingress (inbound in data center) traffic,
	But will bill you for Egress (outbond of data center) traffic.
	Geographical zones:
		- Zone 1: West US, East US, Europe
		- Zone 2: Australia Central, Japan West, Central India
		- Zone 3: Brazil South Only
		- DE Zone 1: Germany Central and Germany Northeast
		
Online pricing calculator
TCO Calculator (Total Cost of Ownership)
Azure Cost Management
You can also set spending limits or quotas to see an Alert when you getting closes

Azure Reservations: Prepay for one year or three years of service.

Azure support options:
	- Docs for all
	- Paid Support plans:
		developer, standart, professional direct, premier (not all suppport plans are available for all customers)
	- Open a support ticket
	- Available support channel (Stackoverflow, twitter, msdn forums, etc)
	- Azuke knowledge center
	
Azure Service Level Agreement (SLA)
	Contains performance details of an Azure Service. And also contains information on what happens, if the SLA is not met.
	99.95 x 99.99 = 99.94 %
	
Azure service lifecycle:
	...
	
	
AZ-103 (LinkedIn Learning):
	AZURE Subscriptions and Resources
	
	Assign Administrator Permissions:
		Roles:
			- Classic Roles: Account admin, Service admin, Co-Admin
				- Service Administrator: same as account admin, if the service admin changed, then account admin will lose access to the portal. Also this service admin can't add user out of the directory. (?)
			- RBAC (Role-Based Access Control):
				- owner: full access to all resources and can delegate access to others 
				- contributor: can't grant access to others, but can create and manage resources
				- reader: view resources only
				- user access admin: special acc, for root access and temporary usage
				- and 70 built-in roles, custom roles
			- AD roles
				- Admin: Manage AD Resources
				- Other: Billing, Device, User acc, etc.
	
	Subscription -> Access Control (IAM) -> New (add) -> Select Role -> choose the user on which apply that selected role -> Save
	
	Cost Center
		- Quotas
			
		- Taging
			To apply tags to a resource, you must have write access to the Microsoft.Resources/tags resource type. The Tag Contributor role lets you apply tags to an entity without having access to the entity itself.
			
			
---the developers guide to azure
---introduction to IaaS on Azure
--azure trainings and certification resources

	


-----
undestand cloud concepts
public, private, hybrid
IaaS, PaaS, SaaS and serverless

The most basic category of cloud computing services. With IaaS, you rent IT infrastructure—servers and virtual machines (VMs), storage, networks, operating systems—from a cloud provider on a pay-as-you-go basis

Platform as a service refers to cloud computing services that supply an on-demand environment for developing, testing, delivering, and managing software applications. PaaS is designed to make it easier for developers to quickly create web or mobile apps, without worrying about setting up or managing the underlying infrastructure of servers, storage, network, and databases needed for development.

Software as a service is a method for delivering software applications over the Internet, on demand and typically on a subscription basis. With SaaS, cloud providers host and manage the software application and underlying infrastructure, and handle any maintenance, like software upgrades and security patching. Users connect to the application over the Internet, usually with a web browser on their phone, tablet, or PC.

Serverless computing
Overlapping with PaaS, serverless computing focuses on building app functionality without spending time continually managing the servers and infrastructure required to do so. The cloud provider handles the setup, capacity planning, and server management for you. Serverless architectures are highly scalable and event-driven, only using resources when a specific function or trigger occurs.


Azure Service Bus
	It's message broker. Data transfered between applications and services with binary messages. Scenarios: Messaging (journals, orders, etc); Decouple applications. Improve reliability and scalability of applications and services. Client and service don't have to be online at the same time. ; Topics and subscriptions. Enable 1:n relationships between publishers and subscribers.; - Message sessions. Implement workflows that require message ordering or message deferral.
	- Namespace - is a container for all messaging components, often serve as application container.
	- Queue - point-to-point communication. stores messages until recieving application is available to recieve and process them.
	- Topic - useful in publish/subscribe scenarios. Can have multiple independent subscriptions to recieve all messages sent to a topic. You can youse rules and filters to define conditions that trigger optional actions.
	- Message sessions - used to create FIFO (first-in, first-out)
	- Autoforwarding - chains a queue or subscription to another topic or queue.
	- Dead Letter Queue (DLQ) - A DLQ holds messages that can't be delivered to any receiver. It holds messages that can't be processed. Service Bus lets you remove messages from the DLQ and inspect them.An application might, with help of an operator, correct issues and resubmit the message, log the fact that there was an error, and take corrective action. From an API and protocol perspective, the DLQ is mostly similar to any other queue, except that messages can only be submitted via the dead-letter operation of the parent entity. In addition, time-to-live isn't observed, and you can't dead-letter a message from a DLQ. The dead-letter queue fully supports peek-lock delivery and transactional operations.
	- Scheduled delivery - You can submit messages to a queue or topic for delayed processing. You can schedule a job to become available for processing by a system at a certain time.
	- Message deferral - A queue or subscription client can defer retrieval of a message until a later time. This deferral might be because of special circumstances in the application. The message remains in the queue or subscription, but it's set aside.
	Batching - Client-side batching enables a queue or topic client to delay sending a message for a certain period of time. If the client sends additional messages during this time period, it transmits the messages in a single batch.
	Transactions - groups two or more operations together into an execution scope. Service Bus supports grouping operations against a single messaging entity within the scope of a single transaction. A message entity can be a queue, topic, or subscription.
	Filtering and actions - Subscribers can define which messages they want to receive from a topic. These messages are specified in the form of one or more named subscription rules. For each matching rule condition, the subscription produces a copy of the message, which can be differently annotated for each matching rule.
	Autodelete - Autodelete on idle enables you to specify an idle interval after which a queue is automatically deleted.
	Duplicate detection - An error could cause the client to have a doubt about the outcome of a send operation. Duplicate detection enables the sender to resend the same message. Another option is for the queue or topic to discard any duplicate copies.
	Security protocols - Service Bus supports security protocols such as Shared Access Signatures (SAS), Role Based Access Control (RBAC) and Managed identities for Azure resources.
	Geo-DR - When Azure regions or datacenters experience downtime, Geo-disaster recovery enables data processing to continue operating in a different region or datacenter.
	Service Bus supports standard AMQP 1.0 and HTTP/REST protocols.




Azure Queue Storage --- /????

Azure Cloud Services --- /???? https://stackoverflow.com/questions/50033033/what-is-azure-cloud-service
								https://github.com/MicrosoftDocs/azure-docs/issues/11861
								
								
								

### Terms and difference between them

*High Availability* - is software used to ensure that systems are running and available most of the time. High availability is a high percentage of time that the system is functioning. It can be formally defined as (1 – (down time/ total time))*100%. Although the minimum required availability varies by task, systems typically attempt to achieve 99.999% (5-nines) availability. This characteristic is weaker than fault tolerance, which typically seeks to provide 100% availability, albeit with significant price and performance penalties.

High availability software is measured by its performance when a subsystem fails, its ability to resume service in a state close to the state of the system at the time of the original failure, and its ability to perform other service-affecting tasks (such as software upgrade or configuration changes) in a manner that eliminates or minimizes down time. All faults that affect availability – hardware, software, and configuration need to be addressed by High Availability Software to maximize availability.

Big-O - 

Scalability - Scalability is the ability of a program to scale. For example, if you can do something on a small database (say less than 1000 records), a program that is highly scalable would work well on a small set as well as working well on a large set (say millions, or billions of records).

	Like gap said, it would have a linear growth of resource requirements. Look up Big-O notation for more details about how programs can require more computation the larger the data input gets. Something parabolic like Big-O(x^2) is far less efficient with large x inputs than something linear like Big-O(x).

	Scalability can be achieved in 2 ways:

	Vertical - In this way, you add more hardware like more RAM, processor or more nodes. You also introduce load balancer, which will help in routing the incoming calls to various servers based on the routing algorithm used. The application is now able to handle more load as load is being shared across the servers.

	Horizontal - In horizontal scaling, you architect/design the application in such a way that it can behave well in case of more parallel traffic. You check how you are managing the memory, sessions , cache & state etc. If you are using the session to maintain the user information, under heavy load single server could be more busy managing the servers, so in this case you can check possibility of going stateless. It can also respond to incoming requests from same user in parallel instead serial replies which happens if sessions are being used.

	When talking about systems scalability, we usually differentiate between

	"Scale up" - the ability to grow by using stronger hardware
	"Scale out"- the ability to grow by adding more hardware

Scalability and Elasticity are very similar, first mostly about physical opportunities, second about flexible management of resources

Elasticity - 
Agility - 
Fault Tolerance - 
Disaster Recovery - 
Global Reach - 
Customer Latency Capability - 
Predictive cost considerations - 
Security - 



-----

AZ-900 questions (cracking the Azure questions):
	- Count benefits of using cloud
		+ you can have stage (uat/pre-prod) as the same as prod easier.
	- Which type of cloud will give you more flexibility
	- Which cloud you should choose for legacy app with specific hardware
	- Which cloud you should choose for new app with common hardware
	


------------