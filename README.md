# wordpress-using-docker-compose

yum install git -y
     yum install docker -y
    systemctl start docker
    sudo curl -L "https://github.com/docker/compose/releases/latest/download/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
    sudo chmod +x /usr/local/bin/docker-compose
    docker-compose --version
    sudo usermod -aG docker ec2-user
    sudo chmod 666 /var/run/docker.sock
    sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose
   systemctl start docker
   sudo systemctl status docker
   ls /var/run/docker.sock
   sudo chmod 666 /var/run/docker.sock
   sudo chmod +x /usr/local/bin/docker-compose
     sudo wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo
     sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io-2023.key
     sudo yum install java-17-amazon-corretto-devel -y
     java --version
     yum install jenkins -y
    yum install mysql -y
     systemctl start jenkins
     systemctl status jenkins
   23  history
   24  cat /var/lib/jenkins/secrets/initialAdminPassword
   25  git init
   26  git 
   27  history
   28  systemctl status docker
   29  mysql --version
   30  history



#########################DOCKER,KUBECTL,MINIKUBE INSTALLATION ################################################

 1. Install Docker on Amazon Linux 2

sudo yum update -y
sudo amazon-linux-extras enable docker
sudo yum install docker -y
sudo service docker start
sudo systemctl enable docker

(Optional but recommended): Add your user to the docker group


sudo usermod -aG docker $USER

sudo usermod -aG docker $USER
 newgrp docker

 2. Install kubectl (Kubernetes CLI)

curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
chmod +x kubectl
sudo mv kubectl /usr/local/bin/


 3. Install Minikube (Local Kubernetes Cluster)

curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
chmod +x minikube-linux-amd64
sudo mv minikube-linux-amd64 /usr/local/bin/minikube
🔹 4. Start Minikube Using Docker Driver

minikube start --driver=docker












###############################################################
sudo apt update && sudo apt upgrade -y

sudo apt install -y docker.io
sudo systemctl enable docker
sudo systemctl start docker
sudo usermod -aG docker ubuntu

curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
sudo install minikube-linux-amd64 /usr/local/bin/minikube

curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl

sudo apt install -y conntrack

sudo systemctl status docker

minikube start --driver=docker --cpus=2 --memory=3072 --disk-size=20g
minikube addons enable ingress
minikube status
kubectl get nodes



# Set up Minikube's Docker environment
eval $(minikube docker-env)

# Build images using Minikube's Docker daemon
docker build -t frontend-app:latest ./app/frontend
docker build -t backend-app:latest ./app/backend

# Verify images are built in Minikube
docker images | grep -E '(frontend|backend)'


kubectl delete -f k8s/deployment-backend.yaml
kubectl delete -f k8s/deployment-frontend.yaml

kubectl apply -f k8s/deployment-backend.yaml
kubectl apply -f k8s/deployment-frontend.yaml


minikube ip

# Forward local port 8080 to frontend service port 80

kubectl port-forward -n demo-app service/frontend-service 8080:80

pkill -f "kubectl port-forward"
kubectl port-forward -n demo-app service/frontend-service 8080:80 --address=0.0.0.0 &

# Update the fetch URL to use relative path
sed -i 's|http://backend-service.demo-app.svc.cluster.local:8080|/api|g' app/frontend/index.html

minikube service frontend-service -n demo-app --url

kubectl describe ingress app-ingress -n demo-app

# Test the ingress routing
curl http://localhost:8080/api/data
   
