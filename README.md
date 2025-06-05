# AWS GuardDuty Threat Alerts

This project uses AWS GuardDuty to detect suspicious activities in an AWS account and sends real-time email alerts through SNS and EventBridge.

## What This Project Does

- Simulates threat findings using `aws guardduty create-sample-findings`
- Detects and reports threats such as unauthorized access and port scans
- Sends alert emails via SNS
- Routes GuardDuty findings to SNS using EventBridge rules

## Technologies Used

- AWS GuardDuty
- AWS SNS (Simple Notification Service)
- AWS EventBridge
- AWS CLI
- IAM roles and policies

## How It Works

1. Create an IAM user and configure AWS CLI
2. Enable GuardDuty in the target AWS region
3. Use CLI to generate sample threat findings
4. Set up SNS and subscribe your email to the topic
5. Create an EventBridge rule to forward GuardDuty findings to SNS
6. Receive automated email alerts on suspicious activity


## Repository Structure

- `screenshots/` - Contains images demonstrating the project
- `scripts/` - CLI command scripts for setup and testing
- `README.md` - Project overview and instructions

## Contact

For any questions or suggestions, please reach out at vartakdipeesha@gmail.com
