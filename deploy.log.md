### 1. Successful deployment on ubuntu server 14.04.3
- local.conf.newton.neutronsfc
- local.conf.newton.tackersfc

Before running ./stack.sh, execute the following command to install essential packages:

```sh
sudo apt-get install python-pip -y
sudo pip install --upgrade pip
sudo pip install -U os-testr
```

### 2. Testing (on ubuntu server 16.04.2)
- status: failure
- local.conf.newton.tackersfc_ceilometer_gnocchi_grafana
- notes:

```sh
export no_proxy=192.168.2.0/24,localhost,127.0.0.0/8,.localdomain
cd ~/devstack
echo "ENABLE_IDENTITY_V2=False" >> local.conf
sed -i 's/export OS_IDENTITY_API_VERSION=${IDENTITY_API_VERSION:-2.0}/export OS_IDENTITY_API_VERSION=3/' openrc
```
