 AWS_cost_optimization
cost optimization project
AWS Cloud Cost Optimization – Identifying Stale EBS Snapshots with example

Scenario  
Imagine a mid-sized e-commerce company that runs seasonal sales campaigns. During peak sales periods ex: Black Friday, Christmas, they scale up their infrastructure by launching multiple EC2 instances to handle high traffic. As part of their backup strategy, they create EBS snapshots regularly to ensure data protection.  

Once the sale is over, they scale down by terminating EC2 instances that are no longer needed. However, the snapshots taken during that period remain in their AWS environment, incurring unnecessary storage costs. These stale snapshots can accumulate over time, leading to significant costs if left unmanaged.  

Solution: Automating Cleanup with AWS Lambda  
To optimize storage costs, the company deploys a Lambda function that runs periodically to identify and delete unused snapshots. Here’s how it works:  

1. Fetch all EBS Snapshots: The Lambda function lists all EBS snapshots owned by the AWS account.  
2. Check for Active EC2 Instances: It retrieves a list of active EC2 instances (both running and stopped).  
3. Identify Stale Snapshots: For each snapshot, the function checks if its associated EBS volume is still linked to any active instance.  
4. Delete Unused Snapshots: If a snapshot is not tied to an active volume, it is flagged as stale and deleted.  
Real-World Benefits
By running this automated cleanup, the e-commerce company:  
1.Saves thousands of dollars in unused storage costs.  
2.Reduces operational overhead, as engineers don’t have to manually track and delete snapshots.  
3.Ensures compliance by keeping only necessary backups while discarding outdated ones.  

This method is crucial for businesses that operate in dynamic cloud environments, where resources are frequently created and terminated. **Proactively managing stale resources can result in substantial AWS cost savings.
