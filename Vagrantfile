# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  config.vm.define :ast1 do |ast1|
    ast1.vm.box = "selvax00y/Asterisk-13"
    ast1.vm.hostname = "asterisk1"
    ast1.vm.network :private_network, ip: "10.1.1.101"
    ast1.vm.network :public_network, ip: "192.168.8.41"
    ast1.vm.synced_folder "templates/", "/etc/asterisk"
    ast1.vm.provision :ansible do |ansible|
    ansible.playbook = "playbook.yml"
    end
  end
  config.vm.define :ast2 do |ast2|
    ast2.vm.box = "selvax00y/Asterisk-13"
    ast2.vm.hostname = "asterisk2"
    ast2.vm.network :private_network, ip: "10.1.1.102"
    ast2.vm.network :public_network, ip: "192.168.8.42"
    config.vm.synced_folder "templates2/", "/etc/asterisk"
    ast2.vm.provision :ansible do |ansible|
    ansible.playbook = "playbook.yml"
    end
  end
end
