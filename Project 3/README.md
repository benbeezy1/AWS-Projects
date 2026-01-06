<h1>Introduction to AWS System Manager</h1>

<h2>Description</h2>
Monitoring and responding to operational changes are critical skills for maintaining a robust infrastructure. This lab provides hands-on experience on how to design and implement proactive monitoring and alerting for AWS resources using Amazon CloudWatch.  The project focuses on monitoring Amazon S3 API activity by enabling request-level metrics, visualizing usage patterns through custom dashboards, and configuring alarms that trigger notifications when predefined thresholds are exceeded. This project simulate real-world operational scenarios where early detection of unusual access patterns is critical for reliability, cost control, and security monitoring.



<br /><br />

<h2>AWS Services Used</h2>

- <b>Amazon S3</b> – scalable object storage service to store and retrieve unlimited amount of data. Here, S3 is used to create a bucket with advanced monitoring capabilities, including versioning, encryption, and object lock.
- <b>Amazon EC2 </b> – AWS compute service. Here, EC2 instance is used to interact with the S3 bucket, perform ListObjects operations, and demonstrate how to generate and analyze CloudWatch metrics.
- <b>Aamzon Simple Notification Service (SNS)</b> – A fully managed messaging service useful for decoupling architectures. Here, SNS is used to create a notification topic for the CloudWatch alarm
- <b>Amazon IAM </b> – Service to securely control access to AWS resources.
- <b> Amazon CloudWatch (metrics, dashboards, alarms) </b> – Service to securely control access to AWS resources.
<br />

<h2>Environments Used</h2>

- <b>AWS Management Console</b>
- <b>AWS CLI</b> 

<br />


<h2>Project Walk-through</h2>

<p align="center">
<b> Create and Configured an Amazon S3 bucket with Advanced monitoring capabilities and enabled request-level metrics to track object access activity</b> <br/>
<img src="https://i.imgur.com/sOpyyav.png" height="80%" width="80%" alt="Create S3 Bucket"/><br/>
 <img src="https://i.imgur.com/6XjNO9z.png" height="80%" width="80%" alt="Create S3 Bucket"/>
<br /><br />

<p align="center">
<b>Upload multiple test objects (3) to generate realistic S3 access patterns </b>: <br/>
<img src="https://i.imgur.com/DE7O43d.png" height="80%" width="80%" alt="S3 Static Hosting"/>
<img src="https://i.imgur.com/cLVS8hI.png" height="80%" width="80%" alt="S3 Static Hosting"/>
<img src="https://i.imgur.com/VVPIesQ.png" height="80%" width="80%" alt="S3 Static Hosting"/>

 <br /><br />

<p align="center">
<b>Created a CloudWatch dashboard + request metric filter to monitor ListObjects API calls across all bucket objects. This step focuses on creating a custom metric representation that captures the frequency of ListObjects calls, enabling you to visualize and monitor access patterns for your S3 bucket. <br/>
<img src="https://i.imgur.com/IaHa0Zm.png" height="80%" width="80%" alt="Upload Files to S3"/>
<img src="https://i.imgur.com/bKwYxUA.png" height="80%" width="80%" alt="Upload Files to S3"/>
<img src="https://i.imgur.com/tQmRvpf.png" height="80%" width="80%" alt="Upload Files to S3"/>
  
<br /><br />

<p align="center">
<b>Configured a CloudWatch alarm with a static threshold (>3 calls) to detect excessive ListObjects requests. This task demonstrates the critical process of establishing proactive monitoring by setting Amazon SNS to send email notifications when the alarm was triggered as S3 bucket access patterns deviate from expected norms. <br/>
 <img src="https://i.imgur.com/HdF8AA6.png" height="80%" width="80%" alt="Bucket Policy"/>
 <img src="https://i.imgur.com/0GNwOCV.png " height="80%" width="80%" alt="Bucket Policy"/>
 <img src="https://i.imgur.com/dx6NRj7.png " height="80%" width="80%" alt="Bucket Policy"/>
 <img src="https://i.imgur.com/7AwIHBR.png" height="80%" width="80%" alt="Bucket Policy"/>
 <img src="https://i.imgur.com/ZnoxWLx.png " height="80%" width="80%" alt="Bucket Policy"/>
 <img src="https://i.imgur.com/wY4xfO6.png" height="80%" width="80%" alt="Bucket Policy"/>
 <img src="https://i.imgur.com/f9pj57w.png" height="80%" width="80%" alt="Bucket Policy"/>
<br /><br />

  <p align="center">
<b>Validated the monitoring setup by generating S3 ListObjects calls from an EC2 instance using AWS CLI. Open EC2SessionManagerConnect URL and pasted the command "for i in {1..5}; do aws s3 ls s3://<BUCKET_NAME>; sleep 2; done"<br/>
<img src="https://i.imgur.com/uROzlEH.png" height="80%" width="80%" alt="S3 Website Endpoint"/> <br /><br />
<img src="https://i.imgur.com/4CwO7Ws.png" height="80%" width="80%" alt="S3 Website Endpoint"/> <br /><br />

  <p align="center">
<b>Observed alarm state transitions and confirmed notification delivery<br/>
 <img src="https://i.imgur.com/9Nk8mq8.png" height="80%" width="80%" alt="S3 Website Endpoint"/> <br /><br />
<img src="https://i.imgur.com/TqdxzXh.png" height="80%" width="80%" alt="S3 Website Endpoint"/> <br /><br />
  
  
</p>


---


<h2>Skills Learned</h2>

- Configuring and interpreting Amazon CloudWatch metrics  
- Designing CloudWatch dashboards for operational visibility
- Monitoring S3 API activity for security and usage analysis
- Integrating CloudWatch with Amazon SNS for notifications 
<br />

<h2>Task Completed</h2>

- Created and configured an Amazon S3 bucket with request metrics enabled.
- Applied a request metric filter to track ListObjects API calls.
- Uploaded test objects to the S3 bucket.
- Built a custom CloudWatch dashboard with S3 request metrics.
- Added ListRequests and AllRequests widgets to the dashboard.
- Configured a CloudWatch alarm with a defined threshold.
- Created and confirmed an SNS topic for email notifications.
- Triggered and verified alarm behavior through EC2-based testing.
