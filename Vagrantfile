# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "ubuntu/trusty64"

  if Vagrant.has_plugin?('vagrant-cachier')
    config.cache.scope = :box
  else
    puts "Run `vagrant plugin install vagrant-cachier` to reduce caffeine intake when provisioning"
  end

  config.vm.define "dev", primary: true do |dev|
    dev.vm.provision "ansible" do |ansible|
      ansible.playbook = 'provisioning/dev.yml'
      ansible.verbose = 'vvv'
    end
  end

end
