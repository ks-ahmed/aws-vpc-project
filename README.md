<div align="center">
<img width="400" alt="DevOps" src="https://media.licdn.com/dms/image/v2/D4E22AQGTqoLT14ORKQ/feedshare-shrink_800/B4EZd5iVaRHYAg-/0/1750090743666?e=1753315200&v=beta&t=ji3p5fsqsu_BGeIfym5OBUvqr8rH0_54Gq7bOpMjUL0" />
</div>

#  AWS VPC Project – Custom VPC with Bastion Host and Private Server

## Project Overview

This project demonstrates the creation and configuration of a custom **Virtual Private Cloud (VPC)** on **Amazon Web Services (AWS)**. The goal was to build a secure, scalable, and well-architected network infrastructure from scratch, including public and private subnets, NAT and Internet Gateways, EC2 instances, and secure connectivity using a Bastion host.

## Project Goals

- Create a **custom VPC** with isolated public and private subnets
- Launch **EC2 instances** in both public (Bastion host) and private subnets (Private Server)
- Configure **Internet Gateway (IGW)** and **NAT Gateway** for connectivity
- Set up **Elastic IP** for the NAT Gateway
- Create and attach appropriate **Security Groups**
- Configure **Route Tables** to manage traffic
- Test **SSH connectivity** to the private server via Bastion Host (public subnet)

---

## Technologies Used

| Technology                   | Purpose                                                              |
| ---------------------------- | -------------------------------------------------------------------- |
| **AWS VPC**                  | Core networking layer for isolating resources in a virtual network   |
| **EC2**                      | Virtual servers used for Bastion Host and Private Server             |
| **Elastic IP**               | Static IP address for NAT Gateway to enable outbound internet access |
| **Internet Gateway**         | Allows resources in public subnet to connect to the internet         |
| **NAT Gateway**              | Enables internet access for private subnet resources                 |
| **Subnets (Public/Private)** | Logical network segments for organizing resources                    |
| **Route Tables**             | Controls traffic routing between subnets and external networks       |
| **Security Groups**          | Virtual firewalls to control inbound and outbound traffic            |
| **SSH**                      | Secure remote access to EC2 instances via Bastion Host               |
| **AWS Console**              | GUI-based management and configuration of all AWS resources          |
| **Key Pairs**                | Used for secure SSH authentication to EC2 instances                  |

---

## 1. VPC Creation

Created a custom VPC with a CIDR block `10.0.0.0/16`

![Screenshot 2025-06-21 130837](https://github.com/user-attachments/assets/be3fd257-1ea9-4b1e-ac26-fc4704288c27)


---

## 2. Public and Private Subnets

- Created **2 Public Subnets** (in different AZs)
- Created **2 Private Subnets** (in different AZs)

  ![Screenshot 2025-06-21 135223](https://github.com/user-attachments/assets/e7eec69c-57ee-4156-99e8-014e7aaaaf59)

---

## 3. Route Tables Configuration

- Associated the **Public Route Table** with public subnets
- Associated the **Private Route Table** with private subnets
- Added routes to IGW and NAT Gateway accordingly

![Screenshot 2025-06-21 153002](https://github.com/user-attachments/assets/3f3e0760-3594-4022-8ca3-b1fa117efffc)

---

 ![Screenshot 2025-06-21 163143](https://github.com/user-attachments/assets/d8762b63-87ed-4203-a780-6061ec314d1f)


---

## 4. Internet Gateway and NAT Gateway

- Created and attached an **Internet Gateway (IGW)** to the VPC
- Created a **NAT Gateway** in a public subnet using an **Elastic IP**
- Enabled private subnets to access the internet through the NAT Gateway

![Screenshot 2025-06-21 163130](https://github.com/user-attachments/assets/6650ba7a-73b2-4151-a499-ebc9fd1eeace)


 ---

![Screenshot 2025-06-21 163111](https://github.com/user-attachments/assets/595b97f6-123a-4f11-b57e-cfe30c469f4d)



---

## 5. EC2 Instance Setup

- Launched **Bastion EC2 Instance** in the public subnet
- Launched **Private Server EC2 Instance** in the private subnet


  ![Screenshot 2025-06-21 155834](https://github.com/user-attachments/assets/e55a37b3-7e5d-4de7-9b5d-a41cd5e66aab)


---

## 6. Security Groups

- Configured Bastion SG to allow SSH from a trusted IP
- Configured Private Server SG to allow SSH only from the Bastion Host

![Screenshot 2025-06-21 155850](https://github.com/user-attachments/assets/a43cf02b-8e59-478c-afcf-316a8726dbda)

---

## 7. SSH Connectivity Test

- SSH into the **Bastion Host**
- From Bastion, SSH into the **Private Server**

![Screenshot 2025-06-21 161657](https://github.com/user-attachments/assets/b1e60724-012d-41b6-9453-3f5cc245f0c9)

---

![Screenshot 2025-06-21 161951](https://github.com/user-attachments/assets/0df2cf32-9604-4199-9b38-7bde1883940f)



---

## Key Takeaway

This project was a successful hands-on implementation of core AWS networking components. I was able to design and deploy a custom VPC architecture that included public and private subnets, route tables, an Internet Gateway, a NAT Gateway with Elastic IP, and secure EC2 instance deployments.

By configuring a Bastion Host in the public subnet and a Private Server in the private subnet, I validated secure access to private resources via SSH. The successful connectivity test confirmed that all networking and security configurations were correctly applied.

This experience not only deepened my understanding of AWS VPC networking but also strengthened my practical skills in cloud infrastructure design, security best practices, and troubleshooting.

