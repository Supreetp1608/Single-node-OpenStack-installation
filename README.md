# Single-node-OpenStack-installation
OPENSTACK SINGLE NODE SET UP


1. sudo apt update
2. sudo apt -y upgrade
3. sudo useradd -s /bin/bash -d /opt/stack -m stack
4.  sudo chmod +x /opt/stack
5. sudo apt-get install sudo -y || yum install -y sudo
6. echo "stack ALL=(ALL) NOPASSWD: ALL" | sudo tee /etc/sudoers.d/stack
7. sudo su stack
8. cd ~
9. sudo apt-get install git -y || sudo yum install -y git

10. git clone https://opendev.org/openstack/devstack
11. cd devstack
12. cd samples
13. vim local.conf

	FLOATING_RANGE=192.168.1.224/27
	FIXED_RANGE=10.11.12.0/24
	ADMIN_PASSWORD=supersecret
	DATABASE_PASSWORD=iheartdatabases
	RABBIT_PASSWORD=flopsymopsy
	SERVICE_PASSWORD=iheartksl

14. To exit: esc + :wq  (Save & exit)
       : esc + :q!    (Don’t save & exit)

15. cp local.conf ../
16. cd ..
17. vim local.conf
18. ./stack.sh FORCE=yes

