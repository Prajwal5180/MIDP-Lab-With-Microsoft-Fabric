# Analytics in the Microsoft Intelligent Data Platform Lab

## Overall Estimated Duration: 8 Hours

## Overview

This interactive lab begins with exploring an integrated Data Lakehouse foundation, focusing on data ingestion, transformation, and analytics using ADX, Synapse, Azure Databricks, and Microsoft Purview. It includes exercises for creating pipelines, combining data, and investigating ML and BI scenarios. Involves working with Microsoft Fabric, including creating a workspace, building a lakehouse, ingesting sample data, preparing and transforming data, and developing reports. This segment emphasizes hands-on experience with data handling and reporting in a Microsoft Fabric environment.

We have arranged this lab into two parts to provide a comprehensive understanding of the Microsoft Intelligent Data Platform. The first emphasizes building and leveraging Microsoft Fabric for advanced data analytics and reporting, and the second focuses on implementing an integrated Data Lakehouse foundation

## Objective

### Lab 1 : Analytics in the Microsoft Intelligent Data Platform Lab

Understand to leverage the Microsoft Intelligent Data Platform to unify data estates and accelerate data value creation through an open and governed Data Lakehouse foundation. By the end of the lab, you will gain insights on :

- **Data ingestion from a spectrum of analytical and operational data sources into the Lakehouse** : Learn to implement data ingestion pipelines using ADX for streaming data and Synapse pipelines to ingest raw data from analytical and operational sources into the Bronze layer of the Data Lake.
- **Explore offline data and analytics pipeline using open Delta format and Azure Databricks Delta Live Tables. Stitch streaming and non-streaming data (landed earlier) to create a combined data product to build a simple Lakehouse** : Learn to use the open Delta format and Azure Databricks Delta Live Tables for offline data and analytics pipelines.
- **Explore Machine Learning and Business Intelligence scenarios on the Lakehouse** : Learn to explore ML and BI scenarios on the Lakehouse using Azure Databricks MLflow, Power BI, and SQL Analytics with Azure Synapse Serverless and Databricks.
- **Glimpse of Purview to govern the overall data and analytics estate** : Learn how the Purview governs the entire data and analytics estate, ensuring comprehensive data management and compliance

### Lab 2 : Lakehouse end-to-end scenario

Gain knowledge on creating and managing a unified data lakehouse with Microsoft Fabric, covering data ingestion, transformation, and reporting. By the end of this lab, you will learn : 

- **Create a Fabric workspace** : Learn to create and set up a Fabric workspace, including understanding prerequisites and executing the workspace creation process.
- **Build a lakehouse** : Learn to build a lakehouse by activating SharePoint Online, creating the lakehouse, ingesting sample data, and building a report.
- **Ingest data into the lakehous** : Gain knowledge on ingesting data into the lakehouse, focusing on the efficient and effective methods for data integration. 
- **Prepare and transform data in the lakehouse** : Prepare and transform data within the lakehouse, focusing on data preparation techniques to ensure high-quality, actionable insights. This exercise covers essential practices for effective data transformation.
- **Building reports in Microsoft Fabric** : Create and build reports in Microsoft Fabric, focusing on leveraging the platform's capabilities to generate actionable insights. This exercise involves designing and developing comprehensive reports.

## Pre-requisites

- **Basic Understanding of Data Architecture**: Familiarity with data lakehouse and data warehouse concepts.

- **Microsoft Fabric Knowledge**: Basic knowledge of Microsoft Fabric and its components, including data integration, data engineering, and analytics services.

## Architecture

In this lab, the architecture covers two main aspects: first, it explores an integrated Data Lakehouse foundation using ADX, Synapse, and Azure Databricks for efficient data ingestion, transformation, and analytics, supporting ML and BI scenarios with governance by Microsoft Purview. Secondly, it delves into building and managing a unified data lakehouse with Microsoft Fabric, which includes creating a workspace, ingesting and preparing data, and leveraging Delta Lake for streamlined data processing and reporting through tools like Power BI.

## Architecture Diagram

![](../media/arch-new.png)

## Explanation of Components

- **Implementing a Lake First Data Foundation for Analytics** : Create a scalable, open Data Lakehouse for business intelligence, machine learning, and AI integration.

- **Implementing an Open and Governed Data Lakehouse** : Transform and prepare data in a unified Data Lakehouse for efficient BI, ML, and AI application.

- **Machine Learning and Data Analysis in the Microsoft Intelligent Data Platform** : Perform ML and interactive data analysis using tools like Synapse SQL and Azure Databricks notebooks.

- **Business Intelligence in the Microsoft Intelligent Data Platform** : Utilize integrated tools for self-serve business intelligence and effective data insights.

- **Data Governance in the Microsoft Intelligent Data Platform** : Manage and govern data seamlessly with Microsoft Purview across the entire analytics estate.

- **Data sources** : Fabric makes it quick and easy to connect to Azure Data Services, as well as other cloud-based platforms and on-premises data sources, for streamlined data ingestion.

- **Ingestion** : You can quickly build insights for your organization using more than 200 native connectors. These connectors are integrated into the Fabric pipeline and utilize the user-friendly drag-and-drop data transformation with dataflow. Additionally, with the Shortcut feature in Fabric, you can connect to existing data, without having to copy or move it.

