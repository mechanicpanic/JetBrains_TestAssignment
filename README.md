# Get started with Grafana: Hands-on Tutorial 
[Grafana](https://grafana.com/) is a powerful tool for data analytics and interactive visualization. It makes exploring and tracking metrics easy, no matter where and how they are stored. 

In this walkthrough, you will get a hands-on start to Grafana. 
You will create your first dashboard and visualize a heatmap after installing Grafana's latest Docker image.  

## Before you start
### You will need
  * [Docker](https://docs.docker.com/install/)
  * [A supported platform](https://grafana.com/docs/grafana/latest/installation/requirements/#supported-operating-systems)
  * [A supported web browser](https://grafana.com/docs/grafana/latest/installation/requirements/#supported-web-browsers) with JavaScript enabled
  * At least 255 MB of RAM
  
## [Grafana building blocks](https://grafana.com/docs/grafana/latest/guides/glossary/)
  * A **panel** is the basic visual element of Grafana comprised of a visualization and at least one query.  
  * A **dashboard** is a set of panels. 
  * A **data source** is a file, database, or service providing the data.
  * A **visualization** is a graphical representation of query results.
  

## Installing Grafana 

Grafana images come in two flavors: Alpine Linux-based and Ubuntu-based. In this tutorial, we will be using the Alpine version, which is recommended for safety and efficiency.
  * Open any kind of terminal and type:
  
  ``` 
  docker ps 
  ```
  
  to make sure Docker is running. If you see errors, then launch Docker and try again. 

  * Next, type in
  
  ``` 
  docker run -d -p 3000:3000 grafana/grafana 
  ```
  to install the latest stable Grafana version.
  > *You may need to use* `sudo` *in front of this command on a Linux system.*

## Logging in
  * Open a web browser and nagivate to [localhost:3000](http://localhost:3000/). 
  * Log in using **admin/admin** as your login and password.
  * When prompted, type in your new password and click **Save**.

## Data source
After you log in, you will see the Grafana welcome screen.

<a href="url"><img src="https://github.com/mechanicpanic/JetBrains_TestAssignment/blob/master/welcome.PNG" width="500" alt="Welcome screen"></a>

The sidebar on the left is the main means of navigation in Grafana. 
  * In the **Configuration** menu (gear icon), click the **Add Data Source** button. 
  * Search for the **TestData DB** data source and select it. 
  * Make sure the **Default** switch is on.
  * Click **Save&Test**.

## Creating a dashboard
Click **Create a dashboard**.
This dashboard will contain a single new panel. 

<a href="url"><img src="https://github.com/mechanicpanic/JetBrains_TestAssignment/blob/master/panel.png" width="500" alt="Panel"></a>
### Create a query
  * Click the **Add query** button. This will open the Query editor.
  
  <a href="url"><img src="https://github.com/mechanicpanic/JetBrains_TestAssignment/blob/master/editor.png" width="500" alt="Query editor"></a>
  
  * In the **Scenario** menu, select **Linear heatmap bucket data**.
     * This scenario will emulate a query returning histogram data for evenly spaced time slices. 
  *  Select the displayed time interval in the drop down menu on the top right.
  
 <a href="url"><img src="https://github.com/mechanicpanic/JetBrains_TestAssignment/blob/master/hm_graph.png" width="550"></a>  
Clearly, the graph does not make a lot of sense for this type of data. Let's visualize it in a more sensible way.

### Visualize the data

  * On the left, click the graph icon. 
  * Open the drop-down **Visualization** menu and select **Heatmap**.
  * **Y Axis & Data format**
    * Select *Time series buckets* for the **Format** property. (The data in this scenario has already been aggregated. This will render the heatmap correctly.)
    * Select *Middle* for the **Bucket bound** property.
 * **Display**
    * Switch on **Show legend**.
    * Switch on **Show tooltip** and **Histogram**.
    * If you choose the **spectrum** color mode, the heatmap will be colored with a gradient.
    * If you choose the **opacity** color mode, the heatmap will be monochrome. Different values will be displayed by different opacity levels. 
## Name & save your dashboard
  * Click the return arrow on the top left to open your dashboard again.
  * Click the save icon on the top right.
  * Name your dashboard **Test**.
  * Click **Save**.
  
Congratulations! You have just created your first dashboard in Grafana. 
As a next step, you can organize a set of panels with different scenarios and visualizations on your dashboard. There are also several links below if you have any questions left.
## Useful links
  * [What is Docker?](https://www.ibm.com/cloud/learn/docker)
  * [Grafana heatmaps](https://grafana.com/docs/grafana/latest/features/panels/heatmap/) 
  * [Grafana panel features](https://grafana.com/docs/grafana/latest/features/panels/panels/)
  * [Grafana dashboard features](https://grafana.com/docs/grafana/latest/features/dashboard/dashboards/)
