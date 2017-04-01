## Vagrant single node Gluster server with Heketi REST API

This Vagrant project demonstrates the [Heketi](https://github.com/heketi/heketi)
REST API on a single node [GlusterFS](https://www.gluster.org/) server. It
consists of a single machine:

* `heketi.example.com`: Gluster server/client with Heketi REST API serice

The Ansible roles used to setup Gluster and Heketi are taken from the
[vagrant-heketi](https://github.com/heketi/vagrant-heketi) project where more
sophisticated Vagrant setups are available.

### Getting Started

1. Create Vagrant machines by running:

        vagrant up

   This will setup a single VM with Gluster server and Heketi preinstalled
   using the Vagrant Ansible privisioner.

2. Login to `heketi` and load the storage server topology into Heketi:

        vagrant ssh heketi
        export HEKETI_CLI_SERVER=http://localhost:8080
        heketi-cli topology load --json=topology_<provider>.json

   Where _provider_ is either `virtualbox` or `libvirt` depending on the used
   vagrant provider.

3. To create a non-distributed and non-replicated Gluster volume with Heketi
   run e.g.:

        heketi-cli volume create --size=100 --durability=none --replica=1 --redundancy=1

Enjoy!

### More information
* See the command line help screen by typing: `heketi-cli -h`
* Please see the [API](https://github.com/heketi/heketi/wiki/API) for REST commands.
