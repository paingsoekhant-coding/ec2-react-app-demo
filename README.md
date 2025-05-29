# 🚀 Deploy React App on AWS EC2 (Vite + NGINX)

This guide walks you through deploying a React app (built with Vite) on an AWS EC2 instance using NGINX.

---

## 🛠 Prerequisites

- AWS account
- EC2 instance (Ubuntu 20.04 or later)
- SSH access to the instance
- Basic knowledge of Linux commands

---

## 1. 🧱 Create a React App with Vite

```bash
npm create vite@latest my-react-app -- --template react
cd my-react-app
npm install
npm run build

##  2. 🚪 Log in to AWS Console

1. Go to [https://console.aws.amazon.com](https://console.aws.amazon.com)
2. Search for **EC2** in the AWS services search bar.
3. Click **EC2** to go to the EC2 Dashboard.

---

## 3. 🚀 Launch a New EC2 Instance

1. Click **"Launch instance"**
2. Fill in the required details:

   ### 📄 Name:
   - Example: `my-ec2-instance`

   ### 📦 Amazon Machine Image (AMI):
   - Choose: **Ubuntu Server 20.04 LTS (Free tier eligible)**

   ### 📈 Instance Type:
   - Select: `t2.micro` (Free tier eligible)

   ### 🔐 Key Pair (login):
   - Create new or choose existing key pair
   - Download the `.pem` file and store it securely

   ### 🔒 Network Settings:
   - Create or select security group
   - Allow:
     - ✅ SSH (port 22)
     - ✅ HTTP (port 80) — if you plan to serve web content

3. Click **"Launch instance"**

---

## 4. 🖥️ View Instance Details

1. Go back to the **EC2 Dashboard**
2. Click **"Instances"**
3. Locate your instance and note:
   - **Instance ID**
   - **Public IPv4 address**

---

## 5. 🔐 Connect to Your EC2 Instance

### 🔧 Set PEM permissions (on local machine):

```bash
chmod 400 your-key.pem



