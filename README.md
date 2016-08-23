# network_ansible
Tested on Oracle Enterprise Linux 7.2

---
NOTE: I am using ansible 2.2 from source.  I had issues with the ansible rpm from EPEL.

[netansible@localhost ~]$ python --version
Python 2.7.5
[netansible@localhost ~]$ ansible --version
 [WARNING]: Optional dependency 'cryptography' raised an exception, falling back
to 'Crypto'

ansible 2.2.0 (devel a695e18615) last updated 2016/08/23 16:27:59 (GMT -400)
  lib/ansible/modules/core: (detached HEAD 368ca738fa) last updated 2016/08/23 16:28:06 (GMT -400)
  lib/ansible/modules/extras: (detached HEAD 0749ce6faa) last updated 2016/08/23 16:28:10 (GMT -400)
  config file =
  configured module search path = Default w/o overrides
[netansible@localhost ~]$
---

-Perform a base installation 

-Enable the network interface and restart the network service

`sudo sed -i 's/ONBOOT=no/ONBOOT=yes/g' /etc/sysconfig/network-scripts/ifcfg-enp0s3`

`sudo systemctl restart network`

-Update the base installation then reboot

`sudo yum update -y`

`sudo reboot`

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

NOTE: All files from ~/ntc-ansible/library/ were copied over to ~/network_ansible/library/

`cd ~; git clone https://github.com/jamiekowalczik/network_ansible.git`

`cd ~/network_ansible`
