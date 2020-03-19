VAGRANT_BOX = 'ubuntu/bionic64'
VM_NAME = 'new-ubuntu-vm'
VM_USER = 'vagrant'

Vagrant.configure(2) do |config|
  config.vm.box = VAGRANT_BOX
  
  # Actual machine name (will be changed later with ansible)
  config.vm.hostname = VM_NAME

  config.vm.provider "virtualbox" do |v|
    v.name = VM_NAME
    v.memory = 2048
  end
  config.vm.network "private_network", type: "dhcp"
  config.vm.network "forwarded_port", guest: 3000, host: 3000, protocol: "tcp"

  config.vm.provision :ansible do |ansible|
  	ansible.playbook = "ansible-demo.yml"
  end
end
