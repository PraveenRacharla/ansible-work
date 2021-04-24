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


