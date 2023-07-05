# Description:  
This repo includes ansible playbooks for libvirt test env setup.  
It can detect host os version automatically, then setup env per the host os version.  
It supports setting up multiple hosts with different os versions at once.   

# Prerequisite:
1. Prepare a control node(machine that runs Ansible, it can be your laptop)  
2. Install pip on control node  
   ```
   yum install python3-pip
   ```
3. On control node, install ansible packages and collections
   ```
   python3 -m pip install --user ansible
   ansible-galaxy collection install ansible.posix
   ansible-galaxy collection install community.crypto
   ansible-galaxy collection install community.general
   ```
4. On control node, disable SSH key host checking in /etc/ansible/ansible.cfg  
   host_key_checking = False

# How to use:
1. Create your own inventory file  
2. Create your own playbook..
3. Run your playbook:  
   `ansible-playbook -i <your_hosts> <your_playbook> [-k]`  
   NOTE:  
   '-k' is not needed if you're configuring localhost or SSH key login is already configured.  
