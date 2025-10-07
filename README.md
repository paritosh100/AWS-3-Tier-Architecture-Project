# 🏗️ AWS Three-Tier Web Architecture (High Availability & Scalability)

This project demonstrates the design of a **highly available, fault-tolerant, and scalable three-tier web application architecture** on **Amazon Web Services (AWS)** — following the AWS Well-Architected Framework.

---

## 🌐 Architecture Overview
The architecture separates the system into three layers:
1. **Web Tier** – An **Application Load Balancer (ALB)** receives incoming HTTP/HTTPS requests from clients and distributes them across multiple **EC2 instances**.
2. **Application Tier** – **Auto Scaling Groups** in **private subnets** host the application servers, scaling dynamically based on demand.
3. **Database Tier** – **Amazon RDS (MySQL)** runs in **Multi-AZ** mode, ensuring data durability, replication, and high availability.

All resources are deployed within an **Amazon VPC** with isolated **public and private subnets**, protected by **security groups** and **route tables** for secure communication.  
**NAT Gateways** enable outbound internet access for private instances, and **CloudWatch** monitors health, scaling events, and performance metrics.

---

## 🧾 Architecture Diagram
> 📘 Click below to view the full PDF diagram.

[**View Architecture Diagram (PDF)**](./3-tier_diagram.drawio.pdf)

> _If GitHub does not render the preview automatically, open the PDF link above._

![AWS Three-Tier Architecture Preview](./3-tier_diagram.drawio.pdf)

---

## 🔁 Traffic Flow
1. **Client** sends a request → reaches **Application Load Balancer** via Internet Gateway  
2. **ALB** forwards traffic to healthy **EC2 instances** (Auto Scaling group)  
3. **EC2** queries the **Amazon RDS MySQL** database (private subnet)  
4. **RDS** returns results → **EC2** processes response → **ALB** → **Client**

---

## 🧰 AWS Services Used
- **Amazon VPC** – Network isolation and subnet segmentation  
- **Application Load Balancer (ALB)** – Request routing and health checks  
- **Amazon EC2 + Auto Scaling** – Compute layer with on-demand scalability  
- **Amazon RDS (MySQL, Multi-AZ)** – Managed relational database with failover  
- **NAT Gateway & Internet Gateway** – Secure public and private network access  
- **Amazon CloudWatch** – Monitoring, scaling metrics, and alerting  

---

## 🔒 Key Features
- Multi-AZ **high availability** and **fault tolerance**  
- **Auto Scaling** for performance and cost efficiency  
- Secure **tier isolation** using private subnets and security groups  
- **Monitoring & automation** through CloudWatch and SNS notifications  
- Architecture aligned with **AWS Well-Architected Framework**

---

## 🧠 Learning Outcome
This project illustrates how to **architect production-grade, data-driven cloud systems** using AWS services.  
It demonstrates how **Data Scientists and Cloud Engineers** can leverage AWS for scalable analytics, API-driven workloads, and resilient backend systems.

---

## 🧩 Author
**Paritosh Kiran Gandre**  
*M.S. in Data Science, Kent State University*  
📫 [LinkedIn](https://linkedin.com/in/paritosh-gandre) | [Portfolio](https://paritosh-gandre.vercel.app)
