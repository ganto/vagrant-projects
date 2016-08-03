## Vagrant multi-machine mailing cluster

This Vagrant project demonstrates a small mail cluster setup using DebOps. It
will setup two machines:

* `webmail.example.com`: Nginx HTTP server with Roundcube
* `mail.example.com`: Postfix SMTP and Dovecot IMAP server


### Getting Started

1. Create Vagrant machines by running:

        vagrant up

   This will setup the two LXC containers and install DebOps into the `webmail`
   machine.

2. Login to `webmail` and run DebOps:

        vagrant ssh webmail
        cd vagrant-project
        debops

   This will run the entire DebOps playbook on both machines and setup the
   Postfix and Dovecot servers on the `mail` machine.

3. As the Roundcube role is not (yet) integrated into the DebOps common
   playbook, it has to be run separately (again from `webmail`):

        debops ansible/playbooks/roundcube.yml

   This will setup Nginx and Roundcube on `webmail`.

4. There are two users created on both machines which still need a password:

        for machine in mail webmail; do
          for user in user1 user2; do
            vagrant ssh -c "echo Set Password for $user on $machine; sudo passwd $user" $machine
          done
        done

5. Now you can start playing around with SMTP, IMAP and Roundcube. You can
   send mails from one user to the other on the command line via `mail` command
   or login on the Web mail interface on: https://webmail.example.com

Enjoy!
