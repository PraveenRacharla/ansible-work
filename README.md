# ansible-work

commands used : 
added to .bashrc file to update the ssh agent to contain the passphrase of my local ssh keys
alias ssha='eval $(ssh-agent) && ssh-add'

sudo apt update
sudo apt install ansible

 ansible all --key-file ~/.ssh/ansible -i inventory -m ping
 ansible all -m ping


