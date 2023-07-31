# Jenkins-Sonarqube-Docker

- for the 3 instances that we launched on AWS we chose t2.medium type and the AMI is ubuntu server 
- for the jenkins instance we ssh to it to install the java run time enviroment using :
 
  ~
  first we Chmod the ssh-key file to avoid the "too open" error using :
  >> chmod 400 ssh-key.pem
  then we ssh using the next command :
  >> ssh -i SSH-KEY-jenkins.pem ubuntu@<ip>
   then we install the java runtime :
  >> sudo apt install openjdk-11-jre -y
   then install the jenkins :
  >> curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key | sudo tee \
  /usr/share/keyrings/jenkins-keyring.asc > /dev/null
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update
sudo apt-get install jenkins
  
~
- Then w chnage the names of the servers to stop the confusion :
  >> sudo hostnamectl set-hostname sonarqube
  >> sudo hostnamectl set-hostname sonarqube
# Sonarqube 
>> sudo apt update
>> sudo apt install openjdk-17-jre -y
