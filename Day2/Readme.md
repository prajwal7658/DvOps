# AWS CLI Installation and Setup Guide (Ubuntu Only)

This guide will help you install AWS CLI and configure it on Ubuntu.

## Step 1: Install AWS CLI

1. Open Terminal

2. Download the AWS CLI zip file:

   curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"

3. Unzip the downloaded file:

   unzip awscliv2.zip

4. Run the installer:

   sudo ./aws/install

5. Verify the installation:

   aws --version

## Step 2: Configure AWS CLI

1. Run the configure command:

   aws configure

2. Enter your credentials:

   AWS Access Key ID: your-access-key-id  
   AWS Secret Access Key: your-secret-access-key  
   Default region name: us-east-1 (or any preferred region)  
   Default output format: json

## Step 3: Verify the Configuration

Run the following command to verify if the CLI is correctly set up:

   aws sts get-caller-identity

If everything is configured correctly, it will return your AWS account details.

## Additional Requirements

Make sure the following tools are installed:

### unzip

   sudo apt install unzip

### curl

   sudo apt install curl

## Notes

- You need an AWS account to get the access and secret keys
- These can be generated in the AWS Management Console under IAM > Users > Security credentials
- Keep your credentials private and secure

## References

AWS CLI Installation Guide for Linux:
https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2-linux.html

