---
title: "4.3. RI-Prediction App"
weight: 70
chapter: true
draft: false
---

::alert[In this section, you will explore the Risk Index Prediction Application running on Amazon Elastic Kubernetes Service (EKS). The intent of this section is to simulate how existing applications running on AWS can invoke the IBM Watson Machine Learnig model with customizations.]

## Architecture Overview of the Risk Index Prediction Application

The Risk Index Prediction application is built using the following client-server architecture:

- Client: ReactJS
- Server: Nginx

Access the :link[Risk Index Prediction Application]{href="http://risk-index-prediction-app.ibmworkshops.com/"}

The app will look something as shown below.

![ri-app](/static/images/50_low_no_code_ml_Lab/lab4-ext-ri-app.png?classes=shadow)

1. You need to enter the Amazon API Gateway Endpoint URL for the Lambda function that you configured in previous step.

::alert[This URL is the **SamEndpointUrl** provided in Infra Provisioning Lab.]

1. Before you get started, download the :link[Covid-19-Predictions-Dashboard.json]{href="/static/dashboard/Covid-19-predictions-dashboard.zip action=download"} dashboard file and extract the zip file.

2. You can upload a dataset with n rows of data and get the risk index prediction along with probability. Download this sample :link[test-data.csv]{href="/static/files/test-data.csv" action=download} file and upload it in the application.
3. You can also see the visual representation of this activity with architecture diagram to understand the flow better.

You can then analyse the risk index predictions and probability along with the scoring data in a table format.

![application-execution](/static/images/50_low_no_code_ml_Lab/lab4-ext-app.gif?classes=shadow)
