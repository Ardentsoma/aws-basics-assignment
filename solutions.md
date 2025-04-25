##  1. VPC & Networking (Custom Networking)

### Steps:
- Created a **custom VPC** with CIDR block `10.0.0.0/16`.
- Created:
  - **2 Public Subnet** ( with `10.0.0.0/20` IPv4 for the first subnet and `10.0.16.0/20` IPv4 CIDR for the second subnet )
  - **2 Private Subnet** (with `10.0.32.0/20` IPv4 for the first subnet and `10.0.48.0/20` IPv4 CIDR for the second subnet)
- Created and attached an **Internet Gateway** to the VPC.
- Created a **Route Table** and updated it with the internet gateway for the public subnet to allow internet access.


## 2. Launch EC2 Instances

### Steps:
- Launched 2 **EC2 instances** in the public subnet using Amazon Linux 2.
- Installed **Apache** on both instances.
- Created a custom **index.html** file to show different messages per server.
  
```
sudo yum update -y
sudo yum install httpd -y
sudo systemctl start httpd
sudo systemctl enable httpd
sudo nano /var/www/html/index.html
```
- Launched 2 **EC2 instances** in the private subnet using Amazon Linux 2.

## 3.  Application Load Balancer (ALB)

### Steps:
- Created an **Application Load Balancer** in the public subnets.
- Created a **Target Group** with the 2 public EC2 instances.
- Configured a **Listener on port 80** to forward traffic to the target group.
- Tested the **ALB DNS URL** in a browser to verify load balancing.

## 4. IAM Users & Policies
### Steps:
- Created an IAM user named developer.
- Created a group called dev-group.
- - Added the user to the group.
- Attached the following permissions to the group:
   `AmazonEC2FullAccess`
   `AmazonS3FullAccess`

  ## 5. S3 Bucket
  
### Steps:
- Created S3 bucket: **soma-private-bucket1**.
- Enabled versioning via the console.
- Uploaded a sample file.
- Uploaded a new version of the same file to verify versioning
- Configured **bucket policy** to deny public access:

```
{
    "Version": "2012-10-17",
    "Id": "Policy1745533251630",
    "Statement": [
        {
            "Sid": "Stmt1745533239951",
            "Effect": "Deny",
            "Principal": "*",
            "Action": "s3:GetObject",
            "Resource": "arn:aws:s3:::soma-private-bucket1/*"
        }
    ]
}
```



