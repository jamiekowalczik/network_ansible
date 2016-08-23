# network_ansible
Tested on Oracle Enterprise Linux 7.2

-Perform a base installation 

-Enable the network interface and restart the network service

`sudo sed -i 's/ONBOOT=no/ONBOOT=yes/g' /etc/sysconfig/network-scripts/ifcfg-enp0s3`

`sudo systemctl restart network`

-Update the base intallation

`sudo yum update -y`

-Install several packages

`sudo yum install -y wget net-tools git python-setuptools gcc libxml2 libxml2-devel python-devel openssl-devel libxslt libsxlt-devel`

-Install pip

`sudo easy_install pip`

-Install more packages, this time using pip

`sudo pip install paramiko PyYAML Jinja2 httplib2 six ntc-ansible`

-Install ansible source

`cd ~; git clone git://github.com/ansible/ansible.git --recursive`

-Install ntc-ansible source

`cd ~; git clone https://github.com/networktocode/ntc-ansible --recursive`

-Setup your environment (this can be put in your ~/.bash_profile file)

`source ~/ansible/hacking/env-setup`

-Download this git repo and begin testing...

`cd ~; git clone https://github.com/jamiekowalczik/network_ansible.git`

`cd ~/network_ansible`
