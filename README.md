# Static Website Hosting on Amazon EC2 (Linux + Apache/httpd)

This project demonstrates how to host a static webpage on an **Amazon EC2 Linux instance** using the **Apache HTTP Server (httpd)**.

## 📌 Overview

A simple static website (HTML/CSS/JS) is deployed on an EC2 instance running Amazon Linux, served publicly via the Apache `httpd` web server.

## 🛠️ Tech Stack

- **Amazon EC2** – Virtual server (Amazon Linux 2/2023)
- **Apache (httpd)** – Web server software
- **HTML/CSS/JS** – Static website files

## 🚀 Deployment Steps

### 1. Launch an EC2 Instance
- Choose **Amazon Linux 2023 AMI**
- Instance type: `t2.micro` (Free Tier eligible)
- Configure a security group to allow:
  - **SSH (port 22)** – from your IP
  - **HTTP (port 80)** – from anywhere (0.0.0.0/0)

### 2. Connect to the Instance
```bash
ssh -i your-key.pem ec2-user@<your-ec2-public-ip>
```

### 3. Install Apache (httpd)
```bash
sudo yum update -y
sudo yum install httpd -y
```

### 4. Start and Enable httpd
```bash
sudo systemctl start httpd
sudo systemctl enable httpd
```

### 5. Create a website file
created a index.html and styles.css file under folder /var/www/html
using command vi index.html
```


### 6. Verify
Open your browser and go to:
```
http://13.203.197.255/
```

## 📂 Project Structure

```
├── index.html
├── style.css
```

## ✅ Verification Checklist

- [ ] EC2 instance is running
- [ ] Security group allows inbound HTTP (port 80)
- [ ] `httpd` service is active (`systemctl status httpd`)
- [ ] Website loads via public IP in browser

## 🔧 Useful Commands

| Command | Purpose |
|---|---|
| `sudo systemctl status httpd` | Check Apache service status |
| `sudo systemctl restart httpd` | Restart Apache after changes |
| `sudo tail -f /var/log/httpd/access_log` | View live access logs |
| `sudo tail -f /var/log/httpd/error_log` | View live error logs |

## 📄 License

This project is open source and available under the [MIT License]

## 🙋 sadaqat ullah siddqui

Feel free to reach out or open an issue if you have questions!
