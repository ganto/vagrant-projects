## Vagrant Projects

This is a repository of [Vagrant](https://www.vagrantup.com) projects which
I use for developing or testing stuff. They can be used as they are or as
example for your own needs.

If you want to run a project on your own machine, make sure you have Vagrant
>=1.8 and the Vagrant
[hostmanager](https://github.com/devopsgroup-io/vagrant-hostmanager) plugin
installed on your machine. Some of the projects will further make use of the
Vagrant Ansible provisioner which will require Ansible >=2.0.

All projects are meant to be run with either the `lxc` or `libvirt`
virtualization provider.

### DebOps

These projects will setup [DebOps](http://debops.org) using the
[vagrant_debops](https://galaxy.ansible.com/ganto/vagrant_debops) Ansible role
via Vagrant Ansible provisioner.

* `debops-jessie64-lxc`: Setup DebOps including Ansible from the
  `jessie-backports` repository on a Debian Jessie LXC machine.

* `debops-precise64-lxc`: Setup DebOps including latest stable Ansible from
  [PyPI](https://pypi.python.org/pypi) on a Ubuntu Precise (12.04) LXC machine.

* `debops-trusty64-lxc`: Setup DebOps including Ansible from the `stable-2.1`
  git branch on a Ubuntu Trusty (14.04) LXC machine.

* `debops-xenial64-lxc`: Setup DebOps with Ubuntu-packaged Ansible on a Ubuntu
  Xenial (16.04) LXC machine.

### Author

The content of this repository was written by:
   
- [Reto Gantenbein](https://linuxmonk.ch/) | [e-mail](mailto:reto.gantenbein@linuxmonk.ch) | [GitHub](https://github.com/ganto)

License: [GPLv3](https://tldrlegal.com/license/gnu-general-public-license-v3-%28gpl-3%29)