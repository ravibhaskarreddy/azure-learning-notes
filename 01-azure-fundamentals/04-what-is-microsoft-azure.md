# What is Microsoft Azure?

## 1. Introduction

Microsoft Azure is a cloud computing platform provided by Microsoft.

It provides a wide range of cloud services that organizations can use to build, deploy, manage, and scale applications and infrastructure.

Instead of purchasing and maintaining physical servers, organizations can use Azure services to create and manage resources in the cloud.

---

## 2. What Can We Do with Azure?

Azure provides services for different technology requirements, including:

* Application hosting
* Virtual machines
* Databases
* Storage
* Networking
* Identity and security
* Integration and messaging
* Monitoring
* Analytics
* Artificial Intelligence
* DevOps and deployment

A simplified view:

```text
                    Microsoft Azure
                           |
     +----------+----------+----------+----------+
     |          |          |          |          |
  Compute    Storage    Database   Networking  Security
     |
     +--> App Service
     +--> Virtual Machines
     +--> Azure Functions
     +--> Containers
```

---

## 3. Why Do Organizations Use Azure?

Organizations use Azure to avoid managing all physical infrastructure themselves and to take advantage of cloud services.

Some common benefits include:

* On-demand resource provisioning
* Scalability
* Global infrastructure
* Managed services
* Security features
* High availability options
* Integration with Microsoft technologies
* Support for different programming languages and platforms

---

## 4. Azure Service Categories

Azure contains many services. They can be grouped into major categories.

### Compute

Compute services provide processing power to run applications.

Examples:

* Azure Virtual Machines
* Azure App Service
* Azure Functions
* Azure Kubernetes Service

### Storage

Storage services are used to store files, documents, images, backups, and application data.

Examples:

* Azure Blob Storage
* Azure Files
* Azure Queue Storage

### Databases

Azure provides managed database services.

Examples:

* Azure SQL Database
* Azure Cosmos DB
* Azure Database for PostgreSQL

### Networking

Networking services help applications and resources communicate securely.

Examples:

* Virtual Network
* Load Balancer
* Application Gateway
* Azure DNS

### Identity and Security

These services help manage users, applications, access, and secrets.

Examples:

* Microsoft Entra ID
* Azure Key Vault
* Role-Based Access Control (RBAC)
* Managed Identities

### Integration and Messaging

These services help different applications and systems communicate.

Examples:

* Azure Service Bus
* Azure Event Grid
* Azure Event Hubs
* API Management

### Monitoring

Azure provides services to monitor applications and infrastructure.

Examples:

* Azure Monitor
* Application Insights
* Log Analytics

---

## 5. Example: .NET Application in Azure

Consider a customer-facing application built using .NET.

A possible Azure architecture could look like this:

```text
                    Users
                      |
                      v
              Azure API Management
                      |
                      v
                .NET Web API
              Azure App Service
                      |
          +-----------+------------+
          |                        |
          v                        v
   Azure SQL Database       Azure Service Bus
          |                        |
          |                        v
          |                 Background Service
          |
          v
      Application Data

                      |
                      v
            Azure Monitor /
          Application Insights
```

In this architecture:

* **Azure App Service** hosts the .NET application.
* **Azure API Management** manages and exposes APIs.
* **Azure SQL Database** stores application data.
* **Azure Service Bus** supports asynchronous communication.
* **Application Insights** helps monitor application performance and issues.

---

## 6. Azure and Cloud Service Models

Azure provides services across different cloud service models.

### IaaS

Azure provides infrastructure services where customers have more control.

Example:

```text
Azure Virtual Machine
```

The customer manages the operating system and applications.

### PaaS

Azure provides managed platforms where developers can focus on applications.

Examples:

```text
Azure App Service
Azure Functions
Azure SQL Database
```

Azure manages most of the underlying infrastructure.

### SaaS

Microsoft also provides complete software applications that users can access and use.

Example:

```text
Microsoft 365
```

---

## 7. Azure Resources

Everything created and managed in Azure is generally referred to as a **resource**.

Examples:

* Virtual Machine
* App Service
* Storage Account
* SQL Database
* Virtual Network
* Service Bus

For example:

```text
Azure Subscription
       |
       v
Resource Group
       |
       +--> App Service
       |
       +--> Azure SQL Database
       |
       +--> Storage Account
       |
       +--> Service Bus
```

Azure resources are usually organized into **Resource Groups**, which help manage related resources together.

> Azure resource hierarchy will be covered in a separate topic.

---

## 8. Azure Portal

The Azure Portal is a web-based interface used to manage Azure resources.

Using the portal, users can:

* Create resources
* Configure services
* Monitor applications
* Manage users and access
* View costs
* Configure networking
* Manage subscriptions

Azure resources can also be managed using:

* Azure CLI
* Azure PowerShell
* ARM templates
* Bicep
* Terraform
* Azure SDKs

---

## 9. Real-World Example

Imagine an insurance company developing a new claims application.

Instead of setting up physical infrastructure, the company can use Azure services.

```text
                 Customers
                     |
                     v
                Web / Mobile
                     |
                     v
              API Management
                     |
                     v
              Azure App Service
                     |
         +-----------+-----------+
         |                       |
         v                       v
   Azure SQL Database      Service Bus
                                 |
                                 v
                         Claims Processing
                                 |
                                 v
                         External Systems
```

The organization can independently scale and manage different parts of the application.

---

## 10. Why Azure is Useful for a .NET Developer

Azure integrates well with the Microsoft and .NET ecosystem.

A .NET developer can use Azure for:

* Hosting ASP.NET Core applications
* Deploying Web APIs
* Running serverless applications using Azure Functions
* Storing application data
* Managing secrets using Key Vault
* Implementing messaging using Service Bus
* Monitoring applications using Application Insights
* Automating deployments using CI/CD pipelines

This allows developers to build cloud-based and enterprise applications using familiar technologies.

---

## 11. Key Takeaways

* Microsoft Azure is a cloud computing platform provided by Microsoft.
* Azure provides services for compute, storage, databases, networking, security, integration, and monitoring.
* Azure supports IaaS, PaaS, and SaaS models.
* Azure resources include services such as Virtual Machines, App Services, Storage Accounts, and SQL Databases.
* Azure provides both managed services and infrastructure services.
* Azure can be used to build, deploy, monitor, and scale applications.
* Azure is widely used for enterprise applications and integrates well with the .NET ecosystem.

---

## 12. Interview Questions

### What is Microsoft Azure?

Microsoft Azure is a cloud computing platform provided by Microsoft that offers services for building, deploying, managing, and scaling applications and infrastructure.

### What are Azure resources?

Azure resources are individual services or components created and managed in Azure, such as Virtual Machines, App Services, Storage Accounts, and SQL Databases.

### What are some major categories of Azure services?

Major Azure service categories include:

* Compute
* Storage
* Databases
* Networking
* Identity and Security
* Integration
* Monitoring

### How can a .NET application use Azure?

A .NET application can be hosted on Azure App Service, store data in Azure SQL Database, use Azure Service Bus for messaging, use Azure Key Vault for secrets, and use Application Insights for monitoring.

### What is the difference between Azure Portal and Azure CLI?

Azure Portal provides a graphical web interface for managing Azure resources.

Azure CLI is a command-line tool used to create and manage Azure resources through commands and automation.
