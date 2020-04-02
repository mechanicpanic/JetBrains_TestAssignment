# Get started with Grafana: Hands-on Tutorial 
[Grafana](https://grafana.com/) is a powerful tool for data analytics and interactive visualization. It makes exploring and tracking metrics easy, no matter where and how they are stored. 

In this walkthrough, you will get a hands-on start to Grafana. 
You will create your first dashboard and visualize a mock signal after installing Grafana's latest Docker image.  

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

Grafana comes in two flavors: Alpine Linux-based and Ubuntu-based. In this tutorial, we will be using the Alpine version, which is recommended by the developers for safety and efficiency.
1. Open any kind of terminal and type:
```
docker ps
```
to make sure Docker is running. If you see errors, then launch Docker and try again. 

2. Next, type in
```
docker run -d -p 3000:3000 grafana/grafana
```
to install the latest stable Grafana version.
> *You may need to use `sudo` in front of this command on a Linux system.*

## Logging in
  * Open a web browser and nagivate to [localhost:3000](http://localhost:3000/). 
  * Log in using **admin/admin** as your login and password.
  * Change your password when prompted. Type in your new password twice and click **Proceed**.

## Data source
After you log in, you will see the Grafana welcome screen.

<a href="url"><img src="https://github.com/mechanicpanic/JetBrains_TestAssignment/blob/master/welcome.PNG" height="400"></a>

The sidebar on the left the main means of navigation in Grafana. 
  * In the Configuration menu (cog icon), click the `Add Data Source` button. 
  * Search for the `TestData DB` data source and select it. 
  * Make sure the `default` switch is on.
  * Click `Save&Test`.

## Creating a dashboard
Click `Create a dashboard`.
On the created dashboard, you will see a panel with two buttons.
(image)
### Setting up a panel
#### Add a query
Click the `Add query` button. This will open the query and visualization editor.
(image)
By default, you will be presented with a graph visualization of static data.
In the `Scenario` menu, select `Streaming Client`. This will provide you with mock signal data that updates once each 250 milliseconds.
  * The time picker menu on the top right contains the time interval displayed. 
  * The `Speed (ms)` field value indicates how often your data updates.
  (images)
#### Set up visualization
Click the graph icon on the left. (image)
This will let you edit your visualization's appearance.
##### A readable legend
  * Switch on the `As Table`, `To your right`, `Min`, and `Max` switches in the **Legend** section.
##### 
