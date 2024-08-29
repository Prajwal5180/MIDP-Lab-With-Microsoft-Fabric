# Analytics in the Microsoft Intelligent Data Platform Lab

## Overall Estimated Duration: 8 Hours

## Overview

Traditionally, organizations have been building modern data warehouses for their transactional and structured data analytics needs. And data lakehouses for big data (semi/unstructured) data analytics needs. These two systems ran in parallel, creating silos, data duplication, and increased total cost of ownership.

Microsoft Fabric is an all-in-one analytics solution for enterprises that covers everything from data movement to data science, real-time analytics, and business intelligence. It offers a comprehensive suite of services, including data lake, data engineering, and data integration, all in one place. Fabric with its unification of data store and standardization on Delta Lake format allows you to eliminate silos, remove data duplication, and drastically reduce the total cost of ownership.

With the flexibility offered by Fabric, you can implement either lakehouse or data warehouse architectures or combine them together to get the best of both with simple implementation. In this tutorial, you're going to take an example of a retail organization and build its lakehouse from start to finish. It uses the medallion architecture where the bronze layer has the raw data, the silver layer has the validated and deduplicated data, and the gold layer has highly refined data. You can take the same approach to implement a lakehouse for any organization from any industry.

## Lab Objectives

### Lakehouse end-to-end scenario

- **Create a Fabric workspace** : Learn to create and set up a Fabric workspace, including understanding prerequisites and executing the workspace creation process.
- **Build a lakehouse** : Learn to build a lakehouse by activating SharePoint Online, creating the lakehouse, ingesting sample data, and building a report.
- **Ingest data into the lakehous** : Gain knowledge on ingesting data into the lakehouse, focusing on the efficient and effective methods for data integration. 
- **Prepare and transform data in the lakehouse** : Prepare and transform data within the lakehouse, focusing on data preparation techniques to ensure high-quality, actionable insights. This exercise covers essential practices for effective data transformation.
- **Building reports in Microsoft Fabric** : Create and build reports in Microsoft Fabric, focusing on leveraging the platform's capabilities to generate actionable insights. This exercise involves designing and developing comprehensive reports.

## Architecture

   ![Lakehouse end-to-end architecture](../media/07/01.png)

The above image shows the lakehouse end-to-end architecture. The components involved are described in the following list:

- **Data sources:** Fabric makes it quick and easy to connect to Azure Data Services, as well as other cloud-based platforms and on-premises data sources, for streamlined data ingestion.

- **Ingestion:** You can quickly build insights for your organization using more than 200 native connectors. These connectors are integrated into the Fabric pipeline and utilize the user-friendly drag-and-drop data transformation with dataflow. Additionally, with the Shortcut feature in Fabric, you can connect to existing data, without having to copy or move it.

- **Transform and store:** Fabric standardizes on Delta Lake format. This means all the Fabric engines can access and manipulate the same dataset stored in OneLake without duplicating data. This storage system provides the flexibility to build lakehouses using a medallion architecture or a data mesh, depending on your organizational requirements. You can choose between a low-code or no-code experience for data transformation, utilizing either pipelines/dataflows or notebook/Spark for a code-first experience.

- **Consume:** Power BI can consume data from the Lakehouse for reporting and visualization. Each Lakehouse has a built-in TDS/SQL endpoint, for easy connectivity and querying of data in the Lakehouse tables from other reporting tools. Additionally, when a Lakehouse is created, a corresponding secondary item called a Warehouse is automatically generated with the same name as the Lakehouse. It provides users with the TDS/SQL endpoint functionality.

----

## Data and transformation flow

This lab uses **Wide World Importers (WWI) sample data** to build this end-to-end lakehouse lakehouse. In this implementation, the sample data is stored in an Azure Data storage account in Parquet file format for all the tables. However, in real-world scenarios, data would typically originate from various sources and in diverse formats.

The following image shows the source, destination and data transformation:

![data-transformation-flow](https://github.com/CloudLabsAI-Azure/MIDP-Lab-With-Microsoft-Fabric/blob/dev/media/07/02.png?raw=true)

- **Data source:** The source data is in Parquet file format and in an unpartitioned structure. It's stored in a folder for each table. In this tutorial, we set up a pipeline to ingest the complete historical or one-time data to the lakehouse.
- **Lakehouse:** In this lab, you create a lakehouse, ingest data into the files section of the lakehouse, and then create delta lake tables in the Tables section of the lakehouse.
- **Transform:** For data preparation and transformation, you see two different approaches. We demonstrate the use of Notebooks/Spark for users who prefer a code-first experience and use pipelines/dataflow for users who prefer a low-code or no-code experience.
- **Consume:** To demonstrate data consumption, you see how you can use the DirectLake feature of Power BI to create reports, and dashboards and directly query data from the lakehouse.

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
