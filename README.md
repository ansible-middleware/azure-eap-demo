# azure-sso-demo

This repository contains reference configurations that can create resourses on Azure using CLI and deploy 
wildfly-cluster-demo (https://github.com/ansible-middleware/wildfly-cluster-demo) on Azure with all the required configurations.

The final architecture looks like:

## Prerequisites

* Red Hat Enterprise Linux (RHEL) 8 host
* Ansible >= 2.9 / python >= 3.9
* python3-netaddr installed on the controller host `dnf install python3-netaddr`
* Azure CLI installed on the controller host 'dnf install azure-cli'
* All the default parmeters for Azure cloud instances are provided in `roles/azure/defaults/main.yml`
* We are using dynamic inventory provided  by Azure. Once the instances are created you can view it by `ansible-inventory -i inventory/myazure_rm.yml --graph`

### Install Ansible Dependencies

`ansible-galaxy collection install -r requirements.yml`

## Running on Azure cloud

1. Create a var-file containing your RHN credentials:
```
$ cat rhn-creds.yml
rhn_username: '<username>'
rhn_password: '<password>'
```

2. Execute the main play:
```
ansible-playbook -e @rhn-creds.yml -i cross-dc-rhsso-demo/myazure_rm.yml -i cross-dc-rhsso-demo/group_vars/all.yml -e "ansible_ssh_user=azureuser ansible_ssh_private_key_file='provide_your_ssh_private_key'" create-demo-setup.yml
```
Note: Replace `provide_your_ssh_private_key` with ssh private key file.

## License

Apache License v2.0 or later

See [LICENCE](LICENSE) to view the full text.


## Authors

* Harsha Cherukuri <hcheruku@redhat.com>
