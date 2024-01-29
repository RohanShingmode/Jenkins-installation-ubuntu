# Jenkins-installation-ubuntu
To install Jenkins on Ubuntu, you can follow these steps. Jenkins is a popular open-source automation server used for continuous integration and continuous delivery (CI/CD) purposes.

## Step 1: Update Package Repositories
Go to ubuntu machine and paste this command
```
sudo apt update
```
## Step 2: Install Java
Jenkins requires Java to run. You can install OpenJDK:
```
sudo apt install openjdk-11-jre
```
Verify Java is Installed

```
java -version
```
## Step 3: Download and Add the Jenkins GPG Key
Retrieve the Jenkins repository key and add it to your system:
```
curl -fsSL https://pkg.jenkins.io/debian/jenkins.io-2023.key | sudo tee \
  /usr/share/keyrings/jenkins-keyring.asc > /dev/null
```
## Step 4: Add Jenkins Repository to sources.list.d
Add the Jenkins repository to the list of sources:
```
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null

```
## Step 5: Install Jenkins
Update your package list and install Jenkins:
```
sudo apt-get update
sudo apt-get install jenkins -y
```
## Step 6: Start Jenkins Service
Start the Jenkins service:
```
sudo systemctl start jenkins
```
## Step 7: Enable Jenkins to Start on Boot
Enable Jenkins to start automatically when your system boots:
```
sudo systemctl enable jenkins
```
## Step 8: Check Jenkins Status
Verify that Jenkins is running:
```
sudo systemctl status jenkins
```
The status command should show that Jenkins is active and running.
## Step 9: Unlock Jenkins
** If you are in Virtual Machine in inbound traffic allow 8080 TCP port **
1. Open a web browser and go to http://your_server_ip:8080

<img width="960" alt="JenkinsSS" src="https://github.com/RohanShingmode/Jenkins-installation-ubuntu/assets/104613881/2ffdcf46-9dfb-4781-9579-bf4b294bd42c">


2. Retrieve the initial Jenkins administrator password:
```
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```
3. Copy the password and paste it into the Jenkins setup wizard.
## Step 10: Complete Jenkins Setup
Follow the instructions in the Jenkins setup wizard to complete the installation. You can install recommended plugins or select specific plugins based on your needs.
## Step 11: Create Admin User
Create an admin user by providing the required information.
## Step 12: Start Using Jenkins
Once the setup is complete, you can start using Jenkins. Access Jenkins at http://your_server_ip:8080 in your web browser.
Congratulations! You've successfully installed and set up Jenkins on your Ubuntu system. 

Reference Links:

[Install Jenkins on Ubuntu](https://www.digitalocean.com/community/tutorials/how-to-install-jenkins-on-ubuntu-20-04) 

[Jenkins Install GPG Key configurations](https://www.jenkins.io/blog/2023/03/27/repository-signing-keys-changing/)
