## Fedora VM with AWX sources and containers built from scratch

This Vagrant project demonstrates a Linux virtual machine including the
[AWX](https://github.com/ansible/awx) sources which is ready to execute the
Ansible playbook which would build and start AWX as Docker containers.

### Getting Started

1. Make sure you have Ansible installed on your Vagrant host, as the
   `Vagrantfile` makes use of the [Ansible provisioner](https://www.vagrantup.com/docs/provisioning/ansible.html).

2. Create Vagrant machines by running:

        vagrant up

   This will setup a Fedora VM with the AWX source code repository
   synchronized and the build and runtime [prerequisites](https://github.com/ansible/awx/blob/devel/INSTALL.md#prerequisites)
   installed (Ansible, Docker, Make, ...).

3. The AWX setup must be started on the machine itself via Ansible playbook
   provided by upstream. See [AWX Setup on Docker](https://github.com/ansible/awx/blob/devel/INSTALL.md#docker-or-docker-compose)
   for a description of the inventory variables.

        vagrant ssh
        vim awx/installer/inventory
        ansible-playbook --become awx/installer/install.yml

4. Eventually the AWX Web interface will be available on `http://awx.example.com`
   or the corresponding address of your Vagrant machine. Login with **admin**
   and **password**.

Enjoy!
