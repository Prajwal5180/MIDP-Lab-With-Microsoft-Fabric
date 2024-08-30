# Get data into Fabric Lakehouse

## Overall Estimated Duration: 4 Hours 45 minutes

## Overview

In this hands-on lab, you will work through a comprehensive data processing and analytics flow. You'll begin by setting up the data source, which consists of Parquet files stored in an unpartitioned structure, with each table organized into its own folder. You will create a pipeline to ingest this historical or one-time data into a Lakehouse. Next, you'll create a Lakehouse, ingest the data into its files section, and then establish Delta Lake tables in the Tables section for structured storage. For data transformation, you will explore two approaches: using Notebooks with Spark for a code-first experience and utilizing pipelines or dataflows for a low-code or no-code experience. Finally, you'll learn how to consume this transformed data by leveraging the DirectLake feature of Power BI to create reports, dashboards, and directly query data from the Lakehouse. This hands-on experience will guide you through each step of managing, transforming, and visualizing data within a modern data architecture.

## Objective

Understand how to set up a Fabric workspace, build a lakehouse, ingest and transform data, and create reports. By the end of this lab, you will be able to:

- **Create a Fabric workspace** : Gain experience on creating and setting up a Fabric workspace, including understanding prerequisites and executing the workspace creation process.
- **Build a lakehouse** : Gain experience to build a lakehouse by activating SharePoint Online, creating the lakehouse, ingesting sample data, and building a report.
- **Ingest data into the lakehouse** : Gain knowledge on ingesting data into the lakehouse, focusing on the efficient and effective methods for data integration. 
- **Prepare and transform data in the lakehouse** : Gain experience to prepare and transform data within the lakehouse, focusing on data preparation techniques to ensure high-quality, actionable insights. This exercise covers essential practices for effective data transformation.
- **Building reports in Microsoft Fabric** : Gain experience to create and build reports in Microsoft Fabric, focusing on leveraging the platform's capabilities to generate actionable insights. This exercise involves designing and developing comprehensive reports.

## Pre-requisites

To effectively perform these exercises, you need basic knowledge of **Microsoft Azure**, **Microsoft Fabric**, **SharePoint Online**, and **data management principles**. Familiarity with creating and managing lakehouses, data ingestion, transformation, and reporting in Microsoft Fabric or Power BI is also required.

## Architecture

In this hands-on lab, you will work through the architecture flow illustrated in the diagram, focusing on data ingestion, transformation, storage, and consumption. You’ll start by connecting to various data sources, both structured and unstructured, and utilizing shortcuts or data pipelines to ingest this data into a Lakehouse. Once the data is ingested, you’ll transform it using notebooks and dataflows, ensuring it is optimized for analysis. The transformed data will be stored in the Lakehouse, a hybrid storage solution that supports both raw and structured data. Finally, you will connect to this data using tools like Power BI or SQL endpoints, enabling real-time reporting and visualization. Throughout the lab, you'll gain hands-on experience in managing and analyzing data end-to-end within this integrated architecture.

