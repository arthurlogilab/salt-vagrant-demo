=================
Salt Vagrant Demo
=================

A Salt Demo using Vagrant.


**Placeholder** for #cfgmgmt2018 salt monitoring auto deployment - this should be updated after I've done the demo. Watch this space.

Use SaltStack to deploy a full monitoring and supervision stack
-------------------------------------------------------------------

http://cfgmgmtcamp.eu/schedule/salt/monitoring.html

Instructions
============

Run the following commands in a terminal. Git, VirtualBox and Vagrant must
already be installed.

.. code-block:: bash

    git clone https://github.com/UtahDave/salt-vagrant-demo.git
    cd salt-vagrant-demo
    vagrant plugin install vagrant-vbguest
    vagrant up


This will download an Ubuntu  VirtualBox image and create three virtual
machines for you. One will be a Salt Master named `master` and two will be Salt
Minions named `minion1` and `minion2`.  The Salt Minions will point to the Salt
Master and the Minion's keys will already be accepted. Because the keys are
pre-generated and reside in the repo, please be sure to regenerate new keys if
you use this for production purposes.

You can then run the following commands to log into the Salt Master and begin
using Salt.

.. code-block:: bash

    vagrant ssh master
    sudo salt \* test.ping
