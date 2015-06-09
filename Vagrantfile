# -*- mode: ruby -*-
# vi: set ft=ruby :

MEMORY = 1024
CPU_COUNT = 2

Vagrant.configure("2") do |config|
  config.vm.box     = "ubuntu/trusty64"


  config.vm.network :private_network, ip: "192.168.50.3"

  # config.vm.synced_folder "/local/path/to/myapp", "/srv/myapp"
  # config.vm.synced_folder "/local/path/to/anotherapp", "/srv/anotherapp"

  config.vm.provider :virtualbox do |vb|
    vb.customize ["modifyvm", :id, "--memory", MEMORY.to_s]
    vb.customize ["modifyvm", :id, "--vtxvpid", "off"]
    vb.customize ["modifyvm", :id, "--cpus", CPU_COUNT.to_s]
  end

  config.vm.provision :ansible do |ansible|
    ansible.playbook = "ansible-playbooks/main.yml"
    # ansible.verbose = 'vvvv'
  end
end
