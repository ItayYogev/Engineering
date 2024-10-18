# Implement Microsoft Defender for Cloud in AWS Environment

## What is CNAPP?
CNAPP (Cloud-Native Application Protection Platform) is a solution designed to identify security risks at all stages of the SDLC (Software Development Life Cycle) and present them in a single user interface.

## CNAPP Components

![image](https://github.com/user-attachments/assets/59c3c9a9-d858-4748-8fdf-1d5ad63fdb86)

### CWPP (Cloud Workload Protection Platform)
CWPP is a security solution designed to monitor and protect workloads running on cloud infrastructure. Cloud workloads include various types of tasks, software, and data that may run on different cloud environments. These workloads can be deployed across both managed and unmanaged cloud infrastructures, depending on the organization's setup. Common examples of cloud workloads include:
- **Applications**: Comprising databases, servers, and networks connecting them.
- **Virtual Machines (VMs)**
- **Containers**
- **Kubernetes Clusters**
- **Serverless Functions** (e.g., AWS Lambda)
- **AI-based Workloads**

CWPP solutions typically offer these key features:
- **Vulnerability Management**: Scans for security vulnerabilities across workloads and infrastructure to ensure that they are protected from known threats.
- **Runtime Protection**: Provides real-time (runtime) security for workloads, detecting and preventing malware, exploits, and other active threats while the workloads are in operation.

### CIEM (Cloud Infrastructure Entitlement Management)
CIEM focuses on managing and monitoring identities, permissions, and access (IAM) to cloud resources. It ensures that proper access controls are in place and enforces the principle of least privilege to reduce security risks, particularly in large-scale, dynamic cloud environments. CIEM helps to detect and mitigate risks such as overprivileged accounts and misconfigured access controls.

---

## Connecting AWS to Microsoft Defender for Cloud

### Access Environment Settings
1. Navigate to **Environment Settings** and click the **Add Environment** button.
![image](https://github.com/user-attachments/assets/c7b73571-8946-4513-99ab-39df93548ded)

2. Select **AWS** as the environment.

### Account Details (First Page):
![image](https://github.com/user-attachments/assets/91d58fcd-f948-40d1-bc3f-c8b6797a39dd)

- **Connector Name**: Enter the name for your connector.
- **Onboard**: Choose how to onboard your AWS accounts:
  - **Management Account**: Select this option to onboard the management account and automatically onboard all other linked accounts. This will also apply to any new accounts created after the onboarding process.
  - **Single Account**: Select this option if you're onboarding a single account.
- **AWS Regions**: Select the AWS region where your resources are located.
- **Subscription**: Choose the Azure subscription under which this connector will be managed.
- **Resource Group**: Assign a name for the resource group.
- **Location**: Select the exact location for the resource group.
- **Scan Interval**: Set the scan interval. Note that for certain resources listed in the documentation, there are fixed scan intervals that cannot be modified.
- **Account ID**: Enter the Account ID of the AWS account you're onboarding.

![image](https://github.com/user-attachments/assets/9469594b-34f3-4f8e-81f7-708ae913184e)

- **Excluded Accounts**: (Optional) If you're using the **Management Account** option, you can exclude specific accounts from onboarding.

### Select Plans
- Choose the protection plan you want to apply.  
![image](https://github.com/user-attachments/assets/e8bc3776-076e-4a52-aa11-cfa68f52d19b)


### Configure Access
- Configure access by assigning the roles chosen on the previous page to AWS:
![image](https://github.com/user-attachments/assets/ef3a501d-7414-4c36-a7e1-0bbfd7e4ca2c)

  - Download the **CloudFormation template** from the top of the page.
  - Click **Go to AWS** (optional; you can go to AWS directly).

**In AWS**:
- Go to **CloudFormation** and create a **stack**. Upload the CloudFormation template you downloaded earlier.

**In Defender for Cloud**:
- Enter the **StackSet name** that you created in AWS for the stack.

### Final Review and Save
- Review the details one last time and click **Save** to complete the s
