## Vagrant Projects

This is a repository of [Vagrant](https://www.vagrantup.com) projects which
I use for developing or testing stuff. They can be used as they are or as
example for your own needs.

If you want to run a project on your own machine, make sure you have
Vagrant >=1.8 and the 
[hostmanager](https://github.com/devopsgroup-io/vagrant-hostmanager) plugin
installed on your machine. Some of the projects will further make use of the
Vagrant Ansible provisioner which will require Ansible >=2.0.

All projects are meant to be run with either the `lxc` or `libvirt`
virtualization provider.

### DebOps

These projects will setup [DebOps](http://debops.org) using the
[vagrant_debops](https://galaxy.ansible.com/ganto/vagrant_debops) Ansible role
via Vagrant Ansible provisioner.

* `debops-jessie64-lxc`: Setup DebOps including Ansible from the `stable-2.3`
  git branch on a Debian Jessie LXC machine.

* `debops-stretch64-lxc`: Setup DebOps including Ansible from the `stable-2.3`
  git branch on a Debin Stretch LXC machine.

* `debops-trusty64-lxc`: Setup DebOps including Ansible from the `stable-2.3`
  git branch on a Ubuntu Trusty (14.04) LXC machine.

* `debops-xenial64-lxc`: Setup DebOps including Ansible from the `stable-2.3`
  git branch on a Ubuntu Xenial (16.04) LXC machine.


### Demo Applications using DebOps

* `debops-jessie64-mailer-lxc`: Multi-machine mailing cluster with Roundcube,
  Postfix and Dovecot using LXC. See separate [README](/debops-jessie64-mailer-lxc/).

* `debops-jessie64-checkmk`: Check_MK monitoring server setup for Virtualbox
  or KVM (libvirt). See separate [README](/debops-jessie64-checkmk/).

* `debops-jessie64-checkmk-lxc`: Check_MK monitoring server setup using LXC.
  See separate [README](/debops-jessie64-checkmk-lxc/).


### Other Application Demos

* `fedora-awx-devel`: Setup AWX development environment on a Fedora 26.

* `awx-debops-demo`: AWX demo setup with GOGS running on a Debian Stretch
  Docker host setup by [debops.docker](https://github.com/debops/ansible-docker).
  See separate [README](/awx-debops-demo/).

* `heketi-centos7-single`: Single node GlusterFS server with Heketi REST API
  service. See separate [README](/heketi-centos7-single/).


### Author

The content of this repository was mostly written by:
   
- [Reto Gantenbein](https://linuxmonk.ch/) | [e-mail](mailto:reto.gantenbein@linuxmonk.ch) | [GitHub](https://github.com/ganto)

License (if not specified otherwise): [GPLv3](https://tldrlegal.com/license/gnu-general-public-license-v3-%28gpl-3%29)
