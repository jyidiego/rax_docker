rax_docker
==========

A dockerized container of the rax workstation

Getting Started
===============
Create ssh keys as below, because this is a demo/development
I opted for less security and just pressed enter for the passphrase

```
vagrant@rax-workstation:~$ ssh-keygen -t rsa
Generating public/private rsa key pair.
Enter file in which to save the key (/home/vagrant/.ssh/id_rsa): 
Enter passphrase (empty for no passphrase): 
Enter same passphrase again: 
Your identification has been saved in /home/vagrant/.ssh/id_rsa.
Your public key has been saved in /home/vagrant/.ssh/id_rsa.pub.
The key fingerprint is:
eb:c0:ba:da:30:d7:4f:e9:04:17:79:3e:ce:73:7b:54 vagrant@rax-workstation
The key's randomart image is:
+--[ RSA 2048]----+
|                 |
|         .       |
|        o .      |
|         +      E|
|      . S o    . |
|     o o = .  .  |
|  o . + = + ..   |
|   = . B   o ..  |
|  ..+.  +   ..   |
+-----------------+
```

Next it's time to log into the rax cloud and add the ssh-key:

```
vagrant@rax-workstation:~$ source openstackrc.sh 
Please enter your Openstack Username: demo
Please enter your OpenStack Password: 
Please enter your Region (ORD, DFW, IAD, SYD): IAD
Please enter HEAT tenant ID (Rackspace Account ID): 666666
root@a426b39425ed:/# 
```

Add your ssh public key

```
nova keypair-add --pub-key ~/.ssh/id_rsa.pub ansible_demo
```

You now are setup to create servers and interact with all the cli tools. Some things you 
should be able to do:
