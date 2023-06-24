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

  






