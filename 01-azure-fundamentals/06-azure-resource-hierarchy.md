# Azure Resource Hierarchy

## 1. Introduction

Microsoft Azure uses a hierarchical structure to organize and manage resources.

This structure helps organizations manage:

* Access and permissions
* Billing
* Policies
* Resource organization
* Governance

The main Azure resource hierarchy is:

```text
Management Groups
        |
        v
   Subscriptions
        |
        v
  Resource Groups
        |
        v
    Resources
```

Each level provides a way to organize Azure resources and apply management, access, and governance controls.

---

# 2. Azure Hierarchy Overview

Let's understand the hierarchy from top to bottom.

```text
Organization
     |
     v
Management Group
     |
     v
Subscription
     |
     v
Resource Group
     |
     +-----------------------+
     |           |           |
     v           v           v
App Service   SQL Database  Storage Account
```

For example, an organization may have multiple subscriptions for different environments or departments.

Each subscription can contain multiple resource groups.

Each resource group can contain multiple Azure resources.

---

# 3. Management Groups

## What is a Management Group?

A **Management Group** is used to organize multiple Azure subscriptions.

It is useful for large organizations that need to manage governance, policies, and access across multiple subscriptions.

Example:

```text
Organization
      |
      v
Management Group
      |
      +------------------------+
      |                        |
      v                        v
Production Subscription   Development Subscription
```

Policies and access controls can be applied at the Management Group level and inherited by lower levels.

## Example

An organization may have the following structure:

```text
Management Group
│
├── Production
│   ├── Production Subscription 1
│   └── Production Subscription 2
│
└── Non-Production
    ├── Development Subscription
    └── Testing Subscription
```

Management Groups are mainly useful for organizing and governing multiple subscriptions.

---

# 4. Azure Subscription

## What is a Subscription?

An Azure Subscription is a logical container that provides a boundary for:

* Billing
* Access management
* Resource usage

Azure resources are created within a subscription.

Example:

```text
Azure Subscription
│
├── Resource Group: Development
│
├── Resource Group: Testing
│
└── Resource Group: Production
```

An organization can have multiple subscriptions.

For example:

```text
Management Group
│
├── Development Subscription
│
├── Testing Subscription
│
└── Production Subscription
```

This separation helps organizations manage costs, access, and environments independently.

## Example Use Cases

Multiple subscriptions may be used for:

* Development
* Testing
* Production
* Different departments
* Different projects
* Separate billing requirements

---

# 5. Resource Group

## What is a Resource Group?

A **Resource Group** is a logical container used to organize related Azure resources.

Resources that belong to the same application, project, or environment can be placed in the same Resource Group.

Example:

```text
Resource Group: Insurance-App-Dev
│
├── Azure App Service
├── Azure SQL Database
├── Storage Account
└── Application Insights
```

The Resource Group makes it easier to manage related resources together.

## Benefits of Resource Groups

Resource Groups help with:

* Organizing related resources
* Managing access
* Monitoring resources
* Applying tags
* Managing deployments
* Managing resource lifecycles

For example, if all resources belong to a temporary development environment, they can be managed together.

> Deleting a Resource Group deletes the resources contained within it, so this action should be used carefully.

---

# 6. Azure Resources

## What is an Azure Resource?

An Azure Resource is an individual service or component created within Azure.

Examples include:

* Azure Virtual Machine
* Azure App Service
* Azure SQL Database
* Azure Storage Account
* Azure Service Bus
* Azure Key Vault
* Virtual Network

Example:

```text
Resource Group
│
├── App Service
│
├── Azure SQL Database
│
├── Storage Account
│
├── Service Bus
│
└── Application Insights
```

Each of these services is an individual Azure resource.

---

# 7. Real-World Example

Consider a .NET insurance application.

The organization has separate environments for development, testing, and production.

A possible Azure structure could be:

```text
Management Group
        |
        +----------------------------+
        |                            |
        v                            v
Non-Production                  Production
        |                            |
        v                            v
Dev Subscription             Prod Subscription
        |                            |
        v                            v
Insurance-App-Dev-RG        Insurance-App-Prod-RG
        |                            |
        +-------------------+--------+
        |          |        |
        v          v        v
   App Service   SQL DB   Service Bus
```

This structure separates environments and makes it easier to manage security, access, and billing.

---

# 8. Resource Group vs Subscription

It is important to understand the difference.

| Feature  | Subscription                            | Resource Group                        |
| -------- | --------------------------------------- | ------------------------------------- |
| Purpose  | Billing and management boundary         | Logical grouping of related resources |
| Contains | Resource Groups and resources           | Azure resources                       |
| Used For | Cost, access, and governance boundaries | Organizing application resources      |
| Example  | Production Subscription                 | Insurance-App-Prod-RG                 |

A simple way to remember:

```text
Subscription
    |
    | Contains
    v
Resource Groups
    |
    | Contains
    v
Resources
```

---

# 9. Azure Resource Hierarchy and Access Control

Azure access can be managed using **Role-Based Access Control (RBAC)**.

Permissions can be assigned at different levels of the hierarchy.

```text
Management Group
        |
        v
   Subscription
        |
        v
  Resource Group
        |
        v
    Resource
```

For example:

### Subscription Level

A user may have access to manage resources across the entire subscription.

### Resource Group Level

A developer may have access only to resources inside a specific Resource Group.

### Resource Level

A user may be given access to a specific resource, such as a Storage Account.

Permissions assigned at higher levels can generally be inherited by lower levels.

> Azure RBAC and access management will be covered in detail in the Identity and Security module.

---

# 10. Tags

Azure Tags are key-value pairs that can be used to organize and manage resources.

Example:

```text
Environment = Development
Application = InsuranceApp
Owner = DevelopmentTeam
```

Tags can help organizations:

* Identify resources
* Track costs
* Organize applications
* Automate operations

Example:

```text
App Service
│
├── Environment: Production
├── Application: Claims
└── Owner: Claims-Team
```

---

# 11. Example Azure Structure

A complete example:

```text
Management Group
│
└── Insurance Organization
    │
    ├── Development Subscription
    │   │
    │   └── Resource Group: Claims-Dev-RG
    │       │
    │       ├── App Service
    │       ├── Azure SQL Database
    │       ├── Storage Account
    │       └── Application Insights
    │
    └── Production Subscription
        │
        └── Resource Group: Claims-Prod-RG
            │
            ├── App Service
            ├── Azure SQL Database
            ├── Storage Account
            └── Application Insights
```

This approach provides a clear separation between development and production environments.

---

# 12. Simple Explanation

You can think of the Azure hierarchy like this:

### Management Group

Used to organize multiple subscriptions.

### Subscription

Acts as a management and billing boundary.

### Resource Group

Used to organize related resources.

### Resource

The actual Azure service being used.

```text
Management Group
        ↓
Subscription
        ↓
Resource Group
        ↓
Azure Resource
```

Example:

```text
Production Management Group
        ↓
Production Subscription
        ↓
Claims-Application-RG
        ↓
Azure App Service
```

---

# 13. Key Takeaways

* Azure uses a hierarchy to organize resources.
* Management Groups can organize multiple subscriptions.
* Subscriptions provide management, access, and billing boundaries.
* Resource Groups logically organize related Azure resources.
* Resources are the actual Azure services created and used.
* RBAC permissions can be assigned at different levels of the hierarchy.
* Tags help organize and manage resources.
* A well-designed hierarchy helps with governance, security, cost management, and environment separation.

---

# 14. Interview Questions

## What is the Azure Resource Hierarchy?

The Azure Resource Hierarchy is:

```text
Management Groups
        ↓
Subscriptions
        ↓
Resource Groups
        ↓
Resources
```

It is used to organize and manage Azure resources, access, governance, and billing.

### What is an Azure Subscription?

An Azure Subscription is a logical boundary used for billing, access management, and resource management.

### What is a Resource Group?

A Resource Group is a logical container used to organize related Azure resources.

### Can a Resource Group contain multiple Azure resources?

Yes. A Resource Group can contain multiple related Azure resources, such as an App Service, SQL Database, Storage Account, and Application Insights resource.

### What happens if a Resource Group is deleted?

Deleting a Resource Group also deletes the resources contained within it. Therefore, this operation should be performed carefully.

### What is the difference between a Subscription and a Resource Group?

A Subscription acts as a management and billing boundary and can contain Resource Groups.

A Resource Group is used to logically organize related Azure resources.

### At which levels can Azure RBAC permissions be assigned?

Azure RBAC permissions can be assigned at different scopes, including:

* Management Group
* Subscription
* Resource Group
* Individual Resource

Permissions assigned at higher scopes can generally be inherited by resources at lower scopes.
