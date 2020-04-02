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
  

## Installing Grafana 

Grafana comes in two flavors: Alpine Linux-based and Ubuntu-based. In this tutorial, we will be using the Alpine version, which is recommended by the developers for safety and efficiency.
1. Open your preferred terminal and type:
```
docker ps
```
to make sure Docker is running. If you see errors, then launch Docker and try again. 

2. Next, type in
```
docker run -d -p 3000:3000 grafana/grafana
```
to install the latest stable Grafana version.
> You may need to use `sudo` in front of this command on a Linux system.

## Logging in
Open your preferred web browser and nagivate to [localhost:3000](http://localhost:3000/). 
(image)
Log in using **admin/admin** as login/password. After that, you will be prompted to change your password.
## Setting up the data source
After you log in, you will see the Grafana welcome screen. 
  * Click the Add Data Source button. 
  * Search for the `TestData DB` data source and select it. 
  * Make sure the `default` switch is on.
  * Click `Save&Test`.

## Creating a dashboard
Click `Create a dashboard`.
On the created dashboard, you will see a single panel.
### Creating a query
Click the `Add query` button. This will open the query and visualization editor.
In the `Scenario` menu, select `Streaming Client`. This will provide you with mock signal data which updates each 250 milliseconds by default.
  * The `Speed (ms)` field value indicates how often your data updates.
  * The drop-down menu on top contains different time intervals which can be applied to your visualization.

### Visualization
Finally, set up the visualization.
