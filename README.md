About
=====
This repo contains vagrant configurations to help you test Multipath TCP.

The setup enables you to test MPTCP from the virtual machine without requiring MPTCP 
support from the host.

Requirements
============
You need a recent vagrant installed (>=2.0.0) and virtualbox. Get it at http://www.vagrantup.com/downloads.html
and https://www.virtualbox.org/wiki/Downloads

When vagrant is installed, you need to install the vagrant-trigger plugin:

vagrant plugin install vagrant-triggers

You also need to have root access via sudo so the script can add NAT rules.
Currently Linux and Mac OS X hosts are supported.

Using it
========

Get it and use it:

    git clone https://github.com/rbauduin/vagrant_mptcp.git
    cd vagrant_mptcp
    # only the first time:
    vagrant plugin install vagrant-triggers
    vagrant up

This will:

  * download a vagrant box
  * start the virtual machine
  * setup NAT

To validate all works as expected, issue this command:

    vagrant ssh -c "curl www.multipath-tcp.org"

The outpout should be message full of joy, congratulating you for your MPTCP capabilities!

You stop the vm by issuing
  vagrant halt
This will also remove the NAT that was setup when starting the vm.
  

Thanks
======

Thanks to @mpyw for the Mac OS X NAT.
