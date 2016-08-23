# network_ansible
Test on Oracle Enterprise Linux 7.2

-Perform a base installation 

-Enable the network interface and restart the network service

sudo sed -i 's/ONBOOT=no/ONBOOT=yes/g' /etc/sysconfig/network-scripts/ifcfg-enp0s3

sudo /etc/init.d/network restart

-Update the base intallation

sudo yum update -y

-Install several packages

sudo yum install -y wget net-tools git python-setuptools gcc libxml2 libxml2-devel python-devel openssl-devel libxslt libsxlt-devel

-Install pip

sudo easy_install pip

-Install more packages, this time using pip

sudo pip install paramiko PyYAML Jinja2 httplib2 six ntc-ansibl

-Install ansible source

cd ~; git clone git://github.com/ansible/ansible.git --recursive

-Install ntc-ansible source

cd ~; git clone https://github.com/networktocode/ntc-ansible --recursive

-Setup your environment (this can be put in your .bashrc file)

source ~/ansible/hacking/env-setup

-Download this git repo and begin testing...
