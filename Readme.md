# Terraform EC2 Web Server Project

## Overview

This project uses Terraform to provision AWS infrastructure and deploy two Apache web servers using EC2 User Data.

## Architecture

- Custom AWS VPC
- Two public subnets across separate Availability Zones
- Internet Gateway and route table
- Security group with HTTP, SSH, and optional HTTPS access
- Two EC2 instances running Apache
- S3 bucket resource
- Automated HTML page generation using instance metadata

## Technologies

- Terraform
- Amazon Web Services (AWS)
- Amazon EC2
- Amazon VPC
- Amazon S3
- Apache HTTP Server
- Linux Bash scripting

## Deployment

1. Configure AWS credentials securely.
2. Update Terraform variables and verify the AMI ID and AWS region.
3. Initialize Terraform:

   ```bash
   terraform init
   ```

4. Validate the configuration:

   ```bash
   terraform fmt
   terraform validate
   ```

5. Review and deploy:

   ```bash
   terraform plan
   terraform apply
   ```

6. Access the public IP address of each EC2 instance over HTTP.

## Security Notes

- Restrict SSH access to trusted IP addresses.
- Do not commit AWS credentials, private keys, Terraform state files, or secret variables.
- Use an IAM instance profile for AWS API access from EC2.
- Configure a trusted TLS certificate and domain for production HTTPS.

## Cleanup

When finished, review the resources Terraform manages and run:

```bash
terraform destroy
```

Review the proposed deletions before confirming. Resources created outside Terraform may require separate cleanup.