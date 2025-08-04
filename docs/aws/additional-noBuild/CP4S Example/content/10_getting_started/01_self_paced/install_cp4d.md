---
title: "Infrastructure Provisioning & Setup"
weight: 55
chapter: true
draft: false
pre: "<b>E. </b>"
---

<!--- # Infrastructure Provisioning & Setup --->

::alert[**Note: This lab document is only for **Self Paced** infrastructure deployment, not to be performed if you are performing lab through _AWS Event Engine_.**]

## Learning Objectives

- Deploy Redhat OpenShift and IBM Cloud Pak for Data using CloudFormation template
- Infrastructure provisioning for Lab - 4.

<!-- -->
## Prerequisites
- IBM Cloud Pak for Data
- AWS Account

## Overview

This lab implements creating required infrastructure and loading data onto respective AWS resources.

## Lab Environment

### Step 1: AWS Resources used in this lab

#### AWS Cloud9
**AWS Cloud9** is a cloud-based integrated development environment (IDE) that lets you write, run, and debug your code with just a browser. It includes a code editor, debugger, and terminal. Cloud9 comes prepackaged with essential tools for popular programming languages, including JavaScript, Python, PHP, and more, so you don’t need to install files or configure your development machine to start new projects. Since your Cloud9 IDE is cloud-based, you can work on your projects from your office, home, or anywhere using an internet-connected machine.

**How we made it different?**

In this cloud9 environment we have pre-installed with the required tools and utilities to access specific to our lab execution.

### Step 2: Cli Resources used in this lab
#### Openshift Cli
With the OpenShift command-line interface (CLI), the oc command, you can create applications and manage OpenShift Container Platform projects from a terminal. The **_OpenShift CLI_** is ideal in the following situations:

* Working directly with project source code

* Scripting OpenShift Container Platform operations

* Managing projects while restricted by bandwidth resources and the web console is unavailable

#### AWS CLI
The AWS Command Line Interface (AWS CLI) is a unified tool to manage your AWS services. With just one tool to download and configure, you can control multiple AWS services from the command line and automate them through scripts.

### Step 3: Create Hosted Zone for your domain

Follow below steps to create Hosted Zone in AWS:

1. Search for the _Route 53_ service and click **Hosted zones** under **DNS Management**.

![](/static/images/00_getting_started/route_53_1.png?classes=shadow)

2. Click **Create hosted zone** to create a new hosted zone for your domain name.

![](/static/images/00_getting_started/route_53_2.png?classes=shadow)

::alert[**Note: If you already have domain registered with AWS, then you may skip this step.**]

3. Note down the newly created NS record.

![](/static/images/00_getting_started/route_53_3.png?classes=shadow)

4. Once after creating hosted zone in AWS. visit your domain name provider and update NS (Name Server) record created in step 3.

### Step 4: Red Hat OpenShift pull secret.

1. Visit https://console.redhat.com/openshift/install/pull-secret and follow instructions to get Red Hat pull secret for OpenShift. Download the pull secret (json) file and save it in the Amazon S3 bucket for further use.

### Step 5: Create the stack in CloudFormation on AWS Console.

::alert[**Note: This lab is available only for 2 - 3 days.**]

  1. Login into AWS Console and search for _CloudFormation_ services and then click on **Create Stack** with new resources.

  ![](/static/images/00_getting_started/create_cfn_stack_1.png?classes=shadow)

  2. Select template source as **Amazon S3** and provide the below s3 url for _Amazon S3 URL_

  ![](/static/images/00_getting_started/create_cfn_stack_2.png?classes=shadow)

  ******
  https://ibm-aws-immersion-day.s3.us-east-2.amazonaws.com/self-paced/templates/master.yml
  ******

  3. Provide the required inputs

  Specify stack name and availability zone as shown below

  ![](/static/images/00_getting_started/create_cfn_stack_3.png?classes=shadow)

  Provide your domain name instead of _example.com_

  ![](/static/images/00_getting_started/create_cfn_stack_4.png?classes=shadow)

  Provide password to login to Red Hat OpenShift and IBM Cloud Pak for Data

  ![](/static/images/00_getting_started/create_cfn_stack_6.png?classes=shadow)

  Provide IBM Cloud Pak for Data API key which you might have received as the part of previous step.

  ![](/static/images/00_getting_started/create_cfn_stack_7.png?classes=shadow)

  Provide Redhat pull secret that you saved in Amazon S3 in earlier step.

  ![](/static/images/00_getting_started/create_cfn_stack_8.png?classes=shadow)

  4. Choose **appropriate IAM Role** as shown below.

  ![](/static/images/00_getting_started/3_Screenshot.png?classes=shadow)

  5. Acknowledge and Click the **Create stack** button

  ![](/static/images/00_getting_started/4_Screenshot.png?classes=shadow)

  6. Review the outputs (stacks) formed in AWS CloudFormation tab.

  ![](/static/images/00_getting_started/resources.png?classes=shadow)

::alert[**TIP: Since this is a master template we can view the resources as nested stacks.**]

  7. Review the output and Connect to the Cloud9 Environment.
  
  ![](/static/images/00_getting_started/cloud9.png?classes=shadow)

#### Access Cloud9 Environment through browser console and validate OpenShift and Cloud Pak for Data deployment.

1.  Check for the tools installation.

    ```sh
    oc version
    ```

    Output:

        ....
        Sample Output:
        .....
        Client Version: 4.9.23
        Server Version: 4.8.11
        Kubernetes Version: v1.21.1+9807387
        .....

    **aws** command

    ```sh
    aws
    ```


    Expected Output:

        usage: aws [options] <command> <subcommand> [<subcommand> ...] [parameters]
        To see help text, you can run:

          aws help
          aws <command> help
          aws <command> <subcommand> help

        aws: error: the following arguments are required: command

2.  Validate the aws secret key credentials.

    ```sh
    aws configure
    ```

    Output:

        AWS Access Key ID [****************HZH5]:
        AWS Secret Access Key [****************BBPW]:
        Default region name [us-east-2]:
        Default output format [json]:


3.  Connect to CP4D Cluster.

    ```sh
    export OCP_USER=ocsadmin
    export OCP_PASSWORD=ocsadmin
    export OCP_API=https://api.<clustername>.<domainname>:6443
    oc login --insecure-skip-tls-verify=true -u ${OCP_USER} -p ${OCP_PASSWORD} ${OCP_API}
    ```

    Expected Output:

        Login successful.

        You have access to 66 projects, the list has been suppressed. You can list all projects with 'oc projects'

    **whoami** command

    ```sh
    oc whoami --show-console
    ```

    Expected Output:

        https://console-openshift-console.apps.<clustername>.<domainname>.com


4.  Get the route.

    ```sh
    oc get route |awk 'NR==2 {print $2}'
    ```

      Using the route, users will be able to login into CP4D using the above created credentials and start Lab exercises.


### Step 6: Low/No Code ML application deployment on Amazon EKS cluster

1. Login to AWS console and search for **CloudFormation** service and search for the **Stack** name which you have created in **step 5**.

![](/static/images/00_getting_started/eks-3.png?classes=shadow)

2. Look for stack name starts with stackname**-PrerequisitesStack** and click on it.

![](/static/images/00_getting_started/eks-4.png?classes=shadow)

3. Go to the **Output** section of the stack and then note down the value of **KeyPairName**.

![](/static/images/00_getting_started/eks-5.png?classes=shadow)

4. Go to **EC2** services home page, and from the **Network & Security** section of EC2 click on **Key Pairs** to find the **ID** of key pair. for example here the ID is key-07137bb589deb20af.

![](/static/images/00_getting_started/eks-6.png?classes=shadow)

5. Search for **System Manager** service

![](/static/images/00_getting_started/eks-7.png?classes=shadow)

6. Click on **Parameter Store** and then search for **Key Pair** name which we found during step 6.

![](/static/images/00_getting_started/eks-8.png?classes=shadow)

7. Click on **Key Pair** and copy the **RSA Private Key** value.

![](/static/images/00_getting_started/eks-9.png?classes=shadow)

8. Create a pem file and paste the content in the pem file.

  ```sh
  vi ekskeypair.pem
  ```

and change the permission
  
  ```sh
  chmod 400 ekskeypair.pem
  ```

9. Go to **EC2** service page and then search for **EKSBastion** instance

![](/static/images/00_getting_started/eks-1.png?classes=shadow)

![](/static/images/00_getting_started/eks-2.png?classes=shadow)


10. Connect to **EKSBastion** node with PEM_FILE and INSTANCE_IP. Here INSTANCE_IP is the public ip of bastion instance.

  ```sh
  ssh -i PEM_FILE.pem ec2-user@INSTANCE_IP
  ```

11. clone **ibm-aws-quickstart-immersionday** repo

  ```sh
  git clone https://github.com/ibm-aws/ibm-aws-quickstart-immersionday.git
  ```

12. deploy the application using below commands

Go to project folder

  ```sh
  cd ibm-aws-quickstart-immersionday/
  ```

then

  ```sh
  cd templates/config
  ```

then

  ```sh
  chmod +x predictionappdeployment.sh
  ```

then run below command to deploy prediction app
   
  ```sh
  ./predictionappdeployment.sh <<EKS-clustername>>
  ```


## Conclusions

1. We have learned how to use the command line tools.
2. We have learned how to access the openshift cluster and CP4D
  environment.
3. We have learned how to use Cloud9 environment.