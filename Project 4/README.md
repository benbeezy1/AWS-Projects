<h1>AWS Database Migration Service: MySQL to Aurora Migration</h1>

<h2>Description</h2>
This project demonstrates an end-to-end migration using <b>AWS Database Migration Service (DMS)</b>.
I migrated a source MySQL database running on an EC2-hosted Windows lab instance to an Amazon Aurora target.
The workflow covered source setup, endpoint configuration, replication task creation, and post-migration validation in MySQL Workbench.
<br /><br />

<h2>AWS Services Used</h2>

- <b>AWS Database Migration Service (DMS)</b> - replication instance, endpoints, and migration task
- <b>Amazon Aurora / Amazon RDS</b> - target managed relational database
- <b>Amazon EC2</b> - source-hosted environment for MySQL setup
- <b>AWS Systems Manager Fleet Manager</b> - remote desktop/session access to the lab instance
<br />

<h2>Environments Used</h2>

- <b>AWS Management Console</b>
- <b>MySQL Workbench</b>
- <b>Windows remote desktop session in Fleet Manager</b>
<br />

<h2>Project Walk-through</h2>

<p align="center">
<b>Prepare source database tools</b>: Connected to the lab instance using AWS systems fleet manager and completed MySQL Connector/Workbench setup for source configuration. <br/>
<img src="https://i.imgur.com/xtxKXqV.png" height="80%" width="80%" alt="MySQL setup on lab instance"/>
<img src="https://i.imgur.com/5pRC0wL.png" height="80%" width="80%" alt="MySQL setup on lab instance"/>
<img src="https://i.imgur.com/mu6IuCY.png" height="80%" width="80%" alt="MySQL setup on lab instance"/>


<br /><br />
</p>

<p align="center">
<b>Configure source MySQL server</b>: Created database "mydb" and imported data from local computer into the database <br/>
<img src="https://i.imgur.com/w9SGFdS.png" height="80%" width="80%" alt="MySQL setup on lab instance"/>
<img src="https://i.imgur.com/0J68MWu.png" height="80%" width="80%" alt="MySQL setup on lab instance"/>
<img src="https://i.imgur.com/diuk20X.png" height="80%" width="80%" alt="MySQL setup on lab instance"/>

<p align="center">
<b>Aurora instance connection</b>: Connected the already created aurora database instance to MySQL workbench. Captured Aurora cluster endpoint for connection. I confirmed that no database exist. <br/>
<img src="https://i.imgur.com/wMhVtiJ.png" height="80%" width="80%" alt="MySQL Workbench data import"/>
<img src="https://i.imgur.com/vFhs0ip.png" height="80%" width="80%" alt="MySQL setup on lab instance"/>
<img src="https://i.imgur.com/4MQinac.png" height="80%" width="80%" alt="MySQL setup on lab instance"/>
<img src="https://i.imgur.com/SnAn4Rn.png" height="80%" width="80%" alt="MySQL setup on lab instance"/>
<br /><br />
</p>

<p align="center">
<b>Create DMS replication instance</b>: Configured network and connectivity settings for the migration replication engine. <br/>
<img src="https://i.imgur.com/Gerve2A.png" height="80%" width="80%" alt="Create DMS replication instance"/>
<img src="https://i.imgur.com/Uf9m0JW.png" height="80%" width="80%" alt="Create DMS replication instance"/>
<br /><br />
</p>

<p align="center">
<b>Create source endpoint</b>: Added MySQL source endpoint details including host, port, and credentials. <br/>
<img src="https://i.imgur.com/VdAD6wZ.png" height="80%" width="80%" alt="Create source endpoint"/>
<br /><br />
</p>

<p align="center">
<b>Create target endpoint</b>: Configured Aurora target endpoint details and validated endpoint settings. <br/>
<img src="https://i.imgur.com/1PdoGvt.png" height="80%" width="80%" alt="Create target endpoint"/>
<br /><br />
</p>

<p align="center">
<b>Create migration task and table mappings</b>: Built a DMS task with selection rules for the source schema and tables. <br/>
<img src="https://i.imgur.com/smc6ogq.png" height="80%" width="80%" alt="DMS task mappings"/>
<br /><br />
</p>

<p align="center">
<b>Validate migration results</b>: Queried the Aurora-side data in Workbench to confirm records were migrated successfully. <br/>
<img src="https://i.imgur.com/GSeiN2O.png" height="80%" width="80%" alt="Migration validation in MySQL Workbench"/>
<img src="https://i.imgur.com/l04y5RF.png" height="80%" width="80%" alt="Migration validation in MySQL Workbench"/>
  
<br /><br />
</p>

<h2>Skills Learned</h2>

- Configuring source and target database endpoints for AWS DMS
- Creating and tuning DMS replication workflows
- Migrating relational datasets from MySQL to Aurora
- Verifying migration output and data accessibility in MySQL Workbench
<br />

<h2>Task Completed</h2>

- Prepared a source MySQL environment on the lab instance
- Created DMS replication instance, source endpoint, and target endpoint
- Built and executed a database migration task
- Validated successful data migration to Aurora
