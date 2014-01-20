# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = 
  config.vm.box_url = 

  config.vm.define "awx" do |awx|
    awx.vm.network :private_network, ip: "192.168.251.10"
  end

  config.vm.define "web1" do |web1|
    web1.vm.network :private_network, ip: "192.168.251.11"
  end  

  config.vm.define "web2" do |web2|
    web2.vm.network :private_network, ip: "192.168.251.12"
  end  

  config.vm.define "db1" do |db1|
    db1.vm.network :private_network, ip: "192.168.251.13"
  end 

  config.vm.define "web3" do |web3|
    web3.vm.network :private_network, ip: "192.168.251.14"
  end 

  config.vm.define "mn1" do |mn1|
    mn1.vm.network :private_network, ip: "192.168.251.15"
  end
 
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "demo-site.yml"
    ansible.verbose = "v"
    ansible.sudo = "true"
    ansible.sudo_user = "root"
    ansible.host_key_checking = "false"
  end
end