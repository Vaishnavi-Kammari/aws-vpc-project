# 🚀 AWS VPC Architecture using Terraform

## 📌 Overview

This project demonstrates the creation of a complete AWS VPC architecture using Terraform. It includes public and private subnets, an Internet Gateway, a NAT Gateway, route tables, and EC2 instances to simulate a real-world production-like environment.

---

## 🧱 VPC Architecture

This project follows a **2-tier architecture** with proper network isolation:

* A **Virtual Private Cloud (VPC)** with CIDR block `10.0.0.0/16`
* A **Public Subnet** for resources accessible from the internet
* A **Private Subnet** for secure internal resources
* An **Internet Gateway (IGW)** to allow inbound/outbound internet traffic for public resources
* A **NAT Gateway** to allow private instances to access the internet securely
* **Route Tables** to control traffic flow between subnets and gateways

### 🔄 Traffic Flow

* **Public EC2 Instance**

  * Receives traffic from the internet via Internet Gateway
  * Used for direct access (SSH/HTTP)

* **Private EC2 Instance**

  * Cannot be accessed directly from the internet
  * Sends outbound traffic through NAT Gateway

* **Routing Logic**

  * Public Subnet → Internet Gateway
  * Private Subnet → NAT Gateway → Internet

---

## 🖼️ Architecture Diagram

vpc_architecture.png

---

## 🛠️ Tech Stack

* Terraform
* AWS (VPC, EC2, Subnets, Route Tables, NAT Gateway)
* Networking Concepts (CIDR, Routing, Isolation)

---

## ⚙️ Infrastructure Components

### 🔹 VPC

* CIDR Block: `10.0.0.0/16`

### 🔹 Subnets

* Public Subnet: `10.0.1.0/24`
* Private Subnet: `10.0.2.0/24`

### 🔹 Gateways

* Internet Gateway (IGW)
* NAT Gateway

### 🔹 Route Tables

* Public Route Table → IGW
* Private Route Table → NAT Gateway

### 🔹 EC2 Instances

* Public EC2 Instance (Internet accessible)
* Private EC2 Instance (No direct internet access)

---

## 🚀 How to Run the Project

### 1️⃣ Clone Repository

```bash
git clone https://github.com/Vaishnavi-Kammari/aws-vpc-project.git
cd aws-vpc-project
```

### 2️⃣ Initialize Terraform

```bash
terraform init
```

### 3️⃣ Preview Changes

```bash
terraform plan
```

### 4️⃣ Apply Configuration

```bash
terraform apply
```

---

## 👩‍💻 Author

Vaishnavi
