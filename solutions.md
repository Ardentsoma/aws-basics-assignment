##  1. VPC & Networking (Custom Networking)

### Steps:
- Created a **custom VPC** with CIDR block `10.0.0.0/16`.
- Created:
  - **2 Public Subnet** ( with `10.0.0.0/20` IPv4 for the first subnet and `10.0.16.0/20` IPv4 CIDR for the second subnet )
  - **2 Private Subnet** (with `10.0.32.0/20` IPv4 for the first subnet and `10.0.48.0/20` IPv4 CIDR for the second subnet)
- Created and attached an **Internet Gateway** to the VPC.
- Created a **Route Table** and updated it with the internet gateway for the public subnet to allow internet access.
=======
##  1. VPC & Networking (Custom Networking)

### Steps:
- Created a **custom VPC** with CIDR block `10.0.0.0/16`.
- Created:
  - **2 Public Subnet** (e.g., `10.0.1.0/24`)
  - **2 Private Subnet** (e.g., `10.0.2.0/24`)
- Created and attached an **Internet Gateway** to the VPC.
- Updated **Route Table** for the public subnet to allow internet access.

