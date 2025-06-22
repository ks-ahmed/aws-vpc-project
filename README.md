#  AWS VPC Project – Custom VPC with Bastion Host and Private Server

## 🚀 Project Overview

This project demonstrates the creation and configuration of a custom **Virtual Private Cloud (VPC)** on **Amazon Web Services (AWS)**. The goal was to build a secure, scalable, and well-architected network infrastructure from scratch, including public and private subnets, NAT and Internet Gateways, EC2 instances, and secure connectivity using a Bastion host.

## ✅ Project Goals

- Create a **custom VPC** with isolated public and private subnets
- Launch **EC2 instances** in both public (Bastion host) and private subnets (Private Server)
- Configure **Internet Gateway (IGW)** and **NAT Gateway** for connectivity
- Set up **Elastic IP** for the NAT Gateway
- Create and attach appropriate **Security Groups**
- Configure **Route Tables** to manage traffic
- Test **SSH connectivity** to the private server via Bastion Host (public subnet)

---

## 📁 Project Structure


---

## 🏗️ 1. VPC Creation

Created a custom VPC with a CIDR block (e.g., `10.0.0.0/16`).

📸 _Screenshot_:  
![VPC Creation](./screenshots/vpc-creation.png)

---

## 🌐 2. Public and Private Subnets

- Created **2 Public Subnets** (in different AZs)
- Created **2 Private Subnets** (in different AZs)

📸 _Screenshot_:  
![Subnets](./screenshots/subnets.png)

---

## 🔀 3. Route Tables Configuration

- Associated the **Public Route Table** with public subnets
- Associated the **Private Route Table** with private subnets
- Added routes to IGW and NAT Gateway accordingly

📸 _Screenshot_:  
![Route Tables](./screenshots/route-tables.png)

---

## 🌍 4. Internet Gateway and NAT Gateway

- Created and attached an **Internet Gateway (IGW)** to the VPC
- Created a **NAT Gateway** in a public subnet using an **Elastic IP**
- Enabled private subnets to access the internet through the NAT Gateway

📸 _Screenshot_:  
![IGW & NAT](./screenshots/igw-nat.png)

---

## 💻 5. EC2 Instance Setup

- Launched **Bastion EC2 Instance** in the public subnet
- Launched **Private Server EC2 Instance** in the private subnet

📸 _Screenshots_:  
**Bastion Host:**  
![Bastion EC2](./screenshots/ec2-bastion.png)

**Private Server:**  
![Private EC2](./screenshots/ec2-private.png)

---

## 🔐 6. Security Groups

- Configured Bastion SG to allow SSH from a trusted IP
- Configured Private Server SG to allow SSH only from the Bastion Host

📸 _Screenshot_:  
![Security Groups](./screenshots/security-groups.png)

---

## 🔗 7. SSH Connectivity Test

- SSH into the **Bastion Host**
- From Bastion, SSH into the **Private Server**

📸 _Screenshot_:  
![SSH Connectivity](./screenshots/ssh-connectivity.png)

---

## 🧠 Key Takeaways

- Understanding and implementing AWS networking fundamentals
- Hands-on experience with route tables, NAT gateways, and security configurations
- Securing access to private resources using a Bastion host

---

## 📌 Future Improvements

- Automate infrastructure using **Terraform** or **CloudFormation**
- Add monitoring using **CloudWatch**
- Implement **Multi-AZ failover** and **Load Balancers**

---

## 🙌 Acknowledgements

Thanks to the AWS documentation and community for guidance and best practices.

---

## 📷 Notes

> 📁 _Please ensure all screenshots are placed inside the `/screenshots` folder as referenced above._

---

## 📤 Author

**Your Name**  
[Your LinkedIn or Portfolio]  
[Your Email]

