Azure role
====================

Requirements
------------

The role handles create instances and configures then on Azure cloud.

<!--start argument_specs-->
Role Defaults
-------------

* No defaults


Role Variables
--------------

| Variable | Description | Default |
|:---------|:------------|:--------|
|`virtualnetwork_name`| Name of the network interface. | `ansible-middileware-vn`|
|`subnet_name`| Name of the subnet network interface. | `ansible-middileware-subnet`|
|`securitygroup_name`| Unique name for the rule. | `ansible-middileware-sg`|
|`admin_username`| Azure VM username. | `azureuser`|
|`admin_password`| Azure VM password. | `Password12345`|
|`offer`| The image used to build the VM. | `RHEL`|
|`publisher`| VM image publisher. | `RedHat`|
|`sku`| VM image SKU. | `8-LVM`|
|`image_version`| Verison of the Image. | `latest`|
|`vm_size`| A valid Azure VM size value. Choices vary depending on the subscription and location. `Standard_D2s_v3`|
|`publicIP`| Name of the Public IP.. | `ansible-middileware-ip`|
|`public_ip_address_name`| Name of the Public IP address name. | `ansible-middileware-public-ip`|
|`domain_name`| The customizable portion of the FQDN assigned to public IP address. This is an explicit setting. If no value is provided, any existing value will be removed on an existing public IP. | `rhsso`|
|`resource_groups`| Dictionary to get the details of resource groups. | `None`|
|`vm`| Dictionary to get the details of VM created for the intance" | `None`|

<!--end argument_specs-->

Dependencies
------------


Example Playbook
----------------

License
-------

GPL2

Author Information
------------------

* [Harsha Cherukuri](https://github.com/hcherukuri)
