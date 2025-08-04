---
title: "Generating data"
weight: 2
---

# IBM Guardium 12– Generating data

As already mentioned this workshop leverages an opensource tool called Scenario Launch Platform (SLP) to generate events that GDP detects. You can read more about SLP here: [https://github.com/IBM/CyberSkill/tree/main/ScenarioLaunchPlatform].  

Lets start by visiting the SLP tool [SLP_URL]

![setup](/static/images/part2/slp_login.png)  

The username is admin  
The password is slp.trial!

## Generate a simple data event

SLP is a fully integrated database traffic toolkit, we have set up SLP with connections to the DB2 community edition deployed in this workshop. Once we log into SLP you are on the dashboard.
### Step 1

![setup](/static/images/part2/slp_dashboard.png) 

### Step 2
Now we verify connections to the datatabase, you do this by clicking on the gears on the top nav. You will see there are 4 users connected. These users are Polly, Liher, Jason and John. You can also see the permissions the users are set up with. This matters becauses some users don't have access to run certain database commands. So by pivoting between SLP users you can generate different events that GDP detects.

![setup](/static/images/part2/slp_connections.png) 

### Step 3
Once you have confirmed the connections are present. You do this by verifying the word connected appears beside each connection.  We can then move on to select a query to run by clicking the database icon on the top nav.

![setup](/static/images/part2/slp_queries.png) 

### Step 4
Select the first query that appears on this list. SLP is configured with queries that will run against DB2 community edition of this workshop, we are going to alter this query for the purpose of this test.

![setup](/static/images/part2/slp_databaseQuery.png) 

### Step 5
Now we edit this query so that it generates a database exception. 

![setup](/static/images/part2/slp_editQuery.png) 

### Step 6
Replace the text with the following, and hit run:   
INSERT INTO crm.tbl_crm_accounts (Idx) values ('a');

![setup](/static/images/part2/error_query.png) 

### Step 7
This will generate an error message.

![setup](/static/images/part2/sql_result.png) 

### Step 8
Now pat yourself on the back, we have generated an exception. We can now pivot to Guardium [GDP_URL] and verify it was picked up, by leveraging the exception count tile in GDP.

![setup](/static/images/part2/gdp_exceptionCount.png) 

You can generate exceptions of all kinds with the 4 users (Polly, Liher, John and Jason) set up in SLP and verify the number of exceptions detected increases.

![setup](/static/images/part2/gdp_Exception.png) 