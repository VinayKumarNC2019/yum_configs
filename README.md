# yum_configs
For yum repository configuration

CentOS/Redhat (YUM repo for EPEL)

yum --enablerepo=extras install epel-release

rpm --import https://www.elrepo.org/RPM-GPG-KEY-elrepo.org

yum install https://www.elrepo.org/elrepo-release-8.el8.elrepo.noarch.rpm (external link)


Jenkins installation

sudo wget -O /etc/yum.repos.d/jenkins.repo  https://pkg.jenkins.io/redhat-stable/jenkins.repo
    
sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io.key

sudo yum upgrade

sudo yum install jenkins java-1.8.0-openjdk-devel



Docker Installation
--------------------------
Executed below on Docker server 192.168.43.200

sudo yum install -y yum-utils

yum-config-manager  --add-repo  https://download.docker.com/linux/centos/docker-ce.repo
    
 yum install docker-ce docker-ce-cli containerd.io --nobest
 
 systemctl enable --now docker
 
 To make this server to explicitly listen to clients from other machines, did below changes.
 
  vi /usr/lib/systemd/system/docker.service
  
  ExecStart=/usr/bin/dockerd -H fd:// -H tcp://0.0.0.0:2000
  
  systemctl daemon-reload && systemctl restart docker
  
  firewall-cmd --add-port 2000/tcp --permanent &&   firewall-cmd --reload
  
  Executed below on Docker Client (Jenkins server) 192.168.43.100
  -----------------------------------------------------------------
  
  yum install -y yum-utils
  
  yum-config-manager --add-repo  https://download.docker.com/linux/centos/docker-ce.repo
    
 yum install docker-ce-cli 
 
 export DOCKER_HOST=192.168.43.200:2000
--------------------------------------------------------------------------------------------
  
 

 
 

