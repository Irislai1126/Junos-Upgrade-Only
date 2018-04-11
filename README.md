# Junos-Upgrade-Only
## Assumption
You have a Linux machine with Ansible installed.  
This Linux machcine can reach target Junos device via IP.  
Target Junos device has NETCONF over SSH enabled.  
You know the username and password to login to target Junos device.

## How to use

### Modify "inventory" file
It should look like:  
```ini
target-device ansible_host=172.16.0.10 target_junos="junos-install-mx-x86-64-17.4R1.16.tgz"



[all:vars]

ansible_connection="netconf"

ansible_user="root"

ansible_password="19900227"
```

### Store Junos image under the same directory of playbook

### Play the playbook
'ansible-playbook -i inventory upgrade.yaml'
