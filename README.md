# LAMP Server Deployment 
## LAMP

- **L → Amazon Linux**: Amazon Linux is a secure, stable, and high-performance Linux distribution provided by AWS, optimized for cloud-based applications and EC2 instances.
- **A → Apache**: Apache HTTP Server is a widely-used open-source web server that handles HTTP requests and serves web content to users efficiently.
- **M → MySQL**: MySQL is an open-source relational database management system that stores and manages application data using structured tables and SQL queries.
- **P → PHP**: PHP is a popular server-side scripting language used to develop dynamic web pages and applications by embedding code into HTML.

## Step 1: Launch an EC2 Instance

1. Go to AWS Console → EC2 
2. Launch Instance.
    - Name → LAMP
    - Choose AMI → Amazon Linux.
    - Instance type → t2.micro
    - Key pair → pem_server_key
    - security group → launch-wizard-1

![Project Screenshot](/images/LAMP-launch.jpg)

## Step 2: SSH to connect the EC2 Instance

```bash
ssh -i "pem-server-key.pem" ec2-user@ec2-52-2-236-21.compute-1.amazonaws.com
```
![Project Screenshot](/images/connect.jpg)

## Step 3: Install LAMP in **Amazon Linux**

1. Update your system

```bash
sudo yum update
```

2. Install Apache your LAMP server then Start & enable 

> **httpd**  → this is open-source web servers used to deliver web content to users.
> 

```bash
sudo yum install httpd -y
sudo systemctl start httpd
sudo systemctl enable httpd
```
![Project Screenshot](/images/httpd-start-status.jpg)

3. Install MYSQL your LAMP server then Start & enable

> mariadb105-server → this is the MySQL database to install or start
> 

```bash
sudo yum install mariadb105-server -y
sudo systemctl start mariadb
sudo systemctl enable mariadb
```
![Project Screenshot](/images/mysql-start-status.jpg)

4. Install PHP your LAMP server then Start & enable

> php → this is programming language.
> 

```bash
sudo yum install php -y
sudo systemctl start php-fpm
sudo systemctl enable php-fpm
```
![Project Screenshot](/images/php-start-status.jpg)

## Step 4: Terminating Your instance

1. Your use are done then got to AWS console 
2. Click on EC2 → instance 
3. Select instance You want to terminated
4. Click on Instance state 
5. Choose **Terminate (delete) instance**
6. Now click delete

![Project Screenshot](/images/delete-instance.jpg)
