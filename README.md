### Install vscode
`sudo snap install --classic code`

### Install jenkins
sudo apt update
sudo apt install openjdk-17-jdk -y
curl -fsSL https://pkg.jenkins.io/debian/jenkins.io-2023.key | sudo tee \
  /usr/share/keyrings/jenkins-keyring.asc > /dev/null

echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null

sudo apt update
sudo apt install jenkins -y

sudo systemctl start jenkins
sudo systemctl enable jenkins

sudo cat /var/lib/jenkins/secrets/initialAdminPassword

Kubernetes access to jenkins user

sudo mkdir -p /var/lib/jenkins/.kube

sudo cp /etc/kubernetes/admin.conf /var/lib/jenkins/.kube/config

sudo chown -R jenkins:jenkins /var/lib/jenkins/.kube








kubeadm init --cri-socket unix:///var/run/crio/crio.sock

mkdir -p $HOME/.kube

export KUBECONFIG=/etc/kubernetes/admin.conf



































