---
title: "Build Predictive models in SageMaker"
weight: 10
chapter: false
draft: false
---

> #### Note:
> Data (COVID19BE_HOSP.csv & COVID19BE_CASES_AGESEX.csv) required for this lab has been uploaded to Amazon S3 bucket as the part of infrastructure automation. **Update the BUCKET_REGION as us-east-2**.

Kindly keep the credentials from CPD, S3, SageMaker, DB2 handy for getting started with Trusted AI.

::alert[**You would need the below for this Lab** :- You will get these details in the **./printcredentials.sh** step from the Infrastructure Provisioning Lab.]

* **S3 Bucket Name**
* **SageMaker Access key & Secret Key**
* **SageMaker role**
* **CPD username & password**
* **DB2 Hostname, username & password**

> **Step 1**

**Download** the notebook :link[Data-pre-processing.ipynb]{href="/static/data-pre-processing/Data-pre-processing.ipynb" action=download} into your local file system.

**Please make sure to update the Region, Access Key & Secret Key in the Notebook wherever specified before running the notebook.**

**We have created multiple SageMaker Notebooks for this lab to simulate the Data Science experience.** You can start by uploading **Data-pre-processing.ipynb** notebook and try the remaining three notebooks offline using the same process.

> **Step 2**

**Create a SageMaker Notebook instance**

Login to the SageMaker console and click on Notebook instances under Notebook in the navigation pane.

![](/static/images/20_trusted_ai_lab/sm-login.png)

> **Step 3**

Click on create notebook instance, give it at name like **Lab1**, select the Notebook instance type as **ml.t2.medium**, Platform Identifier as **Amazon Linux 2, Jupyter Lab 1** & IAM role as shown below. It will take a couple of minutes for the instance to be created. Be patient!

![](/static/images/20_trusted_ai_lab/crt-nb-sm.png)

> **Step 4**

After the instance is created, click on open Jupyter. Click on **Upload** on the top right side to upload notebooks. 

> **Step 5**

Select the Kernel as **conda_python3** when prompted and choose **Set Kernel** option. 

**Note**:-You can upload all the notebooks in one go by clicking on UPLOAD option, select the notebooks and run them in SageMaker. After the notebooks are uploaded, it will reflect per below.

![](/static/images/20_trusted_ai_lab/opn-nb-sm.png)

> **Step 6**

**After uploading the notebook/s, click on the notebook hyperlink to open it, update the AWS credentials, click on Kernel and choose Restart & Run All option.** 

![](/static/images/20_trusted_ai_lab/opn-nb-sm.png)

![](/static/images/20_trusted_ai_lab/run-nb.png)

**You should see something like this after successfully running the Notebooks.**

![](/static/images/20_trusted_ai_lab/nb-run.png)

> **Step 7**

**Let's download the SageMaker Notebook/s to be ported to Cloud Pak for Data - Select/Open the notebook - click on File - Download as - Notebook(.ipynb) into your local file system.** >  

![](/static/images/20_trusted_ai_lab/dw-nb-sm.png)

**Optional**

**Repeat these steps for the other notebooks offline.**

**Download** the remaining three notebooks :link[Notebooks.zip]{href="/static/notebooks/Notebooks.zip" action=download} into your local file system and unzip the file. Follow the process above to upload them into SageMaker, run the notebooks and download the notebooks into your local system which can be ported to Cloud Pak for Data.
