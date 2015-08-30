# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "ubuntu/trusty64" 
  config.vm.network "forwarded_port", guest: 80, host: 8080
  config.vm.network "private_network", ip: "192.168.123.123"
  # uncomment out the following line once you have provisioned the machine
  # config.vm.synced_folder "../", "/var/www/sites/localhost/", :owner => "www-data", :group => "www-data"
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "ansible/webservers.yml"
  end
  config.vm.provider "virtualbox" do |v|
    v.memory = 1024
  end
end
