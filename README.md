# Cloud-Native Security Monitoring Platform (AWS)

## Overview
This project explores how security-relevant identity and privilege events are logged in modern AWS environments using CloudTrail and IAM Identity Center.

## Phase 0 – Audit Logging Setup
- Enabled CloudTrail management events, read + write 
- Validated end-to-end delivery to S3
- Confirmed logging of control plane activity

## Phase 1 – Identity Privilege Events
- Enabled IAM Identity Center
- Created test user, group, and permission set
- Assigned AdministratorAccess to an AWS account
- Identified `CreateAccountAssignment` as the key privilege escalation event in the CloudTrail event history
## Phase 2 - Lambda function and EventBridge
- Create the lambda function first
- Then create the EventBridge tied to AWS services and have the lambda function as the target with event names ["AttachUserPolicy", "AttachRolePolicy", "PutUserPolicy"]
## Next Steps
- Parse CloudTrail JSON logs using Python
- Detect and alert on admin privilege grants
- Deploy detection logic using AWS Lambda
