Cresco
======

Cresco Framework

[Read Me First](https://github.com/ResearchWorx/Cresco/wiki)

### Quickstart VM
The Cresco-VM provides a quickstart enviorment for working with Cresco.

### Using the Cresco-VM

1. Download the [Cresco-VM VMDK Image](http://128.163.2.80/Cresco-VM.vmdk.gz) and uncompress it on your computer.
2. Using [VirtualBox](https://www.virtualbox.org) or [VMware Fusion](http://www.vmware.com/products/fusion) boot the VM.
3. Determine Cresco-VM IP address and login with **username=**_cresco_ and **password=**_u$cresco01_
4. Login to RabbitMQ Web Interface _http://cresco-vm\_ipaddress:15672_ with **username=**_guest_ and **password=**_cresco_
5. Launch Cresco-Controller _controller0_ and Cresco-Agent _agent0_, with DummyPlugin _plugin/0_ by executing the script: _/opt/cresco/run.sh_
6. Log files can be found in the _/opt/cresco/logs/_ directory.
7. SSH into _controller0_ on the same IP address as the Cresco-VM on port 5222 (ssh cresco@cresco-vm\_ipaddress -p 5222) using **username=**_cresco_ and **password=**_cresco_
8. Follow console instructions


