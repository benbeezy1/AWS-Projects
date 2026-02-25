<h1>AWS Systems Manager Run Command on EC2</h1>

<h2>Description</h2>
This project demonstrates how to use <b>AWS Systems Manager (SSM)</b> to automate configuration tasks on an EC2 instance without using SSH.
I created a custom SSM document, executed it with <b>Run Command</b>, and validated the deployed web page through the EC2 public endpoint.
The workflow highlights repeatable operations management using SSM documents and centralized command execution.
<br /><br />

<h2>AWS Services Used</h2>

- <b>AWS Systems Manager</b> - document creation, document execution, and command status tracking
- <b>Amazon EC2</b> - managed target instance for remote command execution
<br />

<h2>Environments Used</h2>

- <b>AWS Management Console</b>
- <b>AWS Skill Builder Lab Environment</b>
<br />

<h2>Project Walk-through</h2>

<p align="center">
<b>Create an SSM command document</b>: I created a new document named <code>install-app</code>, selected the <b>Command</b> type, and used YAML content. <br/>
<img src="https://i.imgur.com/6tefEWl.png" height="80%" width="80%" alt="Create Systems Manager document"/>
<br /><br />
</p>

<p align="center">
<b>Document content used in the lab</b>: The document installs Apache, creates an <code>index.html</code>, and starts the HTTP service. <br/>
</p>

```yaml
---
schemaVersion: '2.2'
description: Command Document Example Template
parameters:
  Message:
    type: String
    description: Message to be displayed
    default: ''
mainSteps:
  - action: aws:runShellScript
    name: prepare_web_instance
    inputs:
      runCommand:
        - |
          sudo yum install httpd -y
          cat <<EOF > /var/www/html/index.html
          <!DOCTYPE html>
          <html>
          <head>
              <title>Benjamin's Web Server</title>
          </head>
          <body>
              <p>Hello World!!! This webpage is by Benjamin {{Message}}</p>
          </body>
          </html>
          EOF
          systemctl start httpd
```

<p align="center">
<b>Run the document on the managed instance</b>: I selected the <code>install-app</code> document, chose the EC2 instance named "command host" manually, and confirmed it has the target instance. <br/>
<img src="https://i.imgur.com/VrZ4XdX.png" height="80%" width="80%" alt="Run command target selection"/>
<br /><br />
</p>

<p align="center">
<b>Execute command </b>: I left the remaining settings as default, and selected <b>Run</b> to execute the document. <br/>
<img src="https://i.imgur.com/g5zOCmk.png" height="80%" width="80%" alt="Run command options and execute"/>
<br /><br />
</p>

<p align="center">
<b>Validate Run Command status</b>: Systems Manager returned command status as <b>Success</b> for the target instance. This indicates that the SSM document was run successfully on the targeted EC2 <br/>
<img src="https://i.imgur.com/5tgsHb8.png" height="80%" width="80%" alt="Command success status"/>
<br /><br />
</p>

<p align="center">
<b>Test web endpoint output</b>: Opening the EC2 public endpoint displayed the expected page content. <br/>
<img src="https://i.imgur.com/HM8YrVI.png" height="80%" width="80%" alt="Web endpoint validation"/>
<br /><br />
</p>

<h2>Skills Learned</h2>

- Building reusable Systems Manager command documents in YAML
- Running remote administration tasks without direct SSH access
- Targeting and executing commands on managed EC2 instances
- Validating command execution and service availability from endpoint output
<br />

<h2>Task Completed</h2>

- Created a custom SSM document (<code>install-app</code>)
- Executed the document on a managed EC2 instance with Run Command
- Verified successful command completion in Systems Manager
- Confirmed application output in a browser using the EC2 endpoint
