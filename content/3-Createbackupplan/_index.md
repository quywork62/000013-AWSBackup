---
title : "Create Backup plan"
date : "2024-01-01"
weight : 3
chapter : false
pre : " <b> 3. </b> "
---

#### Create Backup Plan

To ensure a perfect backup strategy, careful and multi-dimensional consideration is required. The success of an organization depends on many factors, including contingency strategy. The main factors affecting backup strategy include Recovery Time Objective (RTO) and Recovery Point Objective (RPO), which must be determined for each workload. RTO and RPO depend on the criticality of the work to the business, Service Level Agreements (SLA), and cost factors related to achieving RTO and RPO. Note that RTO and RPO need to be determined specifically for each specific workload, not for the entire organization or infrastructure.

#### Step 1: Access AWS Management Console

- Open **AWS Management Console**
- Find and select **AWS Backup**

![Step 1](/images/3-backupplan/1.png?featherlight=false&width=90pc)

#### Step 2: Select AWS Backup Plan

![Step 2](/images/3-backupplan/2.png?featherlight=false&width=90pc)

#### Step 3: Create backup plan

- In the **Create backup plan** interface, select **Build a new plan**
- For the **Backup plan name** field, enter **`BACKUP-LAB`**

![Step 3](/images/3-backupplan/3.png?featherlight=false&width=90pc)

#### Step 4: Configure backup rule

- Fill in **RULE NAME** as **BACKUP-LAB-RULE**
- In the **SCHEDULE** section, under **FREQUENCY**, select **Daily**
- Select **Use backup window defaults - recommended** to use default settings for backup window
- For **BACKUP VAULT**, select **CREATE NEW BACKUP VAULT**

![Step 4](/images/3-backupplan/4.png?featherlight=false&width=90pc)

#### Step 5: Name the Backup Vault

- Fill in **BACKUP VAULT NAME** as **`BACKUP-LAB-VAULT`**
- Select **(default) aws/backup**
- Select **CREATE BACKUP VAULT**

![Step 5](/images/3-backupplan/5.png?featherlight=false&width=90pc)
![Step 6](/images/3-backupplan/7.png?featherlight=false&width=90pc)

#### Step 6: Add Key and Value pairs for tags

- Select **Create plan**

![Step 6](/images/3-backupplan/8.png?featherlight=false&width=90pc)
![Step 7](/images/3-backupplan/9.png?featherlight=false&width=90pc)
![Step 7](/images/3-backupplan/10.png?featherlight=false&width=90pc)

### Step 7: Complete Backup Plan creation

- In the **RESOURCE ASSIGNMENTS** section, select **ASSIGN RESOURCES**

![Step 7](/images/3-backupplan/11.png?featherlight=false&width=90pc)

#### Step 8: Assign resources to Backup Plan

- Fill in **RESOURCE ASSIGNMENT NAME** as **BACKUP-RESOURCES**
- Select **DEFAULT ROLE** for **IAM ROLE**. If the role doesn't exist, AWS Backup will automatically create a new role with necessary permissions
- Add **Tag Key** and **Tag Value**
- Select **ASSIGN RESOURCES**

![Step 7](/images/3-backupplan/11.png?featherlight=false&width=90pc)
![Step 8](/images/3-backupplan/12.png?featherlight=false&width=90pc)

#### Step 9: Confirm and continue

- Confirm by selecting **Continue**

![Step 9](/images/3-backupplan/13.png?featherlight=false&width=90pc)

#### Step 10: Complete resource assignment

![Step 10](/images/3-backupplan/14.png?featherlight=false&width=90pc)