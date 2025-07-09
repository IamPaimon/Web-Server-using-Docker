# Web-Server-using-Docker
Hosting web server using docker 


### 🧰 Tools used: ###
* AWS EC2 (Free Tier eligible)
* Docker
* Apache/Nginx Web Server (inside a Docker container)
* SSH (to connect to the instance)


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


Step 3: Connect to EC2 via SSH
   chmod 400 your-key.pem
   ssh -i "your-key.pem" ubuntu@your-ec2-public-ip


Step 4: Install Docker
   * sudo apt update
      ![Update-Package](https://github.com/user-attachments/assets/7375a047-eff3-4118-8eef-8b4449dd90c4)
   * sudo apt install docker.io -y
     ![Install-Docker](https://github.com/user-attachments/assets/8c93540e-bbca-40a0-ba49-b7b2cece34fd)

   * sudo systemctl enable docker
   * sudo systemctl start docker
Verify: 
   * docker --version
![Docker-Version](https://github.com/user-attachments/assets/585c357a-f585-4434-b3fd-907d1e8958b5)

Step 5: Run a Web Server Container
    You can use Nginx or Apache:
   * sudo docker run -d -p 80:80 nginx
   


Step 6: Test Web Server
   * http://<your-ec2-public-ip>
*** You should see Welcome to nginx! or Apache's default page. ***


### If you want to add your own HTML page: ###
    Indside The container, edit Index.html file (Paste your code)
  Commands:
      * docker ps -a 
      ![Container_is_Running](https://github.com/user-attachments/assets/cefbd185-952a-4d5b-beb6-1752adf51f42)

      * docker exec -it <Container_name> /bin/sh  
              OR 
      * docker exec -it <Container_name> /bin/bash

![Inside_Container](https://github.com/user-attachments/assets/cc6fb412-4ab6-4486-a06d-a46d79414bee)

### Refresh Webpage 
      

![Web-Run](https://github.com/user-attachments/assets/86c3042e-1cf9-40c0-beaa-4f9705c27b35)
