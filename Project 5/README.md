<h1>Building Your First Amazon Virtual Private Cloud (VPC)</h1>

<h2>Description</h2>
This project demonstrates building a foundational AWS network and deploying a simple web application connected to a database.
I created a custom VPC, configured networking components (subnets, routes, and internet gateway), provisioned an RDS database, and validated application connectivity through an Address Book web app.
<br /><br />

<h2>AWS Services Used</h2>

- <b>Amazon VPC</b> - custom networking, subnets, and route control
- <b>Amazon EC2</b> - web server host in a public subnet
- <b>Amazon RDS (MySQL)</b> - managed relational database in private subnets
- <b>Security Groups</b> - controlled traffic between web and database tiers
<br />

<h2>Environments Used</h2>

- <b>AWS Management Console</b>
- <b>Web browser for application validation</b>
<br />

<h2>Architectural Diamgram</h2>
<img src="https://i.imgur.com/5W01Xnw.png" height="80%" width="80%" alt="Create VPC"/>
<br />

<h2>Project Walk-through</h2>

<p align="center">
<b>Create base VPC</b>: Created a VPC with dedicated CIDR range to isolate the lab network. <br/>
<img src="https://i.imgur.com/P1mOquy.png" height="80%" width="80%" alt="Create VPC"/>
<br /><br />
</p>

<p align="center">
<b>Create public subnets for web server</b>: Defined public subnet ranges for one availability zone for the web server deployment. <br/>
<img src="https://i.imgur.com/H3OnaH8.png" height="80%" width="80%" alt="Create private subnets"/>
<img src="https://i.imgur.com/Z6kZsZ6.png" height="80%" width="80%" alt="Create private subnets"/>
<br /><br />
</p>

<p align="center">
<b>Attach Internet Gateway</b>: Created and connected the internet gateway to the VPC to enable external access paths. <br/>
<img src="https://i.imgur.com/QzuIRtX.png" height="80%" width="80%" alt="Attach Internet Gateway"/>
<img src="https://i.imgur.com/dIIgz1u.png" height="80%" width="80%" alt="Attach Internet Gateway"/>
<br /><br />
</p>

<p align="center">
<b>Configure public routing</b>: Added and verified the route table entry for internet-bound traffic. <br/>
<img src="https://i.imgur.com/1y6mtAn.png" height="80%" width="80%" alt="Public route table configuration"/>
<img src="https://i.imgur.com/Me8v4HV.png" height="80%" width="80%" alt="Public route table configuration"/>
<img src="https://i.imgur.com/63DNGY1.png" height="80%" width="80%" alt="Public route table configuration"/>
<br /><br />
</p>

<p align="center">
<b>Create ec2 instance and security Group for webser server </b>: Security group was created to allow inbound and outbound traffic to the web server instance. A linux-based instance was created to host the web server. <br/>
<img src="https://i.imgur.com/exHbywy.png" height="80%" width="80%" alt="Public route table configuration"/>
<img src="https://i.imgur.com/iXSjHGw.png" height="80%" width="80%" alt="Public route table configuration"/>
<img src="https://i.imgur.com/UESLqvG.png" height="80%" width="80%" alt="Public route table configuration"/>
<img src="https://i.imgur.com/kX6rslT.png" height="80%" width="80%" alt="Public route table configuration"/>
<img src="https://i.imgur.com/Qb2QP7Q.png" height="80%" width="80%" alt="Public route table configuration"/>
<br /><br />
</p>

<p align="center">
<b>Create two private subnets for database tier</b>: Defined private subnet ranges across availability zones for RDS deployment. I created a security group for the to allow only MySQL access <br/>
<img src="https://i.imgur.com/4Syxdfv.png" height="80%" width="80%" alt="Create private subnets"/>
<img src="https://i.imgur.com/5RdESru.png" height="80%" width="80%" alt="Create private subnets"/>
<img src="https://i.imgur.com/22jQYmd.png" height="80%" width="80%" alt="Create private subnets"/>
<br /><br />
</p>

<p align="center">
<b>Create DB subnet group</b>: Grouped private subnets to support RDS placement requirements. <br/>
<img src="https://i.imgur.com/b7kvuqy.png" height="80%" width="80%" alt="Create DB subnet group"/>

<br /><br />
</p>

<p align="center">
<b>Provision MySQL RDS instance</b>: Completed database configuration for the application backend. <br/>
<img src="https://i.imgur.com/OspmrnW.png" height="80%" width="80%" alt="Create RDS database"/>
<img src="https://i.imgur.com/kyMiUOr.png" height="80%" width="80%" alt="Create RDS database"/>
<img src="https://i.imgur.com/6A1YZi3.png" height="80%" width="80%" alt="Create RDS database"/>
<img src="https://i.imgur.com/SzYyq6C.png" height="80%" width="80%" alt="Create RDS database"/>
<img src="https://i.imgur.com/Xl645RR.png" height="80%" width="80%" alt="Create RDS database"/>
<br /><br />
</p>

<p align="center">
<b>Validate application endpoint</b>: Opened the Address Book app and confirmed it was reachable from the web tier. <br/>
<img src="https://i.imgur.com/bWWR6Ny.png" height="80%" width="80%" alt="Address book app endpoint"/>
<br /><br />
</p>

<p align="center">
<b>Verify data and update functionality</b>: Confirmed records are stored and validated edit operations in the app UI. <br/>
<img src="https://i.imgur.com/nI5bMjR.png" height="80%" width="80%" alt="Address book records"/>
<img src="https://i.imgur.com/11EEX58.png" height="80%" width="80%" alt="Address book records"/>
<img src="https://i.imgur.com/sXrrBXc.png" height="80%" width="80%" alt="Address book edit contact"/>
<br /><br />
</p>

<h2>Skills Learned</h2>

- Designing and configuring a custom VPC architecture
- Building secure public/private subnet patterns
- Connecting EC2 application tier to RDS database tier
- Validating full-stack connectivity through a working web app
<br />

<h2>Task Completed</h2>

- Created VPC networking components (subnets, route table, internet gateway)
- Configured database subnet group and deployed RDS MySQL instance
- Connected application and database tiers using security controls
- Verified Address Book application read/write behavior
