# AWS IAM Identity-Based Policies: Practical Lab

## Overview
This hands-on lab demonstrates how to **securely manage AWS S3 access using Identity-Based IAM policies**.  
In this scenario, the user `Alice` is granted **full access to a specific S3 bucket** (`cloudlabs-project-data`) while **all other buckets, including newly created ones, are explicitly denied**.

**Key Learning Outcomes:**
- Understanding and creating **Identity-Based Policies** in AWS.
- Implementing **Explicit Deny** rules to enforce strict access control.
- Applying the **Principle of Least Privilege** to improve security.
- Hands-on experience with real-world IAM policy design for S3.

---

## Blog Post
For a detailed explanation of this lab and step-by-step guidance, check out my blog post:  
[Mastering AWS IAM: Identity-Based Policies Lab](https://medium.com/@jobanjitsinghamritsar/hands-on-aws-iam-lab-enforcing-identity-based-access-control-85b7f7f5bf78)  

---
'''
## Project Structure
AWS_ProjectLab/
└── 📂 AWS_IAM_Identity_Lab/
├── 🖼️ Screenshots/
│ ├── 🧩 AWS_Identity&AccessManagement.png
│ ├── 👤 AWS_IAM_Admin_Account.png
│ ├── 🪪 Step1_CreateUser.png
│ ├── ✅ Step2_AllowPolicy.png
│ ├── ⛔ Step3_DenyPolicy.png
│ ├── 🔗 Step4_AttachPolicies.png
│ ├── 🪣 Step5_AllowedBucket.png
│ └── 🚫 Step6_DeniedBucket.png
├── 📄 README.md
└── 📚 [Other AWS Labs Coming Soon]

'''
---

## Step 1: Create IAM User
1. Navigate to **IAM → Users → Create User**.  
2. Enter username: `Alice`.  
3. Select **AWS Management Console access**.  
4. Set a custom password.  
5. Skip attaching permissions for now.  

📸 *Screenshot Placeholder:* `Screenshots/Step1_CreateUser.png`

---

## Step 2: Create Allow Policy for Specific Bucket
1. Navigate to **IAM → Policies → Create Policy → JSON tab**.  
2. Paste the following JSON:

```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "AllowFullAccessSpecificBucket",
            "Effect": "Allow",
            "Action": [
                "s3:ListBucket",
                "s3:GetObject",
                "s3:PutObject"
            ],
            "Resource": [
                "arn:aws:s3:::cloudlabs-project-data",
                "arn:aws:s3:::cloudlabs-project-data/*"
            ]
        }
    ]
}

Name policy: AllowCloudLabsDataAccess

Description: Full access to cloudlabs-project-data bucket.

📸 Screenshot Placeholder: Screenshots/Step2_AllowPolicy.png

Step 3: Create Deny Policy for All Other Buckets

Navigate to IAM → Policies → Create Policy → JSON tab.

Paste the following JSON:
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "DenyAllOtherBuckets",
            "Effect": "Deny",
            "Action": "s3:*",
            "NotResource": [
                "arn:aws:s3:::cloudlabs-project-data",
                "arn:aws:s3:::cloudlabs-project-data/*"
            ]
        }
    ]
}

Step 4: Attach Policies to Alice

Navigate to IAM → Users → Alice → Permissions → Add permissions.

Attach both policies:

AllowCloudLabsDataAccess

DenyAllOtherS3Buckets

Important: Ensure Alice does not belong to any group or have other policies granting broader S3 access.

📸 Screenshot Placeholder: Screenshots/Step4_AttachPolicies.png

Step 5: Test Access

Log in as Alice and verify access:
| Action                   | Bucket                 | Expected Result |
| ------------------------ | ---------------------- | --------------- |
| List / Get / Put Objects | cloudlabs-project-data | ✅ Allowed       |
| Access / Upload          | Any other bucket       | ❌ Denied        |

Conclusion

Identity-Based Policies provide fine-grained control over user access in AWS.
Combining Allow for required resources and Explicit Deny for all others ensures strong security.
Any new S3 buckets created in the account are automatically inaccessible to Alice.
This lab demonstrates a real-world approach to securing AWS resources while adhering to the least privilege principle.

6. References

AWS IAM User Guide – Identity-Based Policies
https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html

AWS S3 Bucket Policies vs IAM Policies
https://docs.aws.amazon.com/AmazonS3/latest/userguide/using-iam-policies.html

AWS IAM Policy Elements Reference
https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_elements.html

AWS IAM Best Practices
https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html

AWS S3 Security and Access Control
https://docs.aws.amazon.com/AmazonS3/latest/userguide/security-best-practices.html
