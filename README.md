<div align="center">

#  Student Registration Form Deployment on AWS EC2 using NGINX, PHP & MariaDB


 AWS | Node.js | Linux | PM2 Deployment Project 

</div>

## Project Overview

This project demonstrates the deployment of a Student Registration Form Web Application on AWS EC2 running Amazon Linux 2023. The application uses HTML, PHP, NGINX and MariaDB.

##  Project Architecture
![](./images/architecture%20dig.png)

##  Technologies Used

| Technology | Purpose |
|------------|---------|
| AWS EC2 | Cloud Virtual Server |
| Amazon Linux 2023 | Operating System |
| NGINX | Web Server |
| PHP 8.5 | Backend |
| MariaDB 10.5 | Database |
| HTML | Frontend |
| VS Code | Code Editor |
| GitHub | Version Control |

##  Features

- Student Registration Form
- AWS EC2 Deployment
- PHP Backend Integration
- MariaDB Database Storage
- NGINX Configuration

##  Project Setup

### 1. Launch EC2 Instance

![EC2 Instance Creation](./images/1.png)

###  Security Group Configuration

Configured the following inbound rules:

| Port | Protocol | Purpose |
|------|----------|----------|
| 22 | TCP | SSH Access |
| 80 | TCP | HTTP Access |

![Security Group Configuration](./images/security%20group.png)

### 2. SSH Connection

```python
ssh -i "myaws.pem" ec2-user@ec2-98-86-225-68

```
![SSH Connection](./images/2.png)

### 3. Install Required Packages

```python
sudo yum update
sudo yum install nginx mariadb105-server php -y
```

![Package Installation](./images/3.png)

### 4. Start Services

```python
sudo systemctl status nginx mariadb php-fpm
```

![Service Status](./images/4.png)

### 5. Create Frontend

```python
cd /usr/share/nginx/html
ls
sudo vim signup.html
```

![Project Files](./images/5.png)

![Frontend HTML Code](./images/6.png)

### 6. Configure Database

```python
sudo mysql
mysql -u root -p
CREATE TABLE users (
id INT AUTO_INCREMENT PRIMARY KEY,
name VARCHAR(100) NOT NULL,
email VARCHAR(100) NOT NULL,
website VARCHAR(255),
gender ENUM('Male','Female','Other'),
comment VARCHAR(100)
);
```

![Database Creation](./images/7.png)

### 7. Configure Backend

```python
ls
sudo vim submit.php
```

![Backend File Creation](./images/8.png)

![PHP Backend Code](./images/9.png)

### 8. Install PHP MySQL Connector

```python
sudo yum install php8.5-mysqlnd.x86_64 -y
```

![Connector Installation](./images/10.png)

### 9. Access Application

![Signup Form Output](./images/11.png)

### 10. Verify Database Entry

```python
sudo mysql
mysql -u root -p
use fct;
select * from users;
```

![Database Verification](./images/12.png)

### 11. Test Form Submission

![Form Submission Example](./images/13.png)

![Successful Submission Output](./images/14.png)

##  Project Structure

```text
student-registration-form/
├── signup.html
├── submit.php
├── README.md
└── images/
```

##  Future Enhancements

- Responsive CSS Design
- Login Authentication
- HTTPS Configuration
- Docker Deployment
- CI/CD Pipeline

##  Conclusion

Successfully deployed a Student Registration Form application on AWS EC2 using Amazon Linux, NGINX, PHP, and MariaDB.

---

###  Author
---
**Prafulla Patil**

 Cloud & DevOps Enthusiast
