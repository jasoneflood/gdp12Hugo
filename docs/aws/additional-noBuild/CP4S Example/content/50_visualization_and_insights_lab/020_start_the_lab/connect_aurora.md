---
title: "2. Connect to AWS Aurora Postgres DB"
weight: 25
chapter: true
draft: false
---

1. From the Cognos Analytics welcome screen, go to **Menu** and click on **Manage**.

![data-server-connections](/static/images/40_visualization_and_insights_lab/data-server-connections.png?classes=shadow)

2. click on **Data Server Connections** to create a new DB connection as shown below.

![data-server-connections-button](/static/images/40_visualization_and_insights_lab/data-server-connections-button.png?classes=shadow)

3. Now, click on Data server **+** icon for the new Data Server connection.

![data-server](/static/images/40_visualization_and_insights_lab/data-server.png?classes=shadow)

4. Select a type as **PostgreSQL** database as shown below.

![postgresql](/static/images/40_visualization_and_insights_lab/postgresql.png?classes=shadow)

5. Edit the JDBC details and add the **HostName (Postgres endpoint url), Port and DatabaseName**, and  select the radio button **Use the following signo** under **Authentication method** and click on **+** as shown below.

![postgresql-jdbc-credentials](/static/images/40_visualization_and_insights_lab/postgresql-jdbc-credentials.png?classes=shadow)

6. Now fill in your AWS Aurora Postgres DB credentials - User ID and Password, as shown below. Click on **Test** and **Save**.

![postgresql-login-credentials](/static/images/40_visualization_and_insights_lab/postgresql-login-credentials.png?classes=shadow)

> **Note: Load the metadata for public schema and then save the connection.**
![load-metadata](/static/images/40_visualization_and_insights_lab/load_metadata_cognos.png?classes=shadow)
