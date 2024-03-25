# ansible-build

Anisible installation steps

Basic command : To ping the remote host

ansible all --key-file ~/.ssh/ansible -i inventory -m ping

ansible all -m ping

ansible all -m gather_facts

ansible all --list-hosts

ansible all -m gather_facts --limit 192.168.0.17
