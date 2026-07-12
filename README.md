### Project Description

Starbucks Corporation is an American multinational chain of coffeehouses and roastery reserves
headquartered in Seattle, Washington

<img width="1892" height="965" alt="image" src="https://github.com/user-attachments/assets/5efa0557-6745-457f-8043-210cb9ab11df" />

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

## Go to manage Jenkins > Tools and configure tools
### 1. Java installation
 
  Add jdk 
  
  name - jdk17
  
  click on install automatically 
  
  add installer select install form adoptiam.net
  
  verison17.0.8.1+1

### 2. nodejs installation
   
  Add nodejs
  
  name - node16
  
  install automatically
  
  version nodejs 16.20.0

### 3- docker installation

  Add docker 0
  
  name -docker
  
  install automatically Dadd installer Odownload from docker.com
  
  Click on apply & save it

  ## SETUP CI
  Create a job > new item > item name - CI Pipeline > Pipeline script from SCM
  <img width="600" height="300" alt="image" src="https://github.com/user-attachments/assets/f7cbae76-3433-4318-801b-1d0d5ea20796" />

  ## SETUP CD
  Create a job > new item > item name - Starbucks app > Pipeline script from SCM

  paste script CD present in the git repo and perform modifications in dockerhub username and git pipeline syntax
  MAKE SURE YOU ARE USING YOUR DOCKERHUB USERNAME IN PIPELINES.

  Browse for <Public IP>:3000 

  This approach run both the pipelines separately i.e. continuous delivery. 

  To make this as continuous deployment, Starbucks app (CD Pipeline) > Configure > Trigger > Build after other projects are built > Select CI pipeline.
  
