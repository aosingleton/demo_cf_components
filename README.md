# demo_cf_components

### Purpose
- Creates basic dashboard for cloud resources
- Resources include:
    * EC2
    * S3
    * Lambda
    * SNS notifications

### Order & Configuration
- Files should be run in order of reliance.  If using aws console, it is suggested that you wait until each stack is completed before creating another with the network taking the longest.  Suggested order is as follows:
    1. base_network
    2. base_permissions
    3. base_ec2
    4. base_s3
    5. base_dashboard

- Before running this file confirm update to default resource values in                          the dashboard.yaml file (ec2 id, s3 name, email, etc).
- If done in cloudformation the default values can be changed.

### Resources
- [Dashboard and Metrics Structure](https://docs.aws.amazon.com/AmazonCloudWatch/latest/APIReference/CloudWatch-Dashboard-Body-Structure.html)
- [Standard Cloudwatch Metrics](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/viewing_metrics_with_cloudwatch.html)
- [Push Custom Metrics](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/publishingMetrics.html)

### Special Considerations
1. AWS cloudwatch creates a number of metrics when resources are created.  
2. Consideration should be given to the type of metrics needed as well as duration for measurement when the resource is created.  
3. Some resources can have detailed metrics/ logging turned on at creation (ec2, s3, etc.)
4. Some resources take time for initial metrics to propagate in cloudwatch (s3 & ec2).
