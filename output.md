Output example:
```
[vs]~/Downloads/ops-task-master [master] $ vagrant destroy  
    default: Are you sure you want to destroy the 'default' VM? [y/N] y
==> default: Forcing shutdown of VM...
==> default: Destroying VM and associated drives...
[vs]~/Downloads/ops-task-master [master] $ vagrant up       
Bringing machine 'default' up with 'virtualbox' provider...
==> default: Importing base box 'ubuntu/bionic64'...
==> default: Matching MAC address for NAT networking...
==> default: Checking if box 'ubuntu/bionic64' is up to date...
==> default: Setting the name of the VM: new-ubuntu-vm
==> default: Clearing any previously set network interfaces...
==> default: Preparing network interfaces based on configuration...
    default: Adapter 1: nat
    default: Adapter 2: hostonly
==> default: Forwarding ports...
    default: 3000 (guest) => 3000 (host) (adapter 1)
    default: 22 (guest) => 2222 (host) (adapter 1)
==> default: Running 'pre-boot' VM customizations...
==> default: Booting VM...
==> default: Waiting for machine to boot. This may take a few minutes...
    default: SSH address: 127.0.0.1:2222
    default: SSH username: vagrant
    default: SSH auth method: private key
    default: 
    default: Vagrant insecure key detected. Vagrant will automatically replace
    default: this with a newly generated keypair for better security.
    default: 
    default: Inserting generated public key within guest...
    default: Removing insecure key from the guest if it's present...
    default: Key inserted! Disconnecting and reconnecting using new SSH key...
==> default: Machine booted and ready!
==> default: Checking for guest additions in VM...
==> default: Setting hostname...
==> default: Configuring and enabling network interfaces...
==> default: Mounting shared folders...
    default: /vagrant => /Users/vs/Downloads/ops-task-master
==> default: Running provisioner: ansible...
Vagrant has automatically selected the compatibility mode '2.0'
according to the Ansible version installed (2.9.6).

Alternatively, the compatibility mode can be specified in your Vagrantfile:
https://www.vagrantup.com/docs/provisioning/ansible_common.html#compatibility_mode

    default: Running ansible-playbook...

PLAY [all] *********************************************************************

TASK [Gathering Facts] *********************************************************
ok: [default]

TASK [setting_hostname] ********************************************************
changed: [default]

TASK [set_timezone] ************************************************************
changed: [default]

TASK [install_system_packages] *************************************************
ok: [default] => (item=git)
changed: [default] => (item=apt-transport-https)
ok: [default] => (item=ca-certificates)
ok: [default] => (item=curl)
ok: [default] => (item=software-properties-common)
changed: [default] => (item=python3-pip)
changed: [default] => (item=python-virtualenv)
ok: [default] => (item=python3-setuptools)

TASK [Add Docker GPG key] ******************************************************
changed: [default]

TASK [add_docker_repo] *********************************************************
changed: [default]

TASK [install_docker] **********************************************************
changed: [default]

TASK [Install docker-compose] **************************************************
changed: [default]

TASK [create_new_user] *********************************************************
changed: [default]

TASK [adjust_user_demo_open_files_limit] ***************************************
[WARNING]: The value 100000 (type int) in a string field was converted to
'100000' (type string). If this does not look like what you expect, quote the
entire value to ensure it does not change.
changed: [default]

TASK [sysctl] ******************************************************************
changed: [default]

TASK [git] *********************************************************************
changed: [default]

TASK [run_ansible_tasks] *******************************************************
changed: [default]

PLAY RECAP *********************************************************************
default                    : ok=13   changed=12   unreachable=0    failed=0    skipped=0    rescued=0    ignored=0   

[vs]~/Downloads/ops-task-master [master] $ curl localhost:3000
welcome to api 1[vs]~/Downloads/ops-task-master [master] $ curl localhost:3000
welcome to api 2[vs]~/Downloads/ops-task-master [master] $ curl localhost:3000
welcome to api 3[vs]~/Downloads/ops-task-master [master] $ curl localhost:3000
welcome to api 4[vs]~/Downloads/ops-task-master [master] $ curl localhost:3000
welcome to api 5
```