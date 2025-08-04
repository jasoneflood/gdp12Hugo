---
title: "Create an AWS account"
weight: 15
chapter: true
draft: false
pre: "<b>A. </b>"
---

<!--- # Create an AWS account --->

::alert[**You need to use your own AWS Account to perform the next steps. Running this workshop will incur in charges.**]

If you don't have an AWS account yet, [click here](https://aws.amazon.com/premiumsupport/knowledge-center/create-and-activate-aws-account/) to create a AWS account.

::alert[**Your account must have the ability to create new IAM roles and scope other IAM permissions.**]

## Create an IAM user

Once you have an AWS account, log in to your AWS account to create an IAM user to use for the workshop.

1. Navigate to the [IAM console](https://console.aws.amazon.com/iam/home#/home) to create a new IAM user with Administrator role.
2. Enter a **User name**, e.g.: IBM-Workshop-Admin.
3. Tick **AWS Management Console access** check box from Access type and then choose **Custom password** and enter the password.
4. Click **Next: Permissions**.

![Create User](/static/images/00_getting_started/create_iam_user.png)

5. Choose Attach existing policies directly, tick AdministratorAccess option and then click Next: Tags 

![Attach Policy](/static/images/00_getting_started/iam_user_policy.png)

6. Click Next: Review from Add tags(optional) section.
7. Review AdministratorAccess, AWS managed policy, is added to Administrator user and then click Create user
8. After creating the user, copy the login URL. The format of the URL is as below.

https://<your_aws_account_id>.signin.aws.amazon.com/console

::alert[**Replace <your_aws_account_id> with the unique ID of your own AWS account. We don't recommend to proceed the lab with root user. Please login with the Administrator user and proceed the lab.**]

![Login URL](/static/images/00_getting_started/iam_user_login.png)

10. Log out from the root user and then **log in to the Administrator user you just created** using the URL you copied above.