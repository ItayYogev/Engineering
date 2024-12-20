# Orca Security Customization
This document serves as a comprehensive guide for maintaining, improving, troubleshooting, and implementing various projects within the Orca Security CNAPP (Cloud Native Application Protection Platform). It aims to provide clear instructions and best practices for utilizing Orca's powerful features to enhance your organization's security posture. 


## Table of Contents
1. [Creating Custom Alerts](#creating-custom-alerts)
   - [Steps](#steps)
   - [Alert Configuration](#alert-configuration)
   - [Viewing Created Alerts](#viewing-created-alerts)
2. [Creating Automation](#creating-automation)
   - [Overview](#overview)
   - [Steps](#steps-1)
3. [Creating Views](#creating-views)
   - [Using the Discovery Category](#using-the-discovery-category)
   - [Using the Alerts Category](#using-the-alerts-category)
4. [Adding an AWS Account](#adding-an-aws-account)
   - [Steps](#steps-2)
   - [Configure AWS Features](#configure-aws-features)

---

## Creating Custom Alerts

In Orca's CNAPP, you can create **custom alerts** to receive notifications about specific situations that your organization wants to monitor. 

In this example, we will create alerts from the **Discovery** category, as it is more convenient. We will create an alert for a new bucket that is publicly accessible.

![image](https://github.com/user-attachments/assets/6d7b3991-669a-4550-b02a-4ff155c0711f)

### Steps
1. Navigate to the **Discovery** category.
2. Enter all the information you want to receive notifications about. 
   - You do not need to know the Orca syntax; you can write free text in English, and Orca's built-in AI engine will display the relevant results. Be sure to check the filtering the AI performs, as there may be errors.
3. Click the **Create** button, then select **Custom Alert**.

![image](https://github.com/user-attachments/assets/82a7a48b-d841-4245-9a58-9912a7ee8f2c)

### Alert Configuration
- **Create Query:** This is the alert filter (already defined).
- **Alert Details:** Fill in the alert details:
  - **Alert Name**
  - **Description**
  - **Category**
  - **Risk Base Score:** Check the box for "Allow Orca to adjust the score using asset context."
  - **Compliance Framework:** Optional (not required).
  - **Summary:** Review all the settings to ensure they are correct, then click **Create**.

### Viewing Created Alerts
To see all the alerts you have created, go to:  
**Settings > Management > Alert Catalog**.

![image](https://github.com/user-attachments/assets/5c480f53-c0d3-428a-8645-55731cba3bea)

---

## Creating Automation

### Overview
You can create automations in the Orca platform to streamline tasks that are performed manually.

In this example, we will address a scenario where the development department uses the **Impacket** library, which is classified by Orca as malicious. 

We will create automation that takes all alerts of this type and resolves them automatically.

![image](https://github.com/user-attachments/assets/115d8d81-e373-47f6-9d9d-3fe3cc16a5c0)

### Steps
1. Navigate to: **Settings > Management > Automations**.
2. Click on **Create Automation**.
3. Fill in the automation details:
   - **Automation Name**
   - **Description**
   - **End Time:** Optional.
   - **Trigger Query:** This is the filter for the automation.
   - **Define Results:** Specify what the result of the automation will be.

There are additional categories that include integrations, but we won't focus on them at this moment. Here’s an example of the automation I created:

![image](https://github.com/user-attachments/assets/fb500cc7-6610-4f52-bba6-b950f2a61c5f)

Once the automation is ready, click the **Save** button at the bottom.

---

## Creating Views

The **View** option is available in almost every category in Orca, aiming to display and save a customized view that you frequently want to see.

### Using the Discovery Category
In this example, we will create a view that shows new alerts with a scoring of 6.5 and above, which includes medium and higher alerts. Orca's scoring is as follows:
- **Critical** (score 9.0 - 10.0)
- **High** (score 7.0 – 8.9)
- **Medium** (score 5.0 – 6.9)
- **Low** (score 3.0 – 4.9)
- **Informational** (score 1.0 – 2.9)

![image](https://github.com/user-attachments/assets/f866168a-f9c7-472f-a27b-a609c5290f27)

#### Steps
1. Navigate to the **Discovery** category.
2. Select the view that you want to save.
3. Click the **Save As** button at the top.

![image](https://github.com/user-attachments/assets/4acf68e6-5def-4287-a1cb-2a174ef2b6d7)

#### Configuration
- Provide a name and description for the view, then click **Save**. 

![image](https://github.com/user-attachments/assets/c93872a6-0b24-4a04-80f6-61af5f6f6004)


Now, you should see the new view you created at the top of the screen.

![image](https://github.com/user-attachments/assets/63fe105f-aa17-4998-bd67-1f277c31eb40)

---

### Using the Alerts Category
Let’s take the same example from the previous explanation to display all new alerts classified as medium and higher.

In the **Alerts** category, the filters are located on the right side:

![image](https://github.com/user-attachments/assets/8e5b590f-6d34-48e9-a36c-3812c78f0f1c)

- **Filters:** Criteria for displaying/not displaying results.

![image](https://github.com/user-attachments/assets/1c17eba7-4287-422a-a040-abfbf119c14a)

- **Group:** Criteria for grouping/not grouping alerts (optional).
- **Sort:** Criteria for sorting/not sorting results.

![image](https://github.com/user-attachments/assets/16dba9c6-a9e2-412c-a9e3-e8f9ac680b5c)

#### Steps for Saving the View
The process for saving the view is the same as described earlier:
1. Click the **Save As** button at the top.
2. Provide a name and description for the view, then click **Save**.

---

## Adding an AWS Account

In this guide, we will explain how to connect an AWS account to the Orca platform.

**Note:** At the top right corner of the Orca platform, you can choose between connecting a single account, multiple accounts, or performing customization. In this guide, we will focus on connecting a single AWS account.

![image](https://github.com/user-attachments/assets/5ef75e8e-922e-40ce-8ff4-84cf824070d3)

### Steps
1. Log in to the Orca platform and go to: **Settings > Connections > Account Center**.
2. Click the **Connect Account** button in the top right.
3. Choose the **AWS** option.

![image](https://github.com/user-attachments/assets/2b37bf34-0de4-4f80-97ec-5a35306df1ba)

### Configure AWS Features
Follow the steps displayed in the Orca platform:

![image](https://github.com/user-attachments/assets/5d39920a-d40e-4e22-a6dc-f6639970842d)

- **Enable Features:** Configure features such as:
  - **Auto Remediation:** Automatic response to security events.
  - **Managed Databases:** Security insights for databases (RDS).
- **Connect to AWS**
- **Upload the CloudFormation Template:** Check the box and click **Create Stack**.

![image](https://github.com/user-attachments/assets/aeed01c7-5ec4-4eb2-86a0-990c824f03c7)

### Finalizing the Connection
1. In CloudFormation, switch to the **Outputs** tab, copy the ARN, and paste it in the appropriate field in the Orca platform.
2. In the Orca platform, click the blue **Connect Account** button.
