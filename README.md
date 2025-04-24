# aws-basics-assignment
This project contains a hands-on AWS basics assignment covering foundational cloud concepts such as custom VPC setup, EC2 instance configuration, application load balancing, IAM user management, and S3 bucket operations. It serves as a practical introduction to networking, compute, storage, and identity management within AWS.

## Project Overview

1. VPC & Networking (Custom Networking)
	•	Create a new VPC with CIDR block 10.0.0.0/16.
	•	Create 2 public subnets.
	•	Create 2 private subnets.
	•	Create and attach an Internet Gateway to your VPC.

2. Launch EC2 Instances
	•	Launch 2 EC2 instances in the public subnets:
	•	Use Amazon Linux 2.
	•	Install and configure a basic web server (e.g., Apache or Nginx).
	•	Add a custom index.html saying “Public Web Server AZ1” and “Public Web Server AZ2”.
	•	Launch 2 EC2 instances in the private subnet


3. Application Load Balancer (ALB)
	•	Create an Application Load Balancer in public subnets.
	•	Target the public EC2 instances using a target group.
	•	Configure a listener on port 80 to forward traffic to the target group.
	•	Test the ALB DNS in a browser to verify load balancing works.

4. IAM Users & Policies
	•	Create an IAM user named developer.
        •      Create a group called dev-group. Attach full access for s3 & ec2 to the group

5. S3 Bucket
	•	Create a new S3 bucket eg: fife-s3-bucket.
	•	Enable bucket versioning.
	•	Add a bucket policy to deny public access.
	•	Upload a sample file and confirm it’s versioned.
