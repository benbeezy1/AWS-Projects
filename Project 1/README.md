<h1>Hosting a Static Website using S3</h1>

 ### [YouTube Demonstration](https://youtu.be/7eJexJVCqJo)

<h2>Description</h2>
This project demonstrates how to host a fully static website using <b>Amazon S3</b>.  
The goal is to understand how S3 can be used as a low-cost, highly available hosting solution for HTML, CSS, JavaScript, and media files.  
The project covers bucket creation, static website configuration, file uploads, permission settings, and testing the public endpoint.
<br /><br />

<h2>AWS Services Used</h2>

- <b>Amazon S3</b> – static hosting, object storage  
- <b>IAM</b> – access control (optional)  
- <b>Amazon CloudFront</b> (optional enhancement)  
- <b>Route 53</b> (optional for custom domain)
<br />

<h2>Environments Used</h2>

- <b>AWS Management Console</b>  
- <b>Local HTML/CSS/JS files</b>
<br />

<h2>Project Walk-through</h2>

<p align="center">
Create an S3 Bucket: <br/>
<img src="https://i.imgur.com/knXv373.jpeg" height="80%" width="80%" alt="Create S3 Bucket"/>
<br /><br />

<p align="center">
Enable Static Website Hosting: <br/>
<img src="INSERT-IMAGE-LINK-HERE" height="80%" width="80%" alt="S3 Static Hosting"/>
<br /><br />

<p align="center">
Upload Website Files (HTML/CSS/JS): <br/>
<img src="INSERT-IMAGE-LINK-HERE" height="80%" width="80%" alt="Upload Files to S3"/>
<br /><br />

<p align="center">
Configure Bucket Policy to Allow Public Read Access: <br/>
<img src="INSERT-IMAGE-LINK-HERE" height="80%" width="80%" alt="Bucket Policy"/>
<br /><br />
  
<p align="center">
Access the Public Website Endpoint: <br/>
<img src="INSERT-IMAGE-LINK-HERE" height="80%" width="80%" alt="S3 Website Endpoint"/>
<br /><br />
</p>

<h2>Skills Learned</h2>

- Hosting static websites using S3  
- Configuring bucket policies  
- Understanding S3 object permissions  
- Managing public access settings  
- Using the S3 website endpoint  
- (Optional) Integrating CloudFront for CDN & HTTPS  
- (Optional) Mapping a custom domain with Route 53
<br />

<h2>Future Enhancements</h2>

- Add <b>CloudFront</b> CDN for faster global delivery  
- Configure <b>HTTPS</b> using ACM certificates  
- Use <b>Route 53</b> to map a custom domain  
- Automate deployment with <b>Terraform</b> or <b>CloudFormation</b>  
- Add a CI/CD pipeline for versioned website deployments  
