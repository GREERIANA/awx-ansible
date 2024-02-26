# awx-ansible
Automate IT infrastructure using Ansible and AWX (Tutorial Walkthrough)  

## Installing Ansible
(This section lists the prerequisites and the steps to install Ansible & AWX.)

### Prerequisites include:
- Python 3
- open-ssh
- Postgresql
- rabbitmq-server
- wget
- memcached
- nginx


Note: Perform the following steps to install the prerequisites of Ansible and AWX using RHEL 7 or above

Step 0: Elevate permissions (Requires authentication via password)
```
  sudo su
```

Step 1: Enable firewall 
```
  systemctl enable firewalld
```

Step 2: Start firewall
```
  systemctl start firewalld
```

Step 3: Allow the server to use the HTTP protocol
```
  firewall-cmd --add-service=http --permanent; firewall-cmd --add-service=https --permanent
```

Step 4: Restart firewall
```
  systemctl restart firewalld
```

Step 5: Install the EPEL repository
```
  yum install http://download.fedoraproject.org/pub/epel/7/x86_64/e/epel-release-7-5.noarch.rpm
```

Step 6: Install the prerequisite packages
```
  yum install postgresql96-server -y
  yum install -y rabbitmq-server wget memcached nginx ansible
```

## Installing and configuring Ansible and AWX packages
(Perform the following steps to install and configure Ansible and AWX packages)

Step 1: Add the AWX repository to yum.repos.d by performing the following tasks:

Download the repo using the wget command
