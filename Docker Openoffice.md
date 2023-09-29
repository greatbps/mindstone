

1. Docker 설치 
  + sudo yum remove docker docker-engine docker.io containerd runc
  + sudo yum update && sudo yum install \
      apt-transport-https \
      ca-certificates \
      curl \
     software-properties-common
  + curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg


yum-config-manager  --add-repo \
 "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"

