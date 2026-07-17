# AWS Linux Practice Project

This repository documents my hands-on transition into Cloud Engineering.

## Skills Practiced

- Launching and managing an AWS EC2 instance
- Connecting to Amazon Linux using SSH
- Navigating the Linux file system
- Creating and organizing files and directories
- Installing and configuring Git
- Creating Git commits
- Connecting an EC2 environment to GitHub
- Pushing files from EC2 to GitHub

## Linux Commands Used

- pwd
- ls
- ls -la
- cd
- mkdir
- cat
- nano

## Git Commands Used

- git init
- git status
- git add
- git commit
- git branch
- git remote
- git push

## Project Goal

The goal of this project is to build confidence working inside a Linux cloud environment while developing practical AWS, Git, and GitHub skills.

## Author

Jamar Lynn


## IAM Role and S3 Read-Only Access

- Created an IAM role named `EC2-S3-ReadOnly-Role`
- Configured EC2 as the trusted AWS service
- Attached the `AmazonS3ReadOnlyAccess` policy
- Attached the IAM role to the running EC2 instance
- Verified the role with `aws sts get-caller-identity`
- Created a private S3 bucket named `jamar-aws-practice-2026-4827`
- Confirmed the EC2 instance could list S3 buckets with `aws s3 ls`
- Attempted to upload a test file and received `AccessDenied`
- Verified that the role allows read access but blocks `s3:PutObject`
- Practiced the AWS security principle of least privilege


## Custom S3 Least-Privilege Policy

- Created a customer-managed policy named `jamar-practice-bucket-ReadOnly`
- Limited the EC2 role to the bucket `jamar-aws-practice-2026-4827`
- Removed the broader `AmazonS3ReadOnlyAccess` policy
- Confirmed `aws s3 ls` returned `AccessDenied`, blocking access to the full bucket list
- Confirmed the approved bucket could still be listed
- Uploaded `s3-read-test.txt` through the S3 console
- Successfully read the object directly from S3 using the EC2 IAM role
- Verified the role cannot upload, delete, or modify S3 objects
- Demonstrated resource-specific least-privilege access



## EC2 Restart Validation

- Restarted the EC2 instance successfully
- Confirmed Apache started automatically through systemd
- Verified the website remained publicly accessible
- Reconfirmed the IAM role and least-privilege S3 access after restart
