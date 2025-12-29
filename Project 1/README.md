<h1>Create a Static Website using S3</h1>

<h2>Description</h2>
This project demonstrates how to host a fully static website using <b>Amazon S3</b>.  
The goal is to understand how S3 can be used as a low-cost, highly available hosting solution for HTML, CSS, JavaScript, and media files.
The project covers bucket creation, S3 bucket policy configuratioion, static website configuration, file uploads, permission settings, and testing the public endpoint.
<br /><br />

<h2>AWS Services Used</h2>

- <b>Amazon S3</b> – static hosting, object storage 
<br />

<h2>Environments Used</h2>

- <b>AWS Management Console</b>  
- <b>VS Code</b>
<br />

<h2>Project Walk-through</h2>

<p align="center">
<b>Create an S3 Bucket</b>: (Name: ben-website-001) <br/>
<img src="https://i.imgur.com/p61llgz.png" height="80%" width="80%" alt="Create S3 Bucket"/>
 <img src="https://i.imgur.com/6XjNO9z.png" height="80%" width="80%" alt="Create S3 Bucket"/>
<br /><br />

<p align="center">
<b>Enable Static Website Hosting and allow public access</b>: <br/>
<img src="https://i.imgur.com/yed2Hr9.png" height="80%" width="80%" alt="S3 Static Hosting"/>
<img src="https://i.imgur.com/02hvdgO.png" height="80%" width="80%" alt="S3 Static Hosting"/>
 <img src="https://i.imgur.com/VVPIesQ.png" height="80%" width="80%" alt="S3 Static Hosting"/>
 <b>word</b>
 <br /><br />

<p align="center">
<b>Add a bucket policy to allow public access to content in the bucket</b>: "Principal "*" allows everyone access". Resource: "this should be the arn of the specific bucket you want public access to" <br/>
<img src="https://i.imgur.com/PqDdwpD.png" height="80%" width="80%" alt="Upload Files to S3"/>
<br /><br />

<p align="center">
<b>Create and upload the website assets</b>: I created the error.html and index.html files on VScode and uploaded those files to the bucket. Here, website assets could include; images, scripts, fonts, style sheet, bascially any files that contribute to the visuals and funtionality of the website <br/>
<img src="https://i.imgur.com/eyASz95.png" height="80%" width="80%" alt="Bucket Policy"/>
 <img src="https://i.imgur.com/2FjhBb9.png" height="80%" width="80%" alt="Bucket Policy"/>
 <img src="https://i.imgur.com/06dhldx.png" height="80%" width="80%" alt="Bucket Policy"/>
<br /><br />
  
<p align="center">
<b>Test and Access the Public Website Endpoint</b>: http://ben-website-001.s3-website-us-east-1.amazonaws.com (This endpoint is the url generated from enabling static hosting <br/>
<img src="https://i.imgur.com/Rz84bLy.png" height="80%" width="80%" alt="S3 Website Endpoint"/> <br /><br />
<b>Inputing an unavaible endpoint</b>; http://ben-website-001.s3-website-us-east-1.amazonaws.com/aboutus.html. The browser can’t find the path to the /aboutus location, so the error.html page is returned as expected.
 <img src="https://i.imgur.com/rEarHyt.png" height="80%" width="80%" alt="S3 Website Endpoint"/>
<br /><br />
</p>

<h2>Skills Learned</h2>

- Hosting static websites using S3  
- Configuring bucket policies  
- Understanding S3 object permissions to allow or deny publich access 
- Managing public access settings  
- Using the S3 website endpoint  
<br />

<h2>Task Completed</h2>

- Created an S3 bucket.
- Configured the S3 bucket as a static website and allowed public access.
- Added a bucket policy.
- Created and uploaded the website assets.
- Tested the Amazon S3 static website. 
