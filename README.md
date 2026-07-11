# Prerequesite
1. AWS Account
2. Dockerhub Acount
###   Tools and Services
1. EC2
2. Docker
3. DockerFile
4. NodeJS
5. Jenkins
6. CI/CD

### Configuration and Steps
  Step-1 Create EC2 VM
  
  Step-2 Install Jenkins, Docker
  
  Step-3 Install Plugins + Configure Jenkins + Credentials + Docker Hub
  
  Step-4 Setup CI

  Step-5 Setup CD
  
  Step-6 Setup CI/CD
  
  Step-7 Setup Continues Delivery + Continues Deployment
  
  Step-8 Understand Scnerio Private + Remote VM CD
  
  Step-9 Setup Jenkins Dev QA & PROD

### Step-1 
Create EC2 Instance using 45GB storage and use Ubuntu LTS image. Consider taking a t2.large for faster compute. But least go woth t2.small

GO to Security Groups and open ports 8080, 3000, 443, 80 and port 22 (this SSH port would be already open).

Enter the commd prompt. 

### Step-2
Become root user by
```
sudo -i
```

Run these commands one by one
```
sudo apt update && sudo apt install git
git clone https://github.com/aavanish/Starbucks-App-JDK.git
```

For Jenkins installation 
https://github.com/aavanish/studious-adventure/blob/61b9a8ec127bff7275fc26dbe6b2da81efd12895/Day-04_Jenkins.md

```
cd Strabucks-App-JDK
chmod * ./  #(this enables the script files to execute)
./2nd-docker.sh #this will install docker
```

Go back to Jenkins UI --- Manage Jenkins (settings) > plugin > available plugins

Search and install 
1. Eclipse Temurin Installer
2. NodeJS
3. Docker
4. Docker Commons
5. Docker Pipeline,
6. Docker API
7. docker-build-step
8. Pipeline stage view

Click on restart jenkins after installation.

then again in Manage Jenkins > Credentials > Click Domains:Global > Add Credentials > Username and Password

Add your dockerhub username and docker password 

<img width="230" height="257" alt="image" src="https://github.com/user-attachments/assets/ad06136c-fb76-4c88-90ad-b80fc4137e4b" />

