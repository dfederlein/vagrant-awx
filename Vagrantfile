# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "centos64vagrantminimal"
  config.vm.box_url = 'https://vagrantboxdfed.s3.amazonaws.com/centos64vagrantminimal.box'

  config.vm.define "awx" do |awx|
    awx.vm.network :private_network, ip: "192.168.250.10"
  end

  config.vm.define "web1" do |web1|
    web1.vm.network :private_network, ip: "192.168.250.11"
  end  

  config.vm.define "web2" do |web2|
    web2.vm.network :private_network, ip: "192.168.250.12"
  end  

  config.vm.define "db1" do |db1|
    db1.vm.network :private_network, ip: "192.168.250.13"
  end 

  config.vm.define "web3" do |web3|
    web3.vm.network :private_network, ip: "192.168.250.14"
  end 

  config.vm.define "mn1" do |mn1|
    mn1.vm.network :private_network, ip: "192.168.250.15"
  end
 
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "demo-site.yml"
    ansible.verbose = "v"
    ansible.sudo = "true"
    ansible.sudo_user = "root"
    ansible.host_key_checking = "false"
  end
end