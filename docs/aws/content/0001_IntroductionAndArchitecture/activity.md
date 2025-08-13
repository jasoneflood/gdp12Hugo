---
title: "Getting started"
weight: 2
---

# IBM Guardium Data Protection – Getting started

There are two servers set up in a Virtual Private Cloud (VPC) configuration for this workshop. One server has Guardium Data Protection (GDP) deployed on it. The other server has DB2 community edition installed on it, as well as an opensource tool called Scenario Launch Platform (SLP), that you can read more about here: [https://github.com/IBM/CyberSkill/tree/main/ScenarioLaunchPlatform] should you wish.    

![setup](/static/images/part1/setup.png)  

The DB2 community edition is pre wired to the GDP instance deployed in the VPC. The SLP tool is used to generate traffic on the DB2 community edition that GDP will report, and has been preset with all the connection and schema information necessary to run the workshop. 

You can log into the workshops Guardium Data Protection by accessing this URL [GDP_URL]  
You can log into the workshops Scenario Launch Platform by accessing this URL [SLP_URL]  

You will use both of these URLs during this workshop. You should not need to log into the servers themselves, however - details of how to do that should you wish are included in the closing section of the workshop.


## Task 1 Setting up GDP.

### Step 1
Log into GDP by visiting [GDP_URL].  The username is admin. The password is AWS.trial1! In the top corner type the word "licence" as seen in the image below.  

![licence](/static/images/part1/licence.png)

### Step 2
This will bring you to a licence page. The GDP instance has been pre wired to the DB2 server, however the licence needs to be added in order for the two services to speak to each other. Your 90 day trial licence was sent to you when you signed up to the workshop. There are infact two licences that must be added. Start by copying and pasting the base licence key and clicking apply. You must start by adding the base licence first. 

![addLicence](/static/images/part1/addLicence.png)

### Step 3
You will then need to accept the licence aggrement.  

![acceptLicence](/static/images/part1/acceptLicence.png)

### Step 4
This will briefly log you out, and bring you back to the home screen where it will display number of days left on the trial.  

![licenceLeft](/static/images/part1/licenceLeft.png)

### Step 5
You now must repeat this process again for the second append licence. It is the exact same process as before. Each licence activates a different set of functionality in the workshop GDP. So it is important to ensure that both licences have been applied.    

#### Note
You will see some errors associated with certificates and updates once you have added the licences. These errors occur because we are using a trial licence. These errors can be ignored.

## Task 2 Validating setup.
Once both licences have been applied the GDP is now fully functional. At this point it is important to validate that the GDP instance is talking with the DB2 instance.  This is achieved by returning to the search bar in the top right and this time enter into search "stap control" and clicking S-TAP Control.   

![stapControl](/static/images/part1/stapControl.png)

### Step 1
Once you are on the S-TAP Control screen, validate that the status is green.   

![stapValidate](/static/images/part1/stapValidate.png)

### Step 2
Pat yourself on the back and congratulations - you have now successfully set up your GDP workshop and can now begin experimenting with GDP and DB2.