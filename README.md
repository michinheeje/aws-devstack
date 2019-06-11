# aws-openstack
`sudo apt-get update; sudo apt-get updgrade; sudo apt-get dist-upgrade`</br>
`sudo reboot`</br>
`sudo -i`</br>
`adduser stack`</br>
`usermod -aG sudo stack`</br>
`su - stack`</br>
`sudo apt-get install git`</br>
`echo "stack ALL=(ALL) NOPASSWD: ALL" >> /etc/sudoers`</br>
`git clone https://github.com/openstack-dev/devstack`</br>
`cp devstack/samples/local.conf ~/devstack/`</br>
`cd devstack/`</br>
`ls`</br>
`sudo nano local.conf`</br>
</br>
`ADMIN_PASSWORD=1234`</br>
`DATABASE_PASSWORD=1234`</br>
`RABBIT_PASSWORD=1234`</br>
`SERVICE_PASSWORD=1234`</br>
</br>
`echo "enable_plugin sahara git://github.com/openstack/sahara" >> local.conf`</br>
`echo "enable_plugin sahara-dashboard git://github.com/openstack/sahara-dashboard" >> local.conf`</br>
`echo "enable_plugin ceilometer git://github.com/openstack/ceilometer" >> local.conf`</br>
</br>
`./stack.sh`
