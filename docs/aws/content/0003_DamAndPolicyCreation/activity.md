---
title: "Activity"
weight: 2
---

# IBM Guardium Data Protection – Basic DAM operations


In this section we will explore some basic DAM capabilities. To do this we must first generate some traffic. We visit SLP and login.
![setup](/static/images/part3/1.png)  
username: admin  
password: slp.trial!



Once logged in click on the story book icon in the top nav section.
![setup](/static/images/part3/2.png)  
The story book mode is a feature that allows different users to perform database operations in sequence.

The SLP deployed in this workshop has 4 stories pre defined.
![setup](/static/images/part3/3.png)  

Run each story in turn. You do this by clicking on the run button. 

When a story runs it will open a pop up and start to execute. You can see the user that is executing the command,and how many chapters are going to run. Leave the window open until the number of chapters described in the heading of the new window have completed. You can then close the window and proceed to the next story. Repeat this until all stories are complete.
![setup](/static/images/part3/4.png)  

If you want to know the commands that each user is calling you can click the query button that is associated with each story chapter.

![setup](/static/images/part3/5.png) 

Each Story has a different number of chapters. 
 
![setup](/static/images/part3/6.png)  

We have now successfully generated traffic and we can now visit Guardium DAM reports to see what has been generated. We do this by clicking on My Custom Dashboards, [DAM] Activity Reports.

![setup](/static/images/part3/7.png)  

When the report opens we can see the DDL activitiues, and Exceptions in the type distribution. But lets get a graph to work also.

![setup](/static/images/part3/8.png)  

Return to SLP and click on the gears in the top nav.
![setup](/static/images/part3/9.png)  

Validate that the users are still connected to the system by looking at the status column.  
![setup](/static/images/part3/10.png)   

Now click on the database icon in the top nav  

![setup](/static/images/part3/11.png)  

Click on the first query on the list of available queries.  

![setup](/static/images/part3/12.png) 

Execute this query, it will generate an exception.   

![setup](/static/images/part3/13.png)  

Now change between all the available users on the list and submit the query. To change the user all you need to do is pick a different user from the dropdown. Once you have pressed the run button on each user, you can then return to the [DAM] Activity Reports screen in the GDP console.  

![setup](/static/images/part3/14.png) 

Hit refresh and you will now see an error about bening unable to render data, click on edit mode. This will make the dashboard editable.     

![setup](/static/images/part3/15.png) 

Click on the configuration icon on the exceptions per db user tile.   

![setup](/static/images/part3/16.png)  

This will allow you to customize the chart.  

![setup](/static/images/part3/17.png)  

Change the chart to be a bar chart.  

![setup](/static/images/part3/18.png)  
 
You will have now generated your DAM report with a graph of your activities.