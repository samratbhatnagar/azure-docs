---
title: Migrate your on-premises datacenter to Azure | Microsoft Docs
description: Provides an overview of the migration strategy used by Contoso to migrate their on-premises datacenter to Azure.
services: azure-migrate
author: rayne-wiselman
ms.service: azure-migrate
ms.topic: conceptual
ms.date: 05/30/2018
ms.author: raynew

---
# Contoso migration: Overview


This is the first article in a series that shows how the fictitious organization Contoso are moving their on-premises infrastructure to the Azure cloud. 

The article series is intended to provide sample example deployments that help you to understand options for migration to Azure and working in a hybrid environment, and to try out different migration scenarios. Articles are geared to Contoso requirements, but pointers for general reading and specific instructions are provided throughout.

## Introduction

Microsoft Azure provides access to a comprehensive set of cloud services that, as developers and IT professionals, you use to build, deploy, and manage applications on a range of tools and frameworks, through a global network of datacenters. As your business faces challenges associated with the digital shift, the Azure cloud helps you to figure out how to optimize resources and operations, engage with your customers and employees, and transform your products.

However, Azure recognizes that even with all the advantages that the cloud provides in terms of speed and flexibility, minimized costs, performance, and reliability, many organizations are going to need to run on-premises datacenters for some time to come. In response to cloud adoption barriers, Azure provides a hybrid cloud strategy that builds bridges between your on-premises datacenters, and the Azure public cloud. For example, using Azure cloud resources like backup to protect on-premises resources, or using Azure analytics to gain insights into on-premises workloads. 

As part of our hybrid cloud strategy, Azure provides growing solutions for migrating on-premises apps and workloads to the cloud. With simple steps, you can comprehensively assess your on-premises resources to figure out how they'll run in the Azure cloud. Then, with a deep assessment in hand, you can confidently migrate resources to Azure. When resources are up and running in Azure, you can optimize them to retain and improve access, flexibility, security, and reliability.

## Migration strategies

As we delve into strategies for migration to the cloud, they fall into four broad categories: rehost, refactor, rearchitect, and rebuild. The strategy you adopt will depend upon your business drivers, and migration goals. You might adopt multiple strategies. For example, you could choose to rehost (lift-and-shift) apps that aren't critical to your business, but rearchitect those that are more complex and business-critical. Let's look at the strategies.


**Strategy** | **Definition** | **When to use** 
--- | --- | --- 
**Rehost** | Often referred to as a "lift-and-shift" migration. This option doesn't require code changes, and let's you migrate your existing apps to Azure quickly. Each app is migrated as is, to reap the benefits of the cloud, without the risk and cost associated with code changes. | Use when you need to move apps quickly to the cloud<br/><br/> When you want to move an app without modifying it.<br/><br/> When your apps are architected in a way that they can leverage Azure IaaS scalability after migration.<br/><br/> When you need the apps but don't need to make any immediate changes to app capabilities.<br/><br/> When your app requirements can be met using an Azure IaaS VM.
**Refactor** | Often referred to as “repackaging,” this cloud migration option requires minimal changes to apps, so that they can take advantage of cloud offerings, and connect to Azure PaaS.  For example, you could migrate existing apps to Azure App Service or Azure Kubernetes Service (AKS), or refactor relational and non-relational databases into Azure options such as Azure SQL Database Managed Instance, Azure Database for MySQL, Azure Database for PostgreSQL, and Azure Cosmos DB. | Use this option if your app can be repackaged easier to work in Azure. This option an also be used if you want to apply innovative DevOpts practices provided by Azure, or you're considering investing in DevOps using a container strategy for workloads.<br/><br/> You will need to think about the portability of your existing code basis, and the development skills you need for this option.
**Rearchitect** | Rearchitect during migration is about both modifying and extending app functionality and code base to optimize the app architecture for cloud scalability. For example, you could break down a monolithic application into a group of microservices that work together and scale easiy. In addition you could rearchitect your relational and non-relational databases to Azure fully-managed DBaaS solutions, such as Azure SQL Database Managed Instance, Azure Database for MySQL, Azure Database for PostgreSQL, and Azure Cosmos DB. | Use this option when your apps need major revisions to incorporate new capabilities, or to work effectively on a cloud platform.<br/><br/> Rearchitecture is an option when you want to make use of existing application investments, meet scalability requirements in a cost-effective way, apply innovative DevOps practices provided by Azure, and minimize use of virtual machines.
**Rebuild** | Takes things a step further by rebuilding an app from scratch using Azure cloud technologies. For example, you could build greenfield applications with cloud-native technologies like serverless, Azure AI, Azure SQL Database Managed Instance, Azure Cosmos DB, and others. | Use when you want rapid development, and the existing apps has limited functionality and lifespan. Rearchitect when you ready to expedite business innovation (including DevOps pratices provided by Azure), build new applications using cloud-native technologies, and take advantage of advancements in AI, blockchain, and IoT.

