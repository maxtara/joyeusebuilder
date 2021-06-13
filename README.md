Joyeuse/Curtana builder
------------

Role/playbook for building android for cutana/joyeuse. Mostly run from bash scripts as the android tooling at least partially sets env variable.

The playbook:
  * Starts the VM. Waits for it to start
  * Logs on, sudo's, installs updates and dependencies
  * Logs on (as user). Build Lineage. Publishes to an SCP location
  * Shutdowns VM
  * Shutdowns Host


Requirements
------------

A Hyper-v VM setup with keys. 

Role Variables
--------------

```
ansible_ssh_common_args: I use a jump host, so this is set to jump through it
user_name: vm username
my_email: used for git
my_name: used for git
host_ip: vm ip
jump_host: jumphost ip.
publish_scp_uri: Where to copy the lineage image to
publish_http_url: Where the publish location is (http url)
vm_name: vm name
```

Dependencies
------------

None.

Run
----------------

```
# Setup inventory files
stuff
# Needed for WSL - which doesnt look in CWD by default apparently.
export ANSIBLE_CONFIG=./ansible.cfg 
# Run
ansible-playbook playbook.yml -v
```

License
-------

Apache 2.0

Author Information
------------------

Max
