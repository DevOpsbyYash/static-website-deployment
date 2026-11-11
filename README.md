# Static Website Deployment on AWS EC2 using Nginx

A hands-on cloud deployment project demonstrating how to launch an AWS EC2 Ubuntu instance, configure an Nginx web server, and host a responsive static portfolio website using HTML5 and CSS3.

This project focuses on practical experience with AWS cloud infrastructure, Linux administration, Nginx configuration, and static website hosting.

---

## Project Architecture

```text
          AWS Management Console
                 |
                 |
              AWS EC2
               Ubuntu 
              t3.micro
                 |
          SSH Connection
            Port 22
                 |
              Nginx
            Port 80
                 |
          /var/www/html/
                 |
          +------+------+
          |             |
       index.html    style.css
          |             |
          +------+------+
                 |
           Static Website
                 |
              Browser
```

---

## Technology Stack

| Component | Technology |
|---|---|
| Cloud Platform | AWS |
| Compute Service | Amazon EC2 |
| Operating System | Ubuntu  |
| Instance Type | t3.micro |
| Web Server | Nginx |
| Frontend | HTML5, CSS3 |
| Remote Connection | SSH |
| SSH Client | Windows PowerShell |

---

## Step-by-Step Implementation

### Step 1: Launch AWS EC2 Instance

1. Logged into the AWS Management Console.
2. Navigated to the Amazon EC2 dashboard.
3. Launched an EC2 instance named `StaticWebsite`.
4. Selected Ubuntu Server.
5. Selected the `t3.micro` instance type.
6. Created and selected an SSH key pair.
7. Configured the Security Group with the following inbound rules:

| Type | Protocol | Port | Source |
|---|---|---|---|
| SSH | TCP | 22 | My IP |
| HTTP | TCP | 80 | 0.0.0.0/0 |

**EC2 Instance Screenshot**

![EC2 Instance](screenshots/instance.png)

---

### Step 2: Connect to EC2 Using SSH

Connected to the Ubuntu EC2 instance from Windows PowerShell using the downloaded private key (`practical.pem` file).

**SSH Command:**

```bash
ssh -i .\Downloads\practical.pem ubuntu@YOUR_PUBLIC_IP
```

After successful authentication, accessed the remote Ubuntu server.

**SSH Connection Screenshot**

![SSH Connection](screenshots/ssh-connection.png)

---

### Step 3: Update Ubuntu and Install Nginx

Updated the Ubuntu package lists and installed the Nginx web server.

**Commands Used:**

```bash
sudo apt update -y
sudo apt install nginx -y
sudo systemctl start nginx
sudo systemctl enable nginx
sudo systemctl status nginx
```

**Nginx Installation Screenshot**

![Nginx Installation](screenshots/nginx-installation.png)

---

### Step 4: Create Static Website Files

Navigated to the default Nginx web root directory:

```bash
cd /var/www/html/
ls
sudo nano index.html
sudo nano style.css
```

**Website Files Setup Screenshot**

![Website Files](screenshots/website-files.png)

---

### Step 5: Access the Deployed Website

After creating the HTML and CSS files, accessed the website using the EC2 instance's public IP address.

**Website URL:**

```text
http://YOUR_PUBLIC_IP
```

Nginx serves the `index.html` file from the default web root directory.

Successfully accessed the static portfolio website through a web browser.

**Website Output Screenshot**

![Website Output](screenshots/website-output.png)

---

## Project Directory Structure

```text
static-website-deployment/
│
├── index.html
├── style.css
├── README.md
│
└── screenshots/
    ├── instance.png
    ├── ssh-connection.png
    ├── nginx-installation.png
    ├── website-files.png
    └── website-output.png
```

---

## Website Sections

The website is designed using HTML5 and CSS3 with a responsive layout.

---

## What I Learned

Through this hands-on project, I gained practical experience in:

- Launching and configuring AWS EC2 instances.
- Connecting to remote Linux servers using SSH.
- Updating Ubuntu packages using APT.
- Installing and managing Nginx.
- Managing Linux services using `systemctl`.
- Working with the `/var/www/html/` directory.
- Creating and hosting static websites using HTML and CSS.
- Configuring AWS Security Group inbound rules.
- Accessing a deployed website through an EC2 public IP address.
- Documenting cloud deployment projects using GitHub.

---

## Conclusion

Successfully deployed a static website on an AWS EC2 Ubuntu instance using Nginx.

This project helped me understand the fundamentals of cloud infrastructure, Linux server administration, web server management, and static website deployment.

---

## Author

**Yash Jain**

MCA Student | Aspiring Cloud & DevOps Engineer

Interested in AWS, Linux, Cloud Computing, and DevOps.