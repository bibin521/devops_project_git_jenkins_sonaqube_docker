# devops_project_git_jenkins_sonaqube_docker
https://www.youtube.com/watch?v=361bfIvXMBI

# diagram

![Screenshot from 2023-06-24 16-24-48](https://github.com/bibin521/devops_project_git_jenkins_sonaqube_docker/assets/115148672/492c3165-3146-4b51-90a9-2bbfe7ab1ad0)

# Workflow
Developers will push the codes to the Git Repo. After that if any changes comes in to the Git repo Jenkis will triggering using webhook. after pulling the code from github we will test the code using Sonarqube, Sonarqube which is used to static code analaysis. After scanning the code passing the code to the docker to create docker image 

# requirements
3 ec2-instance which is one for jenkins,one for sonarqube and one for Docker

# step-1 - Install docker
Set up the repository
----------------------
sudo apt-get update
sudo apt-get install ca-certificates curl gnupg

Add Docker’s official GPG key:
------------------------------
sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
sudo chmod a+r /etc/apt/keyrings/docker.gpg

set up the repository:
----------------------
echo \
  "deb [arch="$(dpkg --print-architecture)" signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  "$(. /etc/os-release && echo "$VERSION_CODENAME")" stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

  Install Docker Engine
  ----------------------
  sudo apt-get update
  sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

  add user to the docker group
  -------------------------------
  usermod -aG docker ubuntu

  # step-2 - install jenkins on the server
  1  sudo apt update
    2  sudo apt install openjdk-11-jre
    3  java -version
    4  curl -fsSL https://pkg.jenkins.io/debian/jenkins.io-2023.key | sudo tee   /usr/share/keyrings/jenkins-keyring.asc > /dev/null
    5  echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc]   https://pkg.jenkins.io/debian binary/ | sudo tee   /etc/apt/sources.list.d/jenkins.list > /dev/null
    6  sudo apt-get update
    7  sudo apt-get install jenkins
    8  systemctl status jenkin

    # step3 - Install sonarqube on the server
    sudo apt-get install openjdk-17-jdk -y
    2  wget https://www.sonarsource.com/products/sonarqube/downloads/success-download-community-edition/
    3  ls
    4  wget https://binaries.sonarsource.com/Distribution/sonarqube/sonarqube-10.1.0.73491.zip
    5  ll
    6  sudo apt install unzip
    7  ll
    8  unzip sonarqube-10.1.0.73491.zip 
    9  ll
   10  cd sonarqube-10.1.0.73491/
   11  ll
   12  cd bin/
   13  ls
   14  cd linux-x86-64/
   15  ls
   16  ./sonar.sh 
   17  ./sonar.sh console


http://sonarqube_server_ip:9000

# step-3 - install the following plugins to the jenkins
1. sonarqubescanner
2. ssh2-easy
3. do the sonarqube configuration in jenkins

# step-4
login to jenkins server
sudo su jenkins
create ssh_key ===> ssh-keygen
and paste the ssh-key to the jenkins   ===> ssh-copy-id ubuntu@52.66.29.3


go to the docker server
sudo su 
vi /etc/ssh/sshd_config
then enable password authentication 

step-5




    

  






