# Minecraft-Server-Infrastructure-Automation
## Background
In this project, we will automate the provisioning, configuration, and setup of a Minecraft Server infrastructure using AWS and Terraform. The goal is to create a fully automated Minecraft Server that can be easily replicated and maintained.
## Requirements
Before proceedings, make sure you have the following requirements in place:

 1. AWS Account: You will need an AWS account to provision the necessary resources.
 2. AWS CLI: Install the AWS Command Line Interface (CLI) to interact with AWS services from the command line.
 3. Terraform: Install Terraform to automate the provisioning of AWS resources.

You will have to set-up your AWS credentials for Terraform to work:
1.  Start your AWS Academy Learner Lab.
2.  Click on "AWS Details" in the top right corner of your Learner Lab page.  
    ![image.png]([https://canvas.oregonstate.edu/courses/1914651/files/98656010/preview](https://github.com/Min-K-99/Minecraft-Server-Infrastructure-Automation/blob/main/image%20(2).png))
3.  Create the file `~/.aws/credentials`  and copy the credentials from your "AWS Details" tab. Save the file.

Another option (useful on Windows) is to use the CLI to setup the auth variables:

    aws configure set <variable> "<value>"

For example:

    aws configure set aws_access_key_id "ASIAQ3SUJJBSZSG4BANA"

You will have to run it three times (the learner lab provides three variables to authenticate, the key, secret, and token).

## Diagram
![image.png](https://github.com/Min-K-99/Minecraft-Server-Infrastructure-Automation/blob/main/diagram.drawio.png)

## List of Commands to Run Terraform

 1. You need to clone the github repo to work on your local machine. To do this:

	`$	git	clone	<HTTPS-link-of-the-repo>`

	For example:

	`$	git	clone	https://github.com/Min-K-99/Minecraft-Server-Infrastructure-Automation.git`
 2. Go to `terraform` directory and enter these commands to start running terraform:
	
	`$	terraform init` - You need to initialize the directory, when you create a new configuration or check out an existing configuration from version control.

	`$	terraform validate` - You can make sure your configuration is syntactically valid and internally consistent.

	`$	terraform apply` - Apply the configuration.

	This will give you the Public IP Address of your Minecraft Server as output to connect using Minecraft Client.
	
	If you don't have Minecraft Client on your local machine, don't worry! We can test the connection by using `$ telnet <public-ip-address>	<query-port>`.
	
	For example:
	`$	telnet	35.88.204.227	25565`
	
	`$	terraform destroy` - In case, you want to terminates resources managed by your Terraform project. (In this case, Instances and Security Groups.)
