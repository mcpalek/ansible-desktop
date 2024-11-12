# ansible-desktop

This is a playbook which I use when I want to install the tools I usually use in my everyday work on a desktop Linux.

It will install Ansible , Visual Studio Code , Brave Brawser , Warp terminal etc

Prerequisit is to creat and copy ssh key to this VM followinf the command below:

ssh-keygen -t ed25519 -C "ansible" # here I write /home/aca/.ssh/ansible for the folder in which I am saving the ssh key

ssh-copy-id -i ~/.ssh/ansible.pub aca@192.168.1.38 # here you write the IP of the vm where I copy the ssh key

ansible all -m ping --key-file ~/.ssh/ansible --ask-become-pass # with this command I am cheking if all virtual machines are accessible

ansible-playbook playbook.yml -i inventory.yaml --key-file ~/.ssh/ansible --ask-become-pass # with this command you start the playbook
