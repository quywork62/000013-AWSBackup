---
title : "Create S3 Bucket"
date : "2024-01-01"
weight : 1
chapter : false
pre : " <b> 2.1 </b> "
---

#### Create S3 Bucket

In this section, we will use **CloudFormation** to create resources for the lab. The **CloudFormation** stack will create service resources such as an **EC2 instance**, **SNS Topic**, and **Lambda Function**.

## Step 1: Download Template and Lambda Function

Download the [CloudFormation template and Lambda Function](https://github.com/AWS-First-Cloud-Journey/Backup-Plan/archive/refs/heads/master.zip).

1. After downloading the **CloudFormation template and Lambda Function** from the link above:

   - We will create an **S3 bucket** to store the source files.
   - Access the **AWS Management Console**, find and select **S3**.

![AWS Backup](/images/2.1-preparation/1.png?featherlight=false&width=90pc)

2. In the **S3** interface, select **Create bucket**.

![AWS Backup](/images/2.1-preparation/2.png?featherlight=false&width=90pc)

3. In the **Create bucket** interface:

   - Enter a **Bucket name**. It must be a unique name; you can choose any name you like (If duplicate, it will cause an error and the bucket cannot be created).

![AWS Backup](/images/2.1-preparation/3.png?featherlight=false&width=90pc)

**Note:**
In this workshop, we will use the Singapore region (ap-southeast-1). If you want to use another region, make sure to switch to the region you want to use when creating workshop-related resources.

4. Keep the default configuration.

![AWS Backup](/images/2.1-preparation/4.png?featherlight=false&width=90pc)
![AWS Backup](/images/2.1-preparation/5.png?featherlight=false&width=90pc)

5. In the **Default encryption** section, select **Disable**, then select **Create bucket**.

![AWS Backup](/images/2.1-preparation/6.png?featherlight=false&width=90pc)

6. Complete creating the **S3 bucket**.

![AWS Backup](/images/2.1-preparation/7.png?featherlight=false&width=90pc)

7. Create a storage folder.

![AWS Backup](/images/2.1-preparation/7.png?featherlight=false&width=90pc)

8. In the folder creation interface:

   - Enter the folder name **`Backup Plan`**.
   - Select **Create folder**.

![AWS Backup](/images/2.1-preparation/8.png?featherlight=false&width=90pc)
![AWS Backup](/images/2.1-preparation/9.png?featherlight=false&width=90pc)

9. Complete creating the folder.

![AWS Backup](/images/2.1-preparation/10.png?featherlight=false&width=90pc)

10. In the newly created folder, **Upload** the downloaded and extracted files.

![AWS Backup](/images/2.1-preparation/11.png?featherlight=false&width=90pc)

11. In the **Upload** section:

    - Select **Add files**.
    - Choose the files you want to upload.
    - Select **Upload**.

![AWS Backup](/images/2.1-preparation/12.png?featherlight=false&width=90pc)
![AWS Backup](/images/2.1-preparation/13.png?featherlight=false&width=90pc)
![AWS Backup](/images/2.1-preparation/14.png?featherlight=false&width=90pc)
![AWS Backup](/images/2.1-preparation/15.png?featherlight=false&width=90pc)

12. Complete uploading the files.

![AWS Backup](/images/2.1-preparation/16.png?featherlight=false&width=90pc)

13. Configure **Permissions** for the **S3 bucket**:

    - For **Block public access (bucket settings)**.

![AWS Backup](/images/2.1-preparation/17.png?featherlight=false&width=90pc)

14. Uncheck **Block all public access**:

    - Then select **Save changes**.

![AWS Backup](/images/2.1-preparation/18.png?featherlight=false&width=90pc)

15. Confirm by selecting **confirm** and then select **Confirm**.

![AWS Backup](/images/2.1-preparation/19.png?featherlight=false&width=90pc)

16. Next, configure the **Bucket policy**:

    - Select **Edit**.

![AWS Backup](/images/2.1-preparation/20.png?featherlight=false&width=90pc)

17. In the **Edit bucket policy** interface:

    - Enter the following code and replace with your **Bucket ARN**.

    ```json
    {
        "Version": "2012-10-17",
        "Statement": [
            {
                "Sid": "PublicReadGetObject",
                "Effect": "Allow",
                "Principal": "*",
                "Action": [
                    "s3:GetObject"
                ],
                "Resource": [
                    "arn:aws:s3:::Bucket-Name/*"
                ]
            }
        ]
    }
    ```

![AWS Backup](/images/2.1-preparation/21.png?featherlight=false&width=90pc)

18. Select **Save changes**.

![AWS Backup](/images/2.1-preparation/22.png?featherlight=false&width=90pc)

19. Verify that **Permissions** are set to **Public**.

![AWS Backup](/images/2.1-preparation/23.png?featherlight=false&width=90pc)

20. Copy the path information of **lambda_function.zip**.

![AWS Backup](/images/2.1-preparation/24.png?featherlight=false&width=90pc)

21. Copy the **Object URL** information of the **backup-lab.yaml** file.

![AWS Backup](/images/2.1-preparation/25.png?featherlight=false&width=90pc)