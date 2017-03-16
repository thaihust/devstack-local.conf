_Add user stack before installation:_

```sh
adduser stack
echo "stack ALL=(ALL) NOPASSWD: ALL" >> /etc/sudoers
```

### 1. Successful deployment on ubuntu server 14.04.3 and 16.04.2
- local.conf.newton.neutronsfc
- local.conf.newton.tackersfc
- local.conf.newton.tacker_odl (tacker-->networking-sfc-->odl allinone setup with OVS NSH 2.6.1, being tested)

Note for ubuntu 14.04: before running ./stack.sh, execute the following command to install essential packages:

```sh
sudo apt-get install python-pip -y
sudo pip install --upgrade pip
sudo pip install -U os-testr
```

Note for ubuntu 16.04: fix skydive plugin error(openjdk has no candidate) before running ./stack.sh

```sh
sudo add-apt-repository ppa:openjdk-r/ppa  
sudo apt-get update   
```

Fix noVNC error keycode: wait for the installation to complete, then:

```sh
cd /opt/stack/noVNC
git checkout v0.6.0
```
Reload VM console!

### 2. Testing (on ubuntu server 16.04.2)
- status: failure
- local.conf.newton.tackersfc_ceilometer_gnocchi_grafana
- notes:

```sh
export no_proxy=192.168.2.0/24,localhost,127.0.0.0/8,.localdomain
cd ~/devstack
echo "ENABLE_IDENTITY_V2=False" >> local.conf
```

