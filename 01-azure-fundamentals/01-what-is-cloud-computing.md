# What is Cloud Computing?

## 1. Introduction

Cloud computing is the delivery of computing services such as servers, storage, databases, networking, software, and processing power over the internet.

Instead of buying and maintaining physical servers or infrastructure, organizations can use resources provided by a cloud service provider and pay based on their usage.

---

## 2. Traditional Infrastructure vs Cloud Computing

### Traditional Infrastructure

In a traditional environment, an organization needs to:

* Purchase physical servers
* Set up and maintain data centers
* Manage hardware
* Install and update software
* Handle backups and disaster recovery
* Plan infrastructure capacity in advance

### Cloud Computing

With cloud computing, these resources are provided by a cloud provider.

For example:

```text
Application
     |
     v
Cloud Provider
     |
     +--> Compute
     +--> Storage
     +--> Database
     +--> Networking
     +--> Security
```

The organization can focus more on building and maintaining applications instead of managing physical infrastructure.

---

## 3. Key Characteristics of Cloud Computing

### On-Demand Access

Resources can be created whenever they are needed.

For example, a developer can create a virtual machine or database within a few minutes.

### Scalability

Resources can be increased or decreased based on application requirements.

For example:

```text
Low Traffic  →  2 Application Instances

High Traffic →  10 Application Instances
```

### Pay-as-You-Go

Organizations generally pay for the resources they consume instead of purchasing all infrastructure upfront.

### Availability

Cloud providers offer infrastructure across multiple locations and can provide services designed for high availability.

### Global Access

Applications can be deployed in different geographical regions to support users across the world.

---

## 4. Real-World Example

Consider an insurance application built using .NET.

The application may require:

```text
Users
  |
  v
Web Application / API
  |
  +-------------------+
  |                   |
  v                   v
Database           File Storage
  |                   |
  +---------+---------+
            |
            v
        Monitoring
```

Instead of managing physical servers, the application can use cloud services for:

* Hosting the .NET application
* Storing customer documents
* Managing databases
* Monitoring application performance
* Handling authentication and security
* Scaling based on user traffic

---

## 5. Benefits of Cloud Computing

* Reduced upfront infrastructure costs
* Faster deployment
* Easy scalability
* High availability options
* Global infrastructure
* Backup and disaster recovery capabilities
* Reduced hardware maintenance
* Access to managed services

---

## 6. Types of Cloud Services

Cloud services are commonly grouped into three main service models:

### Infrastructure as a Service (IaaS)

The cloud provider manages the physical infrastructure, while the customer manages items such as the operating system, applications, and configurations.

**Example:** Virtual Machines

### Platform as a Service (PaaS)

The cloud provider manages the infrastructure and platform, allowing developers to focus mainly on building and deploying applications.

**Example:** Azure App Service

### Software as a Service (SaaS)

The cloud provider delivers a complete software application that users can access and use.

**Example:** Microsoft 365

> IaaS, PaaS, and SaaS will be covered in detail in the next module.

---

## 7. Major Cloud Providers

Some major cloud providers include:

* Microsoft Azure
* Amazon Web Services (AWS)
* Google Cloud Platform (GCP)

This repository will primarily focus on **Microsoft Azure**.

---

## 8. Cloud Computing and .NET Applications

As a .NET developer, cloud computing allows applications and services to be deployed without directly managing physical infrastructure.

For example:

```text
Client Application
        |
        v
Azure API Management
        |
        v
.NET Web API
        |
   +----+-----+
   |          |
   v          v
Azure SQL   Azure Service Bus
   |
   v
Monitoring
```

Azure provides services that can support different parts of a .NET application, including application hosting, databases, messaging, storage, security, and monitoring.

---

## 9. Simple Definition

**Cloud computing is the delivery of computing resources and services over the internet, allowing organizations to use infrastructure and technology resources without owning and managing all the physical hardware themselves.**

---

## 10. Key Takeaways

* Cloud computing provides computing resources over the internet.
* It reduces the need to manage physical infrastructure.
* Resources can be created and scaled based on demand.
* Organizations can use a pay-for-usage model for many cloud services.
* Common cloud service models include IaaS, PaaS, and SaaS.
* Microsoft Azure is one of the major cloud platforms.
* Cloud computing enables developers to focus more on applications and business requirements.

---

## 11. Interview Questions

### What is cloud computing?

Cloud computing is the delivery of computing services such as servers, storage, databases, networking, and software over the internet.

### What are the main benefits of cloud computing?

Some major benefits include scalability, flexibility, reduced infrastructure management, faster deployment, global availability, and pay-for-usage pricing models.

### What are the main cloud service models?

The three main cloud service models are:

* IaaS — Infrastructure as a Service
* PaaS — Platform as a Service
* SaaS — Software as a Service

### Give an example of cloud computing for a .NET application.

A .NET Web API can be hosted on Azure App Service, use Azure SQL Database for data storage, Azure Service Bus for asynchronous messaging, and Application Insights for monitoring.
