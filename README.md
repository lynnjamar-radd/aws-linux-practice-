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
