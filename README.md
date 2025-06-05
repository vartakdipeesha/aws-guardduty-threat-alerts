#  AWS GuardDuty Threat Alerts

This project detects suspicious activities (like port scans or brute-force login attempts) in AWS using **Amazon GuardDuty**. It then sends **real-time email alerts** through **SNS** and **EventBridge**.

## What This Project Does

- Simulates threats using `aws guardduty create-sample-findings`
- Automatically detects and reports threats like:
  - UnauthorizedAccess
  - Recon:EC2/PortProbe
- Uses SNS to send alerts to your email
- Uses EventBridge to route GuardDuty alerts to SNS

## Technologies Used

- AWS GuardDuty
- AWS SNS (Simple Notification Service)
- AWS CloudWatch Logs
- AWS EventBridge
- AWS CLI
- IAM roles & policies

##  How It Works

1. Create an IAM user and configure with AWS CLI
2. Enable GuardDuty in your region
3. Use CLI to generate sample threats
4. Set up SNS → Subscribe to your email
5. Set up EventBridge rule → connect GuardDuty → SNS topic
6. Get alert email automatically!!



