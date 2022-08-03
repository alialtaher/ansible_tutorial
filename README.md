# ansible_tutorial
# This is initial commit message
# ansible ad-hoc commands
# Run ping module to all files within inventory file
ansible all --key-file ~alialt/.ssh/id_ed25519 -i inventory -m ping 
# We can shorten the previous command by declaring default variables inside a new file called #ansible.cfg
# The command become:
ansible all  -m ping
# To list hosts which will be affected by running ansible modules:
ansible all --list-hosts
# To request host information use the gather_facts module
ansible all -m gather_facts
# To request host information use the gather_facts module with a limit of hosts number
ansible all -m gather_facts --limit kubemaster
# #######################################################################
# Running elevated ad-hoc commands "Requires permission"
ansible all -m apt -a update_cache=true
# It will fail since we are running ansible module using a normal user
# To get sudo priviliges "Become priviliges" run
ansible all -m apt -a update_cache=true --become --ask-become-pass
# To install a package:
ansible all -m apt -a name=vim-nox --become --ask-become-pass
# To specify more than one argument:
ansible all -m apt -a "name=snapd state=latest" --become --ask-become-pass
# To upgrade distro packages:
ansible all -m apt -a "upgrade=dist" --become --ask-become-pass

 