- **Transform and store** : Fabric standardizes on Delta Lake format. This means all the Fabric engines can access and manipulate the same dataset stored in OneLake without duplicating data. This storage system provides the flexibility to build lakehouses using a medallion architecture or a data mesh, depending on your organizational requirements. You can choose between a low-code or no-code experience for data transformation, utilizing either pipelines/dataflows or notebook/Spark for a code-first experience.

- **Consume** : Power BI can consume data from the Lakehouse for reporting and visualization. Each Lakehouse has a built-in TDS/SQL endpoint, for easy connectivity and querying of data in the Lakehouse tables from other reporting tools. Additionally, when a Lakehouse is created, a corresponding secondary item called a Warehouse is automatically generated with the same name as the Lakehouse. It provides users with the TDS/SQL endpoint functionality.

## Getting Started with Lab

**Note:** We recommend having strong internet connectivity while performing the lab. Please ensure you are not connected to a VPN as this can slow down the lab-user experience.

1. When the environment is provisioned, a virtual machine (JumpVM) and lab guide will be loaded in your browser. Use this virtual machine to perform the lab.

   ![01](../media/01/01.png?raw=true)

2. To receive lab environment details, select the **Environment Details** tab. Additionally, the credentials will be sent to the email address you provided at registration.

   **Note:** If you see the pop-up **experience.cloudlabs.ai would like to access the Clipboard to copy text**, please click on **Allow**.

   ![02](../media/01/02.png?raw=true)

3. You can also open the Lab Guide in a separate window by selecting the **Split Window** icon in the bottom right corner.

   ![03](../media/01/03.png?raw=true)

----

### Known Issues

1. If you run into an issue where a file starts downloading (eg. file.html) in the VM or get stuck in between, refresh your browser and continue performing the lab:

   ![04](../media/01/04.png?raw=true)

2. If you come across the message: **RDP Gateway is in Running state. Please refresh after 1 or 2 minutes**. Please wait for 2 minutes and then navigate to **Resources Tab**, and click on the **Refresh button**:

   ![05](../media/01/05.png?raw=true)

   **Note:** If you are not using the environment, pause the VM by navigating to the **Resources Tab** and de-allocate it.

   ![06](../media/01/06.png?raw=true)

1. If you wish to start the environment or resume the lab, navigate to the **Resources Tab** and start it (It may take up to 5 minutes for the VM to be up and running).

     ![07](../media/01/07.png?raw=true)
   
   **Note:** If you are unable to proceed with the lab execution, here are the links to the click-by-click version of the lab to continue.   

   [click-by-click without story](https://content.cloudguides.com/guides/Analytics%20in%20MIDP%20-%20Interactive%20Experience)

   [click-by-click with story](https://content.cloudguides.com/guides/Analytics%20in%20MIDP%20-%20Interactive%20Experience%20with%20a%20story)


## Login to Azure Portal

1. In the JumpVM, click on the Azure portal shortcut of the Microsoft Edge browser which is created on the desktop.

   ![08](../media/01/08.png?raw=true)

2. When you click on Azure portal, the edge browser will ask you to sign in to sync data, click on **Start without your data**.

   ![09](../media/01/09.png?raw=true)

3. On the next window, click on **Continue without this data**.

   ![10](../media/01/10.png?raw=true)

4. On the next window, click on **Confirm and start browsing**.

   ![11](../media/01/11.png?raw=true)

5. Now, you will see three tabs in the Edge browser, close the tab named **Welcome to Microsoft Edge** and the other tab named **Welcome**.

6. On the **Sign in to Microsoft Azure** window, you will see the login screen. Enter the following username and click on **Next**.

   * Email/Username: <inject key="AzureAdUserEmail"></inject>

      ![12](../media/01/12.png?raw=true)

7. Now enter the following password and click on **Sign in**.

   * Password: <inject key="AzureAdUserPassword"></inject>

      ![13](../media/01/13.png?raw=true)

8. First-time users are often prompted to **Stay Signed In**, if you see this pop-up, click on **Yes**.


9. If you see the pop-up **Action Required**, keep default and then click on **Ask later**. If you see the pop-up **Help us protect your account**, click on **Skip for now(14 days until this is required)**, and then click on **Next**.

   ![14](../media/01/14.png?raw=true)

   >**Note:** You may see this pop-up multiple times, please proceed to **Skip**

11. If you see the pop-up **You have free Azure Advisor recommendations!**, close the window to continue the lab.

12. If a **Welcome to Microsoft Azure** popup window appears, click **Maybe Later** to skip the tour.

13. In the search results pane, select **Resource groups**.

    ![15](../media/01/15.png?raw=true)

14. On the **Resource groups** page, you can view the pre-deployed resource group **analyticsSolution**.

    ![16](../media/01/16.png?raw=true)

15. After completing each exercise, you have the option to validate it. Simply click on **Lab Validation** and initiate the validation process for the specific task; however, it's important to note that lab validations are not mandatory.
    
    ![](../media/01/validate.png)
 
16. Click Next from the bottom right corner to embark on your Lab journey!

Now you're all set to explore the powerful world of technology. Feel free to reach out if you have any questions along the way. Enjoy your workshop!

## Support Contact

The CloudLabs support team is available 24/7, 365 days a year, via email and live chat to ensure seamless assistance at any time. We offer dedicated support channels tailored specifically for both learners and instructors, ensuring that all your needs are promptly and efficiently addressed.

Learner Support Contacts:

- Email Support: labs-support@spektrasystems.com
- Live Chat Support: https://cloudlabs.ai/labs-support

## Happy Learning!!
