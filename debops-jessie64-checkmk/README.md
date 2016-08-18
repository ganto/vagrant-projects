## Vagrant Check_MK Monitoring Server

This Vagrant project demonstrates the setup of a Check_MK monitoring server
using the [debops-contrib/checkmk_server](https://galaxy.ansible.com/debops-contrib/checkmk_server)
and [debops-contrib/checkmk_agent](https://galaxy.ansible.com/debops-contrib/checkmk_agent)
roles. It can be run with either the default `virtualbox` or with the
`libvirt` Vagrant virtualization provider. If you prefer Linux Containers
checkout [debops-jessie64-checkmk-lxc](../debops-jessie64-checkmk-lxc/).


### Getting Started

1. Create Vagrant machines by running:

        vagrant up

   This will setup a virtual machine with Debian Jessie and install
   [DebOps](https://debops.org) into it.

2. Login into the machine and run DebOps:

        vagrant ssh
        cd vagrant-project
        debops

   This will run the entire DebOps playbook which provides the basic setup
   of the machine.

3. As the Check_MK roles are not (yet) integrated into the DebOps common
   playbook, they have to be run separately from within the machine:

        debops ansible/playbooks/checkmk_server.yml
        debops ansible/playbooks/checkmk_agent.yml

   This will setup the Check_MK server and agent and also register the agent
   with the created monitoring site.

5. Now you can start playing around with Check_MK. Login on the WATO Web
   interface on https://debops-checkmk.example.com/debops with the default
   administrator credentials (username: omdadmin, password: omd)

Enjoy!
