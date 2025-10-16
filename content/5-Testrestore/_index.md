---
title : "Test Restore"
date : "2024-01-01"
weight : 5
chapter : false
pre : " <b> 5. </b> "
---

# Test Restore

To ensure the usefulness of data backups, testing backups is crucial. Without testing, there may be cases where data cannot be recovered from backups. This can lead to situations where workloads are affected due to the need to restore from backup, but the backup is corrupted or the recovery time (RTO) is exceeded. To avoid this situation, backups need to be tested regularly to ensure recoverability.

In this lab, AWS Lambda is used to automatically test all created backups, ensuring that the recovery process is successful and resources created during testing are then deleted to save costs. Automating this process with trigger notifications will help ensure operation at the lowest cost and operations teams have knowledge about the status of backup and restore.

During the restore testing process, it is important to identify the necessary criteria for successfully restoring data from the backed-up resource. This will depend on many factors such as data source, data type, error tolerance, and many other factors. Organizations and workload owners will be responsible for determining these success criteria.

For example, in this lab, an EC2 instance has been created and is running a simple web application. In this case, the successful recovery criteria is determined by checking whether the application is running on the restored resource. If any critical application files are missing on the restored resource, the health check will fail, indicating there is an issue with the backup.

#### Test Restore

Within the scope of this lab, we will simulate the action that AWS Backup performs when creating a backup of the data source. First, we will create an on-demand backup to test whether the backup is successful. When the backup is complete, a notification will be sent to report the completion of the backup and the Lambda function will be triggered. The Lambda function will make API calls to start the restore process from the backup. This ensures the accuracy of the backup. After the restore process is complete, another notification will be sent to confirm this and the Lambda function will be called again to clean up the newly created resources during the restore process. When the cleanup process is complete, a final notification will be sent to confirm the cleanup.

1. Access **AWS Management Console**:

   - Open **AWS Backup** interface
   - Select **CREATE AN ON-DEMAND BACKUP**

   ![AWS Backup](/images/5-test/1.png?featherlight=false&width=90pc)

2. In the **RESOURCE TYPE** section, select **EC2**, then paste the **Instance ID** from the **Output** section of the CloudFormation Stack.

   - In **BACKUP WINDOW**, select **CREATE BACKUP NOW**.
   - For **Backup Vault**, select **BACKUP-LAB-VAULT.**
   - Use the default IAM role.
   - Select **CREATE ON-DEMAND BACKUP**

   ![AWS Backup](/images/5-test/2.png?featherlight=false&width=90pc)
   ![AWS Backup](/images/5-test/3.png?featherlight=false&width=90pc)
   ![AWS Backup](/images/5-test/4.png?featherlight=false&width=90pc)

3. In **Jobs**, select **Backup jobs**, and wait until the status changes to **Completed**

   ![AWS Backup](/images/5-test/5.png?featherlight=false&width=90pc)

4. Click on **Backup jobs ID** to view details.

   ![AWS Backup](/images/5-test/6.png?featherlight=false&width=90pc)

5. Check email to confirm notifications.

   ![AWS Backup](/images/5-test/7.png?featherlight=false&width=90pc)

6. Check email related to **Restore Test Status**.

   ![AWS Backup](/images/5-test/8.png?featherlight=false&width=90pc)
   ![AWS Backup](/images/5-test/7.png?featherlight=false&width=90pc)
   ![AWS Backup](/images/5-test/8.png?featherlight=false&width=90pc)

7. Return to **AWS Management Console**:

   - Find and select **CloudWatch**

   ![AWS Backup](/images/5-test/9.png?featherlight=false&width=90pc)

8. In the **CloudWatch** interface:

    - Select **Logs**
    - Select **Log groups**
    - Select the lab's **Log group**. (```/aws/lambda/RestoreTestFunction-<YOUR CLOUDFORMATION STACK NAME>```)

    ![AWS Backup](/images/5-test/10.png?featherlight=false&width=90pc)

9. In the **Log groups** interface:

    - Select **Log streams**
    - Select the lab's **Log stream**.

    ![AWS Backup](/images/5-test/11.png?featherlight=false&width=90pc)

10. View **Log Events** details.

    ![AWS Backup](/images/5-test/12.png?featherlight=false&width=90pc)

By completing the above steps, you have successfully deployed **AWS BACKUP FOR THE SYSTEM**.