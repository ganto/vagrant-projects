## AWX Demo Setup for DebOps

This Vagrant project contains two Debian Linux virtual machines which can be
used to manage and run Ansible playbooks via [AWX](https://github.com/ansible/awx):

* `awxdemo.example.com`: Docker container host running the AWX application stack
  ([awx_web](https://hub.docker.com/r/linuxmonk/awx_web/),
  [awx_task](https://hub.docker.com/r/linuxmonk/awx_task/),
  [RabbitMQ](https://hub.docker.com/_/rabbitmq/),
  [memcached](https://hub.docker.com/_/memcached/)
  and [PostgreSQL](https://hub.docker.com/_/postgres/)) containers as well as a
  [Gogs](https://hub.docker.com/r/gogs/gogs/) git repository server for storing
  the Ansible playbooks and roles.
* `node01.example.com`: Plain Debian host which can be used for applying
  Ansible playbooks.


### Getting started

Create Vagrant machines by running:

    vagrant up

This will create the two Linux virtual machines and setup the complete AWX/Gogs
application stack on the `awxdemo` machine. 

AWX will take a while to setup itself but after a while you should be able to
login the Ansible management Web interface with the default credentials 
`admin/password` at http://awxdemo.example.com
