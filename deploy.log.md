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
