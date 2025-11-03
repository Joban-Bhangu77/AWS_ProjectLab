
# 🚀 Launching a Linux EC2 Instance on AWS — Step-by-Step Guide

## 🧭 Overview
This project demonstrates how to **launch and configure a Linux EC2 instance** on AWS, step by step.  
You’ll learn how to set up networking, key pairs, and security groups, then connect securely using SSH or the AWS Console.  

> 💡 EC2 (Elastic Compute Cloud) is a core AWS service that lets you run virtual servers with flexible compute power and scalability.

---

## 🧩 Step 1: Login to AWS Management Console
1. Go to [AWS Management Console](https://aws.amazon.com/console/).  
2. Sign in using your IAM or Root credentials.  
3. Search for **EC2** in the AWS search bar and open the **EC2 Dashboard**.

📸 **Screenshot Placeholder:**  
`![Step 1 Screenshot](Screenshots/Step1_AWSConsole.jpg)`

---

## ⚙️ Step 2: Launch a New EC2 Instance
1. From the EC2 dashboard, click **Launch Instance**.  
2. Enter a name for your instance, e.g., `My-Linux-EC2`.  
3. Under **Application and OS Images (AMI)**, select **Amazon Linux 2 AMI (Free tier eligible)**.

📸 **Screenshot Placeholder:**  
`![Step 2 Screenshot](Screenshots/Step2_LaunchInstance.jpg)`

---

## 🧮 Step 3: Choose an Instance Type
- Select **t2.micro** (Free Tier eligible).  
- Click **Next**.

📸 **Screenshot Placeholder:**  
`![Step 3 Screenshot](Screenshots/Step3_InstanceType.jpg)`

---

## 🔐 Step 4: Create or Select a Key Pair
1. Create a new key pair if you don’t have one:
   - **Key pair name:** `MyKeyPair`
   - **Type:** RSA
   - **Format:** `.pem`
2. Download and securely store the `.pem` file for SSH access.

📸 **Screenshot Placeholder:**  
`![Step 4 Screenshot](Screenshots/Step4_KeyPair.jpg)`

---

## 🌐 Step 5: Configure Network Settings
1. Under **Network settings**, click **Edit**.  
2. Choose a **VPC** with:
   - A **Public Subnet**  
   - **Auto-assign Public IP:** Enabled  
3. Create a new **Security Group**:
   - Name: `EC2-SG`
   - Add inbound rule:
     - **Type:** SSH  
     - **Port:** 22  
     - **Source:** My IP (for security)

📸 **Screenshot Placeholder:**  
`![Step 5 Screenshot](Screenshots/Step5_NetworkSettings.jpg)`

---

## 💾 Step 6: Configure Storage
- Keep the default storage (8 GiB gp3).  
- Click **Next** or continue.

📸 **Screenshot Placeholder:**  
`![Step 6 Screenshot](Screenshots/Step6_Storage.jpg)`

---

## 🚀 Step 7: Launch the Instance
- Review all settings.  
- Click **Launch Instance**.  
- When the instance launches, click **View all instances**.

📸 **Screenshot Placeholder:**  
`![Step 7 Screenshot](Screenshots/Step7_LaunchSuccess.jpg)`

---

## 🔍 Step 8: Verify Instance Details
- Ensure your instance is in **running state**.  
- Confirm:
  - **Instance State:** Running  
  - **Public IPv4 Address:** Assigned  
  - **Public DNS:** Available  

📸 **Screenshot Placeholder:**  
`![Step 8 Screenshot](Screenshots/Step8_InstanceDetails.jpg)`

---

## 🧠 Step 9: Connect to Your Instance

### 🔹 Option 1 — EC2 Instance Connect (Browser)
1. Select your instance and click **Connect** → **EC2 Instance Connect**.  
2. Use the username:
   ```bash
   ec2-user

3. Click Connect to open the terminal.

📸 Screenshot Placeholder:
![Step 9a Screenshot](Screenshots/Step9_EC2Connect.jpg)

🌍 Step 10: Verify Internet Connectivity:

Run the following command:

ping google.com

If you receive replies, your instance has outbound internet access ✅.

📸 Screenshot Placeholder:
![Step 10 Screenshot](Screenshots/Step10_PingResult.jpg)

✅ Conclusion

You have successfully:

Launched a Linux EC2 Instance

Configured networking and SSH access

Verified connectivity and public access

🌟 Next Steps: Try deploying a simple web server (Apache/Nginx) on your EC2 instance and host your first web app.

📂 Folder Structure
 
AWS_ProjectLab/
 ├── AWS_EC2_Linux_Instance/
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
 │   └── Notes.txt


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

