# Azure Compute Overview

## 1. Introduction

In cloud computing, **compute** refers to the processing resources used to run applications, services, workloads, and code.

In a traditional environment, an organization needs to purchase and manage physical servers to run applications.

With Microsoft Azure, compute resources can be created and managed in the cloud.

Azure provides different compute services based on application requirements.

---

## 2. What is Azure Compute?

Azure Compute is a collection of cloud services that provide the processing power required to run applications and workloads.

Depending on the requirement, an application can run on:

* Virtual Machines
* Managed application platforms
* Serverless environments
* Containers
* Kubernetes clusters

A simplified view:

```text
                    Azure Compute
                         |
        +----------------+----------------+
        |                |                |
        v                v                v
 Virtual Machines    App Service      Functions
        |                |                |
        +----------------+----------------+
                         |
                         v
                  Applications
```

---

## 3. Why Do We Need Compute Services?

Every application needs processing power to execute code.

For example, a .NET application needs an environment where it can:

* Run application code
* Process user requests
* Connect to databases
* Execute business logic
* Communicate with other services

Traditionally:

```text
.NET Application
       |
       v
Application Server
       |
       v
Physical Infrastructure
```

With Azure:

```text
.NET Application
       |
       v
Azure Compute Service
       |
       v
Azure Cloud Infrastructure
```

Azure manages some or most of the underlying infrastructure depending on the compute service you choose.

---

## 4. Main Azure Compute Services

### Azure Virtual Machines

Azure Virtual Machines provide virtualized servers in the cloud.

You have greater control over:

* Operating System
* Installed software
* Server configuration
* Application environment

Example:

```text
Azure Virtual Machine
        |
        v
Windows / Linux
        |
        v
.NET Application
```

**Best suited for:**

* Legacy applications
* Applications requiring OS-level control
* Custom software installations

---

### Azure App Service

Azure App Service is a managed platform for hosting web applications, APIs, and backend services.

Developers can focus mainly on:

* Application code
* Deployment
* Configuration
* Scaling

Example:

```text
Users
   |
   v
Azure App Service
   |
   v
ASP.NET Core Web API
```

**Best suited for:**

* Web applications
* REST APIs
* Backend services
* Modern .NET applications

---

### Azure Functions

Azure Functions is a serverless compute service used to run code based on events or triggers.

Example:

```text
Event
  |
  v
Azure Function
  |
  v
Execute Code
```

Common triggers include:

* HTTP requests
* Timer schedules
* Queue messages
* Service Bus messages
* Blob Storage events

**Best suited for:**

* Background processing
* Event-driven applications
* Scheduled jobs
* Integration workflows

---

### Containers

Containers package an application along with its dependencies.

Azure provides different services for running containers.

Example:

```text
Container
│
├── Application
├── .NET Runtime
└── Dependencies
```

Containers provide consistency across different environments.

---

### Azure Kubernetes Service (AKS)

Azure Kubernetes Service is a managed Kubernetes service used to deploy and manage containerized applications.

Example:

```text
                    AKS Cluster
                         |
          +--------------+--------------+
          |              |              |
          v              v              v
     Container 1    Container 2    Container 3
```

AKS is commonly used for:

* Microservices architectures
* Large containerized applications
* Applications requiring advanced orchestration and scaling

---

## 5. Comparison of Azure Compute Services

| Service                  | Compute Model      | Best For                                  | Level of Infrastructure Management |
| ------------------------ | ------------------ | ----------------------------------------- | ---------------------------------- |
| Azure Virtual Machines   | IaaS               | Legacy and custom environments            | Higher                             |
| Azure App Service        | PaaS               | Web applications and APIs                 | Low                                |
| Azure Functions          | Serverless         | Event-driven workloads                    | Very Low                           |
| Containers               | Container-based    | Portable applications                     | Depends on service                 |
| Azure Kubernetes Service | Managed Kubernetes | Microservices and container orchestration | Medium                             |

---

## 6. Choosing the Right Compute Service

The choice depends on the application's requirements.

### Choose Virtual Machines when:

* You need control over the operating system.
* You need to install custom software.
* You are migrating a legacy application.
* You require server-level configuration.

### Choose App Service when:

* You are hosting a web application.
* You are deploying a REST API.
* You want to focus on application development.
* You do not want to manage servers.

### Choose Azure Functions when:

* Code needs to run in response to an event.
* You have background processing.
* You need scheduled jobs.
* You are building serverless applications.

### Choose Containers or AKS when:

* You are building containerized applications.
* You have multiple microservices.
* You need portability across environments.
* You require advanced container orchestration.

---

## 7. Real-World .NET Example

Consider an insurance application with multiple workloads.

```text
                         Users
                           |
                           v
                    Azure App Service
                           |
                           v
                     .NET Web API
                           |
              +------------+------------+
              |                         |
              v                         v
       Azure SQL Database        Azure Service Bus
                                          |
                                          v
                                   Azure Function
                                          |
                                          v
                                  Background Processing
```

In this example:

* **Azure App Service** hosts the customer-facing .NET API.
* **Azure SQL Database** stores application data.
* **Azure Service Bus** enables asynchronous messaging.
* **Azure Functions** process messages in the background.

Different Azure services are selected based on the workload.

---

## 8. Compute and Scalability

Azure compute services can support scaling based on application demand.

For example:

```text
Low Traffic

Users
  |
  v
[ Application Instance ]
```

During higher traffic:

```text
High Traffic

              Load
               |
      +--------+--------+
      |        |        |
      v        v        v
   App 1    App 2    App 3
```

Adding more application instances is known as **scaling out**.

Increasing the resources of an existing instance, such as CPU or memory, is known as **scaling up**.

Different Azure compute services provide different scaling capabilities.

---

## 9. Simple Comparison

You can think about Azure compute services like this:

```text
Need Full Server Control?
        |
       Yes
        |
        v
Virtual Machine


Need to Host Web App / API?
        |
       Yes
        |
        v
Azure App Service


Need Event-Based Processing?
        |
       Yes
        |
        v
Azure Functions


Need Container Orchestration?
        |
       Yes
        |
        v
Azure Kubernetes Service
```

---

## 10. Key Takeaways

* Compute provides the processing power required to run applications and workloads.
* Azure provides multiple compute services for different requirements.
* Azure Virtual Machines provide greater infrastructure and operating system control.
* Azure App Service is suitable for hosting web applications and APIs.
* Azure Functions are used for serverless and event-driven workloads.
* Containers package applications with their dependencies.
* AKS helps manage and orchestrate containerized applications.
* The right compute service depends on application architecture and business requirements.

---

## 11. Interview Questions

### What is Azure Compute?

Azure Compute refers to Azure services that provide processing resources for running applications, workloads, and code in the cloud.

### What are some common Azure Compute services?

Common Azure Compute services include:

* Azure Virtual Machines
* Azure App Service
* Azure Functions
* Azure Container services
* Azure Kubernetes Service

### What is the difference between Azure Virtual Machines and Azure App Service?

Azure Virtual Machines provide greater control over the operating system and server environment.

Azure App Service is a managed platform that allows developers to deploy applications without managing the underlying servers.

### When would you use Azure Functions?

Azure Functions are useful for event-driven workloads, background processing, scheduled jobs, and applications that need to execute code in response to triggers.

### What is the difference between scaling up and scaling out?

**Scaling up** means increasing the resources, such as CPU or memory, of an existing instance.

**Scaling out** means adding more instances to handle increased workload.
