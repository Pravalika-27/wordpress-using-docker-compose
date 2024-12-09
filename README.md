# wordpress-using-docker-compose

yum install git -y
    2  yum install docker -y
    3  systemctl start docker
    4  sudo curl -L "https://github.com/docker/compose/releases/latest/download/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
    5  sudo chmod +x /usr/local/bin/docker-compose
    6  docker-compose --version
    7  sudo usermod -aG docker ec2-user
    8  sudo chmod 666 /var/run/docker.sock
    9   sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose
   10   systemctl start docker
   11  sudo systemctl status docker
   12  ls /var/run/docker.sock
   13  sudo chmod 666 /var/run/docker.sock
   14  sudo chmod +x /usr/local/bin/docker-compose
   15  sudo wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo
   16  sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io-2023.key
   17  sudo yum install java-17-amazon-corretto-devel -y
   18  java --version
   19  yum install jenkins -y
   20  yum install mysql -y
   21  systemctl start jenkins
   22  systemctl status jenkins
   23  history
   24  cat /var/lib/jenkins/secrets/initialAdminPassword
   25  git init
   26  git 
   27  history
   28  systemctl status docker
   29  mysql --version
   30  history


   
