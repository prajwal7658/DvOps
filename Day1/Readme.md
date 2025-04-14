# AWS EC2 Instance Setup and SSH Connection Guide

This guide explains how to launch an EC2 instance on AWS and connect to it using SSH.

## Prerequisites

- AWS account
- AWS CLI installed and configured
- Existing key pair (.pem file)
- Basic terminal knowledge

## Step 1: Launch an EC2 Instance

1. Log in to the AWS Console at https://console.aws.amazon.com
2. Search for EC2 in the Services section and open the EC2 Dashboard
3. Click on "Launch Instance"
4. Fill in the following details:
   - Name: MyEC2Instance
   - Amazon Machine Image (AMI): Ubuntu Server 22.04 LTS (or your preferred one)
   - Instance Type: t2.micro
   - Key Pair: Create new or use existing key pair
   - Network Settings: Allow SSH (port 22) from your IP address
   - Storage: Default 8 GB is fine
5. Click "Launch Instance"

## Step 2: Get the Public IP

After the instance is running:
- Go to the Instances page
- Select your instance
- Copy the Public IPv4 address

## Step 3: Connect to EC2 via SSH

For macOS/Linux:

Run the following commands in your terminal:

chmod 400 /path/to/your-key.pem

ssh -i /path/to/your-key.pem ubuntu@your-ec2-public-ip

Example:

ssh -i ~/Downloads/my-key.pem ubuntu@3.120.45.67

Note: Use ec2-user instead of ubuntu if you're using Amazon Linux

## Step 4: Verify the Connection

If connected successfully, you will be inside your EC2 server.







