---
title: "3. Connect to Data virtualization data source"
weight: 35
chapter: true
draft: false
---

::alert[NOTE: This step is similar to step 2 in terms of procedure.]

1. To fetch Data Virtualization(DV) credentials, open DV instance from CP4D console and see for connection details. See below screenshot for reference.
![dv-creds](/static/images/40_visualization_and_insights_lab/dv-creds.png?classes=shadow)

> Note: We need In-Cluster hostname, to fetch that information click on Choose resource and select In-Cluster hostname, and click on Apply.
![dv-creds-2](/static/images/40_visualization_and_insights_lab/dv-creds-2.png?classes=shadow)

2. From the Cognos Analytics welcome screen, go to **Manage** and click on **Data Server Connections** to create a new DB connection.

3. Now, click on Data server **+** icon for the new Data Server connection.

4. Select a type as **BIGSQL** database. 

![DatabaseType-BIGSQL](/static/images/40_visualization_and_insights_lab/DatabaseType_BIGSQL.png?classes=shadow)

::alert[Note: You should choose Database type as **BIGSQL**, since we are using CPD 4.5. For older versions of CPD, you should choose **IBM db2**.]

5. Edit the JDBC details and add the **HostName (CP4D url), Port and DatabaseName**, (which we have already gathered from the above step) and select the radio button Use the following signon under **Authentication method** and click on **+**.

6. Fill in your DV credentials - User ID and Password. Click on **Test** and **Save**.

7. Load the metadata under schemas as shown in the below screenshot.

![dv-ss](/static/images/40_visualization_and_insights_lab/dv-ss.png)

::alert[Note: Click on **Load options**, select only one table **joined_view** and click on the **Load** button.]

8. After you add the data virtualization data source, you should be able to create widgets similar to the above steps. See the below widget for your reference which will help to create a similar one.
