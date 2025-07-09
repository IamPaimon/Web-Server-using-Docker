# Web-Server-using-Docker
Hosting web server using docker 


### 🧰 Tools used: ###

AWS EC2 (Free Tier eligible)

Docker

Apache/Nginx Web Server (inside a Docker container)

SSH (to connect to the instance)


### ✅ Step-by-Step Process  ###
Step 1: Create AWS Free Tier Account
Go to https://aws.amazon.com/free

Sign up with a credit/debit card (no charges if you stay within limits).

Log in to the AWS Management Console.


Step 2: Launch an EC2 Instance
Search for “EC2” in the AWS Console → Click Launch Instance.

Set:

Name: docker-webserver

AMI: Select Ubuntu 22.04 LTS (Free Tier eligible)

Instance type: t2.micro

Key pair: Create a new one or use existing → download .pem file

Security group:

Allow SSH (port 22) from My IP

Allow HTTP (port 80) from Anywhere

Click Launch Instance



