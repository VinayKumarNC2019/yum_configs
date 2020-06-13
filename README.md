# yum_configs
For yum repository configuration

Yum configuration

wget https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm


yum install epel-release-latest-7.noarch.rpm

sudo yum --disablerepo="*" --enablerepo="epel" list available

sudo wget -O /etc/yum.repos.d/jenkins.repo \
    https://pkg.jenkins.io/redhat-stable/jenkins.repo
sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io.key
sudo yum upgrade
sudo yum install jenkins java-1.8.0-openjdk-devel


CentOS machine:

yum --enablerepo=extras install epel-release

rpm --import https://www.elrepo.org/RPM-GPG-KEY-elrepo.org
yum install https://www.elrepo.org/elrepo-release-8.el8.elrepo.noarch.rpm (external link)

Docker Installation
--------------------------

sudo yum install -y yum-utils

yum-config-manager \
    --add-repo \
    https://download.docker.com/linux/centos/docker-ce.repo
    
 yum install docker-ce docker-ce-cli containerd.io --nobest