## Architecture Diagram

   ![Lakehouse end-to-end architecture](../media/07/01.png)

   ![data-transformation-flow](https://github.com/CloudLabsAI-Azure/MIDP-Lab-With-Microsoft-Fabric/blob/dev/media/07/02.png?raw=true)

## Explanation of Components

- **Microsoft Entra ID** : Microsoft Entra ID is a cloud-based identity and access management service that enables secure access to both external and internal resources. It allows users to seamlessly sign in to a wide range of applications, including Microsoft 365, the Azure portal, and other SaaS apps, as well as custom applications developed for an organization. By managing user identities and controlling access, Microsoft Entra ID enhances security and simplifies the user experience across various platforms and devices.

- **Microsoft Fabric** : Microsoft Fabric is a comprehensive analytics and data platform tailored for enterprises seeking an integrated solution. It covers all aspects of data management, including movement, processing, ingestion, transformation, real-time event routing, and reporting. The platform provides a full range of services, such as Data Engineering, Data Factory, Data Science, Real-Time Analytics, Data Warehousing, and Databases.

- **SharePoint Online** : SharePoint Online is a cloud-based service from Microsoft that facilitates collaboration, document management, and content sharing within organizations. It enables users to create, store, and manage web-based documents and data, offering tools for team sites, document libraries, and lists.

- **Fabric lakehouse** : Microsoft Fabric Lakehouse is a data architecture platform designed to store, manage, and analyze both structured and unstructured data in one unified location. It offers flexibility and scalability, enabling organizations to handle extensive data volumes through a range of tools and frameworks for processing and analysis. The platform integrates seamlessly with other data management and analytics tools, delivering a comprehensive solution for data engineering and analytics.

- **Power BI** : Power BI is a suite of software services, applications, and connectors that collaborate to transform disparate data sources into cohesive, visually engaging, and interactive insights. Whether your data comes from an Excel spreadsheet or a mix of cloud-based and on-premises data warehouses, Power BI enables you to seamlessly connect to these sources, uncover and visualize key information, and share insights with anyone you choose.

# Getting Started with the Lab
 
Once the environment is provisioned, a virtual machine (JumpVM) and lab guide will get loaded in your browser. Use this virtual machine throughout the workshop to perform the lab. You can see the number on the bottom of the Lab guide to switch to different exercises of the lab guide.
 
## Accessing Your Lab Environment
 
Once you're ready to dive in, your virtual machine and lab guide will be right at your fingertips within your web browser.
 
   ![01](../media/01/01.png?raw=true)

### Virtual Machine & Lab Guide
 
Your virtual machine is your workhorse throughout the workshop. The lab guide is your roadmap to success.
 
## Exploring Your Lab Resources
 
To get a better understanding of your lab resources and credentials, navigate to the **Environment** tab.
 
![Explore Lab Resources](../media/01/env.png?raw=true)
 
## Utilizing the Split Window Feature
 
For convenience, you can open the lab guide in a separate window by selecting the **Split Window** button from the top right corner.
 
![Use the Split Window Feature](../media/01/split.png?raw=true)
 
## Managing Your Virtual Machine
 
Feel free to start, stop, or restart your virtual machine as needed from the **Resources** tab. Your experience is in your hands!
 
![Manage Your Virtual Machine](../media/01/resourses.png?raw=true)

## **Lab Duration Extension**

1. To extend the duration of the lab, kindly click the **Hourglass** icon in the top right corner of the lab environment. 

    ![Manage Your Virtual Machine](../media/01/gext.png?raw=true)

    >**Note:** You will get the **Hourglass** icon when 10 minutes are remaining in the lab.

2. Click **OK** to extend your lab duration.
 
   ![Manage Your Virtual Machine](../media/01/gext2.png?raw=true)

3. If you have not extended the duration prior to when the lab is about to end, a pop-up will appear, giving you the option to extend. Click **OK** to proceed.
 
## Let's Get Started with Azure Portal
 
1. On your virtual machine, click on the Azure Portal icon as shown below:
 
    ![Launch Azure Portal](../media/01/azure.png?raw=true)
 
2. You'll see the **Sign into Microsoft Azure** tab. Here, enter your credentials:
 
   - **Email/Username:** <inject key="AzureAdUserEmail"></inject>
 
      ![](../media/01/image7.png?raw=true)
 
3. Next, provide your password:
 
   - **Password:** <inject key="AzureAdUserPassword"></inject>
 
      ![](../media/01/image8.png?raw=true)

1. If you see the pop-up **Action Required**, click **Ask Later**.
   
     ![](../media/01/asklater.png?raw=true)

1. First-time users are often prompted to Stay Signed In, if you see any such pop-up, click on No.

1. If a **Welcome to Microsoft Azure** popup window appears, click **Cancel** to skip the tour.
    
     ![](../media/01/gettingstarted-new-2.png?raw=true)

1. Click **Next** from the bottom right corner to embark on your Lab journey!
 
    ![Start Your Azure Journey](../media/01/num.png?raw=true)

In this hands-on lab, you'll learn to set up a **Fabric workspace**, **build a lakehouse** , **ingest and transform data**, and **create reports**. The lab covers workspace creation, data integration, preparation techniques, and report development using Microsoft Fabric.

### Known Issues

1. If you run into an issue where a file starts downloading (eg. file.html) in the VM or get stuck in between, refresh your browser and continue performing the lab:

   ![04](../media/01/04.png?raw=true)
 
1. Click Next from the bottom right corner to embark on your Lab journey!

Now you're all set to explore the powerful world of technology. Feel free to reach out if you have any questions along the way. Enjoy your workshop!

## Support Contact

The CloudLabs support team is available 24/7, 365 days a year, via email and live chat to ensure seamless assistance at any time. We offer dedicated support channels tailored specifically for both learners and instructors, ensuring that all your needs are promptly and efficiently addressed.

Learner Support Contacts:

- Email Support: labs-support@spektrasystems.com
- Live Chat Support: https://cloudlabs.ai/labs-support

## Happy Learning!!
