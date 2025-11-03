# 🚀 AWS EC2 Instance Launch – Step-by-Step Lab

## 🧩 Overview
This project demonstrates how to **create, configure, and connect** an Amazon EC2 Linux instance on AWS using the **AWS Management Console**.  
It includes every step from launching an instance, configuring security groups, creating key pairs, and connecting via SSH or EC2 Instance Connect.  

---

## 🧠 Learning Objectives
- Understand the process of launching an EC2 instance  
- Configure VPC, Subnets, and Security Groups  
- Connect to your EC2 instance securely using SSH  
- Verify connectivity using `ping` and command-line tools  
- Document and visualize every stage with screenshots  

---

## 🛠️ Project Steps

### 1. Login to AWS Console
- Navigate to the **AWS Management Console**  
- Select the **EC2** service under the “Compute” section  
📸 **Screenshot:** `AWS_HomePage.jpg`

---

### 2. Launch a New EC2 Instance
- Click **Launch Instance**  
- Select **Amazon Linux 2 AMI (Free Tier Eligible)**  
📸 **Screenshot:** `AWS_EC2_Launch.jpg`

---

### 3. Configure Instance Details
- Name your instance: `MyLinuxServer`  
- Choose an instance type (e.g., `t2.micro`)  
📸 **Screenshot:** `AWS_EC2_Name.jpg`

---

### 4. Configure Key Pair
- Create a new key pair (`.pem` file)  
- Download and store it securely  
📸 **Screenshot:** `AWS_KeyPair.jpg`

---

### 5. Configure Network and Security Group
- Attach your instance to a **Public VPC**  
- Create a **Security Group** to allow:
  - SSH (port 22) from your IP  
  - ICMP (ping) for connectivity testing  
📸 **Screenshot:** `AWS_Security_Group.jpg`

---

### 6. Configure Storage
- Use default 8 GB EBS storage or modify as needed  
📸 **Screenshot:** `AWS_Storage_Window.jpg`

---

### 7. Review and Launch
- Review configuration summary  
- Click **Launch Instance**  
📸 **Screenshot:** `AWS_EC2_Details.jpg`

---

### 8. Connect to Instance via SSH

#### 🔹 EC2 Instance Connect (Browser)
- Navigate to **Connect** → **EC2 Instance Connect**  
📸 **Screenshot:** `AWS_EC2_InstanceConnect_Via_SSH_Terminal.jpg`

#### 🔹 SSH via Terminal
```bash
ssh -i "my-key.pem" ec2-user@<Public-IP>
📸 Screenshot: AWS_SSH_Client.jpg


9. Verify Connectivity

Run the following command:

ping google.com


📸 Screenshot: AWS_Ping_Works.jpg

AWS_ProjectLab/
│
├── AWS_EC2/
│   ├── AWS_EC2_README_Screenshots/
│   │   ├── AWS_Amzon_EC2_Instance.jpg
│   │   ├── AWS_EC2_Details.jpg
│   │   ├── AWS_EC2_Instance_Connect.jpg
│   │   ├── AWS_EC2_InstanceConnect_Via_SSH_Terminal.jpg
│   │   ├── AWS_EC2_Launch.jpg
│   │   ├── AWS_EC2_Name.jpg
│   │   ├── AWS_HomePage.jpg
│   │   ├── AWS_KeyPair.jpg
│   │   ├── AWS_Ping_Works.jpg
│   │   ├── AWS_Security_Group.jpg
│   │   ├── AWS_SSH_Client.jpg
│   │   └── AWS_Storage_Window.jpg
│   │
│   ├── README.md
│
└── (Other Project Folders)


🧾 Conclusion

This project provided hands-on experience with AWS EC2 instance creation and SSH connectivity setup.
By following this structured workflow, users gain practical skills in managing cloud-based virtual servers within AWS.


📚 References
🔹 AWS EC2 Documentation

https://docs.aws.amazon.com/ec2/

🔹 Connect to Your Linux Instance

https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/AccessingInstancesLinux.html

🔹 AWS Free Tier

https://aws.amazon.com/free/

🔹 Amazon VPC Documentation

https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html

🔹 EC2 Security Groups

https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-security-groups.html

🔹 EC2 Key Pairs and SSH Keys

https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-key-pairs.html

🔹 AWS Cloud Practitioner Essentials

https://www.aws.training/Details/Curriculum?id=20685

🔹 Getting Started with Amazon EC2

https://aws.amazon.com/getting-started/hands-on/launch-linux-virtual-machine/

🔹 AWS YouTube Channel

https://www.youtube.com/@AWSEducate