## Migration articles

The articles summarized in the table use the fictional Contoso company, and describe a number of migration scenarios that Contoso could implement, using the same applications. 

- The scenarios are of increasing complexity, and we're adding to them over time.
- For each scenario, summarized in the table below, we provide business drivers & goals, proposed architecture, information about the migration process, steps to prepare Azure and perform migration, and post migration steps to show you how to clean up and what to do next.

**Article** | **Details** | **Status**
--- | --- | ---
1. Overview (this article) | Provides an overview of Contoso's migration strategy, and the sample articles | Live
2. [Deploy an Azure infrastructure](contoso-migration-infrastructure.md) | This articles describes how Contoso prepares its infrastructure for Azure migration. The infrastructure will be used for all Contoso migration scenarios. | Live
3. [Assess on-premises resources](contoso-migration-assessment) | In this article, Contoso ran an assessment of resources running a on-premises SmartHotel app. They assessed VMs running the app with the Azure Migrate service, and the assessed the app's SQL Server database with the Azure Database Migration Assistant. 
4. [Refactor: Lift and shift to Azure VMs and a SQL Managed Instance](contoso-migration-rehost-vm-sql-managed-instance.md) | In this article Contoso migrated their SmartHotel app using Site Recovery to migrate the Web frontend VM, and the Database Migration service to migrate the app database to a SQL Managed Instance.
5. [Refactor: Lift and shift to Azure VMs](contoso-migration-rehost-vm.md) | In this article Contoso migrated their SmartHotel app VMs using Site Recovery only.
6. Refactor: Lift and shift to Azure VMs and SQL Server Availability Groups** | In this article Contoso migrated their SmartHotel app using Site Recovery to migrate the Web frontend VM, and the Database Migration service to migrate the app database to A SQL Server Availability Group.


### Demo apps

- The articles use two demo apps - SmartHotel360, and osTicket.
    - SmartHotel: This app was developed by Microsoft as a test app that you can use when working with Azure. You can download it from [GitHub](https://github.com/Microsoft/SmartHotel360).
    - osTicket is an open-source service desk ticketing app that runs on Linux, Apache, PHP, and MySQL (LAMP), and can be downloaded from [GitHub](https://github.com/osTicket/osTicket).
    - The source code and a sample development project for SmartHotel360 will be migrated to Visual Studio Team Services.

**App** | **Rehost* | **Refactor** | **Rearchitect** | **Rebuild** 
--- | --- | --- | --- | ---
SmartHotel360 | 1-SmartHotel360-assessment-iaas-sqlvml<br/><br/>1-SmartHotel360-iaas-sqlvml<br/><br/>2-SmartHotel360-iaas-iaas<br/><br/>3-SmartHotel360-iaas-aog | 1-SmartHotel360-ci-sqldb | 1-smarthotel-service-fabric-func-cosmos-sqldb | 1-smarthotel-appservice-func-cosmos
osTicket | 4-osticket-iaas-iaas<br/><br/> 5-osticket-iaas-mysqldb | 2-osticket-appservices-mysqldb | | 
TFS | | 3-dev-test-tfs-vsts | | 


## Next steps

Learn how Contoso  [deploy an Azure infrastructure](contoso-migration-infrastructure.md)



