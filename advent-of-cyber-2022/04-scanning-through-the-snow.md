## Day 4 - Scanning through the snow


### 1. What is the name of the HTTP server running on the remote host?  
![image](https://user-images.githubusercontent.com/34974437/205623060-269ffada-6d43-4170-8c5e-2cd8aa1f90f0.png)

Peforming an nmap scan on the IP address of the target machine reveals that there are 4 open ports.  
As we used the -sV flag, we are able to identify the service version running on the machine. Looking at the information for Port 80, we will get the answer for the first question,

### 2. What is the name of the service running on port 22 on the QA server?  
Looking at the results of the previous scan we are able to identify what service is running on Port 22

### 3. What flag can you find after successfully accessing the Samba service?
From our initial nmap scan, it was revealed that we have an SMB service running on ports 139 & 445. For the previous days OSINT challenge we found a github repository for the site.
This repository revealed the database password for the QA & PROD environments was the same. It is worth considering that they may have reused this password elsewhere.
We are able to authenticate to the SMB share using the credentials found in the previous task. 

![image](https://user-images.githubusercontent.com/34974437/205624545-2d1b0378-423b-48c0-b843-79c31492d7ae.png)

We are now able to access the flag.txt file and this gives us the answer to question 3

### 4. What is the password for the username santahr? 

Further exploring the SMB share, we find another file in the admins folder. This userlist.txt file will allow us to see a list of users and passwords stored in plain text.
This information will allow us to answer question 4
