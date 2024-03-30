# ansible-build

Anisible installation steps

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

ansible-playbook --ask-become-pass install_apache.yml





