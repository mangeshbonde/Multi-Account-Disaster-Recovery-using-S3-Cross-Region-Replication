# 🌐 Multi-Account Disaster Recovery using S3 Cross-Region Replication (CRR)

## 📌 Overview
This project demonstrates how to implement a **multi-account disaster recovery (DR) strategy** using **Amazon S3 Cross-Region Replication (CRR)**.  
The solution automatically and securely replicates objects between **different AWS accounts and regions**, ensuring **zero data loss**, high availability, and disaster recovery readiness.

---

## 🎯 Problem Statement
Organizations often face challenges such as:
- Data loss due to regional outages
- Accidental deletion or corruption
- Lack of cross-account backup strategy
- Manual and unreliable recovery processes

This project solves these problems by enabling **automated, cross-account, cross-region data replication**.

---

## ✅ Solution Summary
- Source S3 bucket in **Primary AWS Account**
- Destination S3 bucket in **Secondary AWS Account**
- Cross-Region Replication (CRR) enabled
- IAM roles and bucket policies for secure access
- Continuous, automatic replication of objects

---

## 🛠️ AWS Services Used
- Amazon S3
- S3 Cross-Region Replication (CRR)
- AWS IAM
- AWS KMS (optional, for encryption)
- AWS CloudWatch (monitoring)

---

## 🧩 Architecture Flow
1. Objects are uploaded to the **source S3 bucket**
2. S3 automatically replicates objects to the **destination bucket**
3. Replication happens across:
   - Different AWS accounts
   - Different AWS regions
4. Destination bucket acts as a **Disaster Recovery backup**

---

## ⚙️ Prerequisites
- Two AWS accounts (Source & Destination)
- S3 buckets created in different regions
- IAM permissions for S3 and replication
- (Optional) KMS keys for encryption

---

## 🧪 Implementation Steps

### 1️⃣ Create S3 Buckets
- Create a source bucket in **Primary Account**
- Create a destination bucket in **Secondary Account**
- Enable **Versioning** on both buckets (mandatory)

---

### 2️⃣ Configure IAM Role for Replication
- Create an IAM role in the source account
- Grant permissions to:
  - Read objects from source bucket
  - Write objects to destination bucket
- Add trust relationship for S3 service

---

### 3️⃣ Configure Bucket Policy (Destination Account)
- Allow replication role to:
  - Put objects
  - Replicate delete markers
  - Replicate object versions

---

### 4️⃣ Enable Cross-Region Replication
- Go to source bucket → Management → Replication rules
- Add replication rule:
  - Select destination bucket (cross-account)
  - Choose IAM replication role
  - Enable replication for all objects

---

### 5️⃣ Test Replication
- Upload files to source bucket
- Verify objects appear automatically in destination bucket
- Confirm metadata and versions are replicated

---

## 📈 Benefits
- Zero data loss
- Automated disaster recovery
- Multi-account isolation
- High availability
- Enterprise-grade data protection
- No manual backup process

---

## 🔐 Security Best Practices
- Use least-privilege IAM roles
- Enable bucket versioning
- Encrypt data using SSE-S3 or SSE-KMS
- Enable access logging and monitoring

---

## 📂 Repository Structure
.
├── README.md
├── bucket-policies/
├── iam-roles/
└── screenshots/


---

## 🧠 Key Learnings
- Multi-account AWS architecture
- Cross-region replication
- Disaster recovery planning
- IAM security and access control
- Data durability and availability

---

## 🏷️ Tags / Topics
aws  
amazon-s3  
cross-region-replication  
disaster-recovery  
multi-account-architecture  
cloud-security  
data-backup  

---

## 🤝 Contribution
This repository is intended for learning and demonstration purposes.  
Feel free to fork, explore, and enhance the architecture.

---

## 📜 License
This project is licensed under the MIT License.

