# Installing Jenkins on AWS Ubuntu
This guide will walk you through the steps required to install Jenkins on an AWS Ubuntu instance.

## Prerequisites
Before you begin, make sure you have the following:

- An AWS Ubuntu instance
- A user account with sudo privileges
- Java 8 or later installed
## Step 1: Update the package manager
First, update the package manager to ensure that all the latest packages are installed on your instance.
```bash
sudo apt-get update
```
## Step 2: Install Java
Install Java by running the following command:
```bash
sudo apt-get install openjdk-8-jdk -y
```
This will download and install Java 8 on your AWS Ubuntu instance.

## Step 3: Add the Jenkins repository key
Add the Jenkins repository key to your system using the following command:
```bash
wget -q -O - https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo apt-key add -
```
## Step 4: Add the Jenkins repository
Add the Jenkins repository to your system using the following command:
```bash
sudo sh -c 'echo deb https://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'
```
## Step 5: Update the package manager again
Update the package manager again to ensure that Jenkins is available.
```bash
sudo apt-get update
```
## Step 6: Install Jenkins
Install Jenkins by running the following command:
```bash
sudo apt-get install jenkins -y
```
This will download and install Jenkins on your AWS Ubuntu instance.

## Step 7: Start Jenkins
Start Jenkins using the following command:
```bash
sudo systemctl start jenkins
```
## Step 8: Verify the installation
Verify that Jenkins is installed correctly by accessing the Jenkins web interface at `http://<your-server-ip>:8080`. You should see the Jenkins login screen.

## Step 9: Unlock Jenkins
Before you can use Jenkins, you need to unlock it using the initial administrator password. You can find this password in the following file:
```bash
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```
Copy the password from the file and paste it into the Jenkins web interface.

## Conclusion
Congratulations, you have successfully installed Jenkins on your AWS Ubuntu instance! You can now use Jenkins to automate your build, test, and deployment processes.