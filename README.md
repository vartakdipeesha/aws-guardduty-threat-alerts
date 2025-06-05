# AWS GuardDuty Threat Alerts

This project uses AWS GuardDuty to detect suspicious activities in an AWS account and sends real-time email alerts through SNS and EventBridge.

# What This Project Does

1) Simulates threat findings using aws guardduty create-sample-findings

2) Detects activities like port scans, account compromise, or unusual API calls

3) Sends real-time alerts via Amazon SNS to subscribed email addresses

4) Uses Amazon EventBridge to route findings from GuardDuty to SNS

# Technologies Used

🛡️ AWS GuardDuty

📩 AWS SNS (Simple Notification Service)

⚙️ AWS EventBridge

💻 AWS CLI

🔐 IAM roles & permissions


# Setup & Workflow with Screenshots

This section explains the key commands used in the project along with their purpose, permissions required, and relevant screenshots illustrating each step.

## Installing AWS CLI

   
        brew install awscli
   

  <img width="735" alt="Screenshot 2025-06-05 at 8 28 07 PM" src="https://github.com/user-attachments/assets/a583a7ea-950f-496d-9a8f-1da440fc2cc9" />


Explanation:

  Installs the AWS Command Line Interface to allow command-line interactions with AWS services.

  Permissions: None (local installation).


## Configuring AWS CLI

   
        aws configure
   

  <img width="588" alt="Screenshot 2025-06-05 at 8 33 46 PM" src="https://github.com/user-attachments/assets/aa723620-d811-40e4-8d2c-7989cf0acf9b" />


Explanation:

  Configures your AWS credentials (Access Key, Secret Key), default region, and output format for AWS CLI commands.

   Permissions: IAM user with programmatic access.


## Listing GuardDuty Detectors

   
        aws guardduty list-detectors
   

<img width="491" alt="Screenshot 2025-06-05 at 8 38 04 PM" src="https://github.com/user-attachments/assets/00797b58-32fb-426b-9da6-bbf3dac8ccf7" />


Explanation:

Lists active GuardDuty detectors in your AWS account. A detector monitors your AWS environment for threats.

Permissions: guardduty:ListDetectors


## Creating GuardDuty Detector

   
        aws guardduty create-detector --enable
   

<img width="910" alt="Screenshot 2025-06-05 at 8 40 16 PM" src="https://github.com/user-attachments/assets/0608b494-33fe-4945-a6f6-9dbc13c06362" />


Explanation:

Enables GuardDuty for your AWS account by creating a detector. If one exists, you’ll receive an error.

Permissions: guardduty:CreateDetector



## Generating Sample GuardDuty Findings

  
        aws guardduty create-sample-findings --detector-id <detector-id>
   

Explanation:

Simulates threat findings to test alerting workflows without needing real attacks.

Permissions: guardduty:CreateSampleFindings


<img width="1423" alt="Screenshot 2025-06-05 at 6 14 53 PM" src="https://github.com/user-attachments/assets/7b56e8df-3f0d-417e-9de9-b70a3330f890" />


## Assigning GuardDuty Permissions

   
Explanation:

IAM user or role requires AmazonGuardDutyFullAccess policy to perform GuardDuty operations.



<img width="1440" alt="Screenshot 2025-06-05 at 6 17 01 PM" src="https://github.com/user-attachments/assets/dc5da6b7-06a7-42d7-99dd-49c55af595d7" />


## Creating SNS Topic & Email Subscription

   
Explanation:

Creates an SNS topic to send notifications and subscribes an email address to receive alerts.

Permissions: sns:CreateTopic, sns:Subscribe, sns:ConfirmSubscription

Screenshots:


1) <img width="1440" alt="Screenshot 2025-06-05 at 6 18 04 PM" src="https://github.com/user-attachments/assets/95b91581-f749-4442-bee2-f43d1502ac54" />


- SNS topic creation screen


2) <img width="720" alt="Screenshot 2025-06-05 at 8 48 59 PM" src="https://github.com/user-attachments/assets/521d64d3-470a-48ce-9d38-f26a278c7152" />


— Creating subscription to topic


3) <img width="1401" alt="Screenshot 2025-06-05 at 9 16 35 PM" src="https://github.com/user-attachments/assets/5d75d7fd-f886-4b7d-9acb-a81a834d570f" />



— Subscription success confirmation


4) <img width="683" alt="Screenshot 2025-06-05 at 8 53 09 PM" src="https://github.com/user-attachments/assets/320758a6-b6b5-442b-b898-2eca59d50b24" />


— Email received to confirm subscription


## Creating EventBridge Rule to Route Findings to SNS


- EventBridge rule configured to capture GuardDuty findings and forward them to SNS for alerting.


Permissions: events:PutRule, events:PutTargets


## Receiving Alert Emails
   
<img width="1440" alt="Screenshot 2025-06-05 at 7 13 03 PM" src="https://github.com/user-attachments/assets/e14d303b-3fd0-4855-9cb3-7e738d4b22a7" />

- When GuardDuty detects threats (including simulated ones), SNS sends alert emails to subscribed addresses.

- Example of alert emails received with details of GuardDuty findings.

  

# Summary

This project showcases how to build an automated threat detection and alerting pipeline using AWS GuardDuty, Amazon SNS, and EventBridge. By simulating threat activity, configuring real-time alert rules, and integrating email notifications, it demonstrates a practical approach to cloud security monitoring.

From setting up GuardDuty detectors to receiving live email alerts for suspicious behavior, every step is illustrated with CLI commands and real AWS Console screenshots—making it easy to replicate, learn, and apply in real-world AWS environments.



# Contact

For any questions or suggestions, please reach out at vartakdipeesha@gmail.com
