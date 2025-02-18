# Exercise 1 : Data ingestion from a spectrum of analytical and operational data sources into the Lakehouse.

### Estimated Duration: 1 Hour

In this exercise, you'll learn to ingest data from various sources, including databases and event streams, into the Synapse Lakehouse for centralized storage and processing.

## Lab Objectives

In this lab, you will perform:

- **Task 1**: Explore a Streaming data and analytics pipeline using ADX for a near real time analytics scenario.


## Task 1: Explore a Streaming data and analytics pipeline using ADX for a near real time analytics scenario.

In this task, you will use ADX to explore thermostat data from the stores streamed in near real-time to an Azure Event Hub.

1. In the search results pane, select **Resource groups**.

    ![In the search results pane, select the Resource group](https://github.com/CloudLabsAI-Azure/Ignite-lab/blob/main/media/image1107.png?raw=true)

2. In the **Resource groups** page, in the filter box, enter: **analyticsSolution**.

3. In the filtered results, select the resource group that has a name starting with **analyticsSolution**.

    ![In the filtered results, select the resource group](https://github.com/CloudLabsAI-Azure/Ignite-lab/blob/main/media/image1109.png?raw=true)

4. In the resources filter box for resources, search for **app**.

5. In the filtered results, select the **App Service**.

    ![Select the app service](https://github.com/CloudLabsAI-Azure/Ignite-lab/blob/main/media/imageAppServices.png?raw=true)

6. Select **Browse** (on the top left). This action will start the data simulation required to execute this task successfully (this will take 3-5 mins).

   ![Select Browse](https://github.com/CloudLabsAI-Azure/Ignite-lab/blob/main/media/imageclickBrowse.png?raw=true)

And, this will take you to a webpage that will confirm **Data Simulation** has started:

   ![Data Simulation](https://github.com/CloudLabsAI-Azure/Ignite-lab/blob/main/media/datasimulation.png?raw=true)

7. Return to the Azure Portal session by selecting the resource group from the top navigation bar.

    ![Return to Azure Portal](https://github.com/CloudLabsAI-Azure/Ignite-lab/blob/main/media/returnToAzurePortal.png?raw=true)

8. In the resources filter box for resources, search for **Synapse**.

9. In the filtered results, select the **Azure Synapse resource**.

    ![In the filtered results, select the Azure Synapse resource](https://github.com/CloudLabsAI-Azure/Ignite-lab/blob/main/media/image1114.png?raw=true)

>**Note:** You might see a Synapse workspace resource name with a different suffix in your Azure Portal.

10. In the Open Synapse Studio tile, select the Open link.

     ![Open Synapse studio](https://github.com/CloudLabsAI-Azure/Ignite-lab/blob/main/media/image1115.png?raw=true)

>**Note:** Synapse Studio opens in a new web session (tab).

11. In Synapse Studio, on the left pane, select the **Data** hub icon.

12. In the **Data** pane, expand **Data Explorer Databases (Preview).**

13. Expand the **analyticspool<inject key="DeploymentId"></inject>** Data Explorer pool.

14. Select the **ellipses** (the three dots next to the data explorer pool).

>**Note:** If you do not see the ellipses, expand the Data pane by dragging it to the right. 

   ![Expand Data Explorer Pool](https://github.com/CloudLabsAI-Azure/Ignite-lab/blob/main/media/img114.png?raw=true)

15. Select **Open in Azure Data Explorer**.

*This will open Azure Data Explorer in a new web session (tab).*

   ![Open Azure Data Explorer](https://github.com/CloudLabsAI-Azure/Ignite-lab/blob/main/media/img115.png?raw=true)

*For this lab, an ADX pool has already been created in the Azure Synapse workspace.*

*By using ADX’s powerful Kusto Query Language (KQL), you can ensure that the thresholds you have set for each device in the store are being met.*

>**Note:** Other Azure services use KQL for analytical queries. These services include Azure Monitor logs, Application Insights, and Microsoft Defender for Endpoint.

>**Note:** Select **Dismiss** if any pop-up appears on your screen.
16. In Azure Data Explorer Studio, in the left pane, select the **Data** hub icon.

17. In the **Data Management** page, select the **Data** in the left navigation pane and select **Ingest data** action.

    ![Paste the URI into the address bar](https://github.com/CloudLabsAI-Azure/Ignite-lab/blob/main/media/image1127.png?raw=true)

18. In the **Destination** tab, in **Cluster** dropdown list, select the Data Explorer pool starting with **analyticspool<inject key="DeploymentId"></inject>**.
     
19. In the Database dropdown, select **AnalyticsDB**. Then in the **Table** textbox, enter/type **Thermostat**.

20. Click on **Next: Source.**

    ![Click Next](https://github.com/CloudLabsAI-Azure/Ignite-lab/blob/main/media/img119.png?raw=true)

21. In the **Source** tab, in the **Source** dropdown list, select **Event Hubs**.

22. In **Subscription** dropdown list, select the subscription given by default.

    ![Select Eventhub](https://github.com/CloudLabsAI-Azure/Ignite-lab/blob/main/media/01.png?raw=true)

23. In the **Event Hub namespace** dropdown list, select Event Hub that has a name starting with **adx-thermostat-occupancy-**.

24. In the **Event Hubs** dropdown list, select **thermostat**.

25. In **Data connection name** dropdown list, select **AnalyticsDB-thermostat**.

26. In the **Consumer group** dropdown list, select **$Default**.

27. Click on **Next: Schema**.

    ![Click Next](https://github.com/CloudLabsAI-Azure/Ignite-lab/blob/main/media/02.png?raw=true)

28. In the **Schema** tab, wait until the data preview loads (about 20 seconds).

29. Review the event data, which comprises thermostat measures from different devices.

30. In the **Data** format dropdown list, select **JSON.**

31. Click on **Next: Start ingestion.**

    ![Click Next](https://github.com/CloudLabsAI-Azure/Ignite-lab/blob/main/media/img132.png?raw=true)

32. Confirm that the continuous ingestion from Event Hub has been established, and then click on **Close** (located at the bottom of the page).

    ![Select Close](https://github.com/CloudLabsAI-Azure/Ignite-lab/blob/main/media/img133.png?raw=true)

33. Return to the Synapse Studio web session (tab).

34. In Synapse Studio, at the left, select the **Develop** hub icon (the third from the top).

35. In the **Develop** pane, expand **KQL scripts**.

36. Select the **ThermostatOccupancyScript** script.

    ![Select the ThermostatOccupancyScript Sript](https://github.com/CloudLabsAI-Azure/Ignite-lab/blob/main/media/image1148.png?raw=true)

37. In the **Connect to** dropdown list select the data explorer pool starting with **analyticspool-**.

    >**Note:** If you do not see this option, click on the ellipsis [...] next to Publish on the top bar.

    >**Note:** If required, collapse the panes on the left using the << icon at the top right of each pane.

38. In the **Use database** dropdown list, select **AnalyticsDB**.

39. Select the query (lines 4-8) that is commented as **What is the average temp every minute?**.

*The query retrieves the average temperature per minute for a thermostat device (TH005) for the Miami store.*

40. Select **Run**. 

41. In the **Results** pane (located along the bottom), review the query result expressed as a chart. Please note that it may take upto 2-3 minutes to accumulate data. If you do not see any result please re-run query after sometime. 

    >**Note:** If you dont see data in the query result, wait for few minutes and try again since the data will take a few minutes to start streaming. In case your query returns an error, chances are that the thermostat table was not created successfully in previous steps. You may have to create that table with a different name e.g. Thermostat1, update the KQL query accordingly and re-execute the KQL query.  

   ![Review the query result ](https://github.com/CloudLabsAI-Azure/Ignite-lab/blob/main/media/img_graph1.png?raw=true)

*Your graph may appear slightly different than the one shown above. It may take up to 60 seconds to load.*

42. Notice that the temperature in the Miami store is oscillating between 65 and 70 degrees Fahrenheit. Based on these insights, we are able to adjust the temperatures to optimal level.

## Summary

In this exercise, we set up a streaming data pipeline using Azure Data Explorer (ADX), ingested streaming data, and performed real-time analytics to gain immediate insights. This demonstrated efficient processing of high-volume data for time-sensitive scenarios.

### You have successfully completed this exercise.
