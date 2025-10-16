---
title : "Clean up resources"
date : "2024-01-01"
weight : 6
chapter : false
pre : " <b> 6. </b> "
---

## Clean up resources

### Delete SNS Subscriber

- Access AWS SNS Console.
- Select Subscription in the left sidebar.
- Select and delete related Subscribers.

![Clean](/images/6-clean/1.png?featherlight=false&width=90pc)

### Delete SNS Topic

- Access AWS SNS Console.
- Select Topics in the left sidebar.
- Select and delete related Topic.

![Clean](/images/6-clean/2.png?featherlight=false&width=90pc)
![Clean](/images/6-clean/3.png?featherlight=false&width=90pc)
![Clean](/images/6-clean/4.png?featherlight=false&width=90pc)

### Delete Backup Vaults

- Access AWS Backup Console.
- Select Backup Vaults in the left sidebar.
- Select the Backup Vault created in this lab.

![Clean](/images/6-clean/5.png?featherlight=false&width=90pc)

- On the Backup Vault information page.
- In the **Recovery points** section, check **Recovery points**, select Actions, and select Delete.

![Clean](/images/6-clean/6.png?featherlight=false&width=90pc)

- Next, in the Backups section, after deleting **Recovery points**, select **Delete vault**.

![Clean](/images/6-clean/7.png?featherlight=false&width=90pc)

![Clean](/images/6-clean/8.png?featherlight=false&width=90pc)

### Delete Backup Plans

- Access AWS Backup Console.
- Select Backup plans in the left sidebar.
- Select the Backup plan created in this lab.

![Clean](/images/6-clean/9.png?featherlight=false&width=90pc)
![Clean](/images/6-clean/10.png?featherlight=false&width=90pc)
![Clean](/images/6-clean/11.png?featherlight=false&width=90pc)

- In the Resource assignments section, select the created resource and select Delete.

![Clean](/images/6-clean/12.png?featherlight=false&width=90pc)

- On the Backup plan information page, select Delete.

![Clean](/images/6-clean/13.png?featherlight=false&width=90pc)

### Delete CloudFormation Stack

- Access **AWS CloudFormation**.
- Select the lab's **Stack**.
- Select **Delete**.

![Clean](/images/6-clean/14.png?featherlight=false&width=90pc)
![Clean](/images/6-clean/15.png?featherlight=false&width=90pc)

### Delete CloudWatch Logs

- Access **AWS CloudWatch**.
- Select **Logs**.
- Select **/aws/lambda/RestoreTestFunction.**
- Select **Actions**, select **Delete Log Group**.
- Select **Yes, Delete**.

![Clean](/images/6-clean/16.png?featherlight=false&width=90pc)
![Clean](/images/6-clean/17.png?featherlight=false&width=90pc)