---
title: "Getting Started with IBM Guardium Data Protection"
weight: 20
chapter: false
---

::alert[**Prerequisites**: Ensure you have access to the Event Dashboard with your unique GuardiumCollectorURL and SLPURL from the Event Outputs section.]

This workshop environment has been pre-configured with IBM Guardium Data Protection (GDP) and DB2 database services running in a secure AWS Virtual Private Cloud (VPC). Additionally, a Scenario Launch Platform (SLP) has been deployed to help generate realistic database activities for monitoring and analysis.

![setup](/static/images/part1/setup.png)  

All components are fully integrated and pre-configured with the necessary connections and schema information to provide you with a seamless learning experience. 

You can log into your Guardium Data Protection by accessing the Event Dashboard, and accessing the URL associated with the GuardiumCollectorURL key in Event Outputs. This URL is unique to your instance.  
You can log into your Scenario Launch Platform by accessing the Event Dashboard, and accessing the URL associated with the SLPURL key in Event Outputs. This URL is unique to your instance.  

![Event Outputs URLs](/static/images/URLs.png)  

You will use both of these URLs during this workshop. You should not need to log into the servers themselves.


## Step 1: Setting up GDP

Log into GDP by visiting the GuardiumCollectorURL in Event dashboard -> Event Outputs .  

  The username is :code[admin]{showCopyAction=true}   
  The password is :code[AWS.trial1!]{showCopyAction=true}   
  
In the top corner type the word "license" as seen in the image below.  

![licence](/static/images/part1/licence.png)

## Step 2: Adding Base License

This will bring you to a license page. The GDP instance has been pre wired to the DB2 server, however the licence needs to be added in order for the two services to speak to each other. Your 90 day trial licence was sent to you when you signed up to the workshop. There are infact two licences that must be added. Start by copying and pasting the base licence key and clicking apply. You must start by adding the base licence first. 

![addLicence](/static/images/part1/addLicence.png)

## Step 3: Accept License Agreement

You will then need to accept the licence aggrement.  

![acceptLicence](/static/images/part1/acceptLicence.png)

## Step 4: Verify License Status

This will briefly log you out, and bring you back to the home screen where it will display number of days left on the trial.  

![licenceLeft](/static/images/part1/licenceLeft.png)

## Step 5: Add Second License

You now must repeat this process again for the second append licence. It is the exact same process as before. Each licence activates a different set of functionality in the workshop GDP. So it is important to ensure that both licences have been applied.

![licenceLeft](/static/images/part1/licence_p2.png)    


::alert[**Note**: You will see some errors associated with certificates and updates once you have added the licences. These errors occur because we are using a trial licence and can be safely ignored.]

## Step 6: Validate S-TAP Connection

Once both licences have been applied the GDP is now fully functional. At this point it is important to validate that the GDP instance is talking with the DB2 instance.  This is achieved by returning to the search bar in the top right and this time enter into search "stap control" and clicking S-TAP Control.   

![stapControl](/static/images/part1/stapControl.png)

Once you are on the S-TAP Control screen, validate that the status is green.   

![stapValidate](/static/images/part1/stapValidate.png)

## Step 7: Complete Setup

Pat yourself on the back and congratulations - you have now successfully set up your GDP workshop and can now begin experimenting with GDP and DB2.