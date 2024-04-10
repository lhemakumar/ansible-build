# Basic Unix commands to create SSH-Key and copy public keys into  nodes

ssh-keygen -t ed25519 -C "Ansible"

ssh-copy-id -i ~/.ssh/id_ed25519.pub couser@192.168.0.18

ssh-copy-id -i ~/.ssh/ansible.pub couser@192.168.233.128

ssh -i ~/.ssh/ansible couser@192.168.0.18

ssh -i ~/.ssh/ansible couser@192.168.233.128

eval $(ssh-agent)

Ps aux | grep 1785

alias ssha='eval $(ssh-agent) && ssh-add'

ssh-add ~/.ssh/ansible

# ansible installation & guide steps

https://docs.ansible.com/ansible/2.8/index.html

# ansible best practices
https://docs.ansible.com/ansible/2.8/user_guide/playbooks_best_practices.html#best-practices

# ansible-build module 

Basic command : To ping the remote host

ansible all --key-file ~/.ssh/ansible -i inventory -m ping

ansible all -m ping

ansible all -m ping  -i inventory-withalias

ansible all -m gather_facts

ansible all --list-hosts

ansible all --list-hosts -i inventory-withalias

ansible all -m gather_facts --limit 192.168.0.17

ansible all -m gather_facts --limit 192.168.233.128 | grep ansible_distribution

ansible all -m apt -a update_cache=true --become --ask-become-pass

ansible all -m apt -a name=vim-nox --become --ask-become-pass

ansible all -m apt -a name=tmux --become --ask-become-pass

ansible all -m apt -a name=snap --become --ask-become-pass

ansible all -m apt -a "name=snap state=latest" --become --ask-become-pass

ansible all -m apt -a "upgrade=dist" --become --ask-become-pass

ansible-playbook --ask-become-pass playbooks/jdk_playbook.yml

ansible-playbook --ask-become-pass playbooks/install_apache.yml

#######
####testing github brnach protection 3




