# ansible-work

commands used : 
added to .bashrc file to update the ssh agent to contain the passphrase of my local ssh keys
alias ssha='eval $(ssh-agent) && ssh-add'

sudo apt update
sudo apt install ansible

ansible all --key-file ~/.ssh/ansible -i inventory -m ping
ansible all -m ping

ansible all -u opc -a "/bin/echo hello"
ansible all -m ping -u opc --become
ansible all -m ping -u opc --become --become-user root
ansible all --list-hosts
ansible all -u opc -m gather_facts
ansible all -u opc -a "hostname -i" --limit 193.123.39.205

red-hat .. which using rpm based package mgmt system
ansible all -u opc -m yum -a update_cache=true

Ubuntu/Debian .. which using apt based package mgmt system
ansible all -u opc -m yum -a update_cache=true
ansible all -u opc -m yum -a update_cache=yes --become
ansible all -u opc -m yum -a "update_cache=yes state=latest"

yum install net-tools

wget -qO- ifconfig.me/ip
193.123.39.205[

sudo service httpd status
sudo /bin/systemctl status/stop/start/restart httpd.service

ansible-playbook -u opc 

sudo firewall-cmd --list-all
sudo firewall-cmd --add-service=http --permanent
sudo firewall-cmd --remove-service=http --permanent
sudo firewall-cmd reload
sudo firewall-cmd --list-all

sudo firewall-cmd --zone=public --add-port=80/tcp --permanent
sudo firewall-cmd --zone=public --remove-port=80/tcp --permanent

WHEN STMT: 
when: ansible_distribution_version == "OracleLinux"
when: ansible_distribution_version == "OracleLinux" and ansible_distribution_version == "CentOS"
when: ansible_distribution_version in ["OracleLinux", "CentOS"]