# AWS Network Architecture — VPC with Public & Private Subnets  

## 📌 Overview  
This project demonstrates a **secure AWS VPC network design** with both **public and private subnets**, NAT Gateway, route tables, and EC2 instances.  
It shows how to host applications securely in private subnets while exposing only necessary services through the public subnet.  

---

## 🖼️ Architecture Diagram  
![AWS Network Architecture](./aws-network-architecture.png)  

---

## 🏗️ Architecture Details  

- **VPC CIDR:** `10.0.12.0/24`  
- **Public Subnet (10.0.12.0/28):**  
  - EC2 instance (Bastion Host / Web Server)  
  - NAT Gateway (with Elastic IP)  
  - Internet Gateway attached  
- **Private Subnet (10.0.12.16/28):**  
  - EC2 instance (Application Server)  
  - No public IP  
- **Route Tables:**

- ## 🔄 How It Works  
- Internet users access the **Public EC2** via IGW.  
- Private EC2 communicates with the internet **through NAT Gateway**.  
- Public EC2 can SSH into Private EC2 (bastion host).








  - Public RT → `0.0.0.0/0` → Internet Gateway  
  - Private RT → `0.0.0.0/0` → NAT Gateway
