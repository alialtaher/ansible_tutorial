# ansible_tutorial
# This is initial commit message
#ansible ad-hoc commands
#Run ping module to all files within inventory file
ansible all --key-file ~alialt/.ssh/id_ed25519 -i inventory -m ping 
#We can shorten the previous command by declaring default variables inside a new file called ansible.cfg
#The command become:
ansible all  -m ping
#To list hosts which will be affected by running ansible modules:
ansible all --list-hosts
To request host information use the gather_facts module
ansible all -m gather_facts
#To request host information use the gather_facts module with a limit of hosts number
ansible all -m gather_facts --limit kubemaster
