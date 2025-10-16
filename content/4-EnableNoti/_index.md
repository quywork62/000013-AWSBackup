---
title : "Set up notifications"
date : "2024-01-01"
weight : 4
chapter : false
pre : " <b> 4. </b> "
---

#### Set up notifications

In the cloud environment, you can easily set up notifications to know about important events in your workload. AWS Backup uses AWS SNS (Simple Notification Service) to send notifications related to ongoing backup activities. This allows you to monitor the status of backup jobs, restore operations, and potential errors, helping the Operations team respond promptly and appropriately.

#### Step 1: Open CloudShell

1. Open the email you received earlier to get the ARN of the SNS TOPIC you created

![AWS Backup](/images/4-notification/1.png?featherlight=false&width=90pc)
    
2. Edit the following AWS CLI command and replace it with the ARN of the SNS TOPIC you created and Region. This ARN can be found in the output section of the CloudFormation Stack.

    ```sh
    aws backup put-backup-vault-notifications --region ap-southeast-1 --backup-vault-name BACKUP-LAB-VAULT --backup-vault-events BACKUP_JOB_COMPLETED RESTORE_JOB_COMPLETED --sns-topic-arn <YOUR SNS TOPIC ARN>
    ```

3. After editing, execute the above command. This will activate notifications through SNS TOPIC every time a backup or restore job completes. This information helps the Operations team capture potential errors that may occur during backup or data restore processes.

   ![AWS Backup](/images/4-notification/2.png?featherlight=false&width=90pc)
   ![AWS Backup](/images/4-notification/3.png?featherlight=false&width=90pc)

#### Step 2: Check SNS interface

   ![AWS Backup](/images/4-notification/4.png?featherlight=false&width=90pc)

#### Step 3: Verify notifications

1. To verify that notifications have been successfully activated, you can use the following command. The output will include a section called SNSTopicArn, followed by the ARN of the SNS Topic that was created.

    ```sh
    aws backup get-backup-vault-notifications --backup-vault-name BACKUP-LAB-VAULT --region ap-southeast-1
    ```

   ![AWS Backup](/images/4-notification/5.png?featherlight=false&width=90pc)
   ![AWS Backup](/images/4-notification/6.png?featherlight=false&width=90pc)
   ![AWS Backup](/images/4-notification/7.png?featherlight=false&width=90pc)

2. Now, you have successfully activated notifications for BACKUP-LAB-VAULT, ensuring that the Operations team knows about the completion of backup and restore activities related to this vault as well as any errors related to those activities.

![AWS Backup](/images/4-notification/8.png?featherlight=false&width=90pc)