# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  
  config.vm.box = "precise64"

  config.ssh.forward_agent = true

  # Create a private network, which allows host-only access to the machine
  # using a specific IP.
  config.vm.network :private_network, ip: "192.168.111.222"

  # If keeping vagrant and provisioning in source older create src/ and uncomment
  # config.vm.synced_folder "src/", "/home/vagrant"

  # config.vm.provider "virtualbox" do |v|
  #   v.customize ["modifyvm", :id, "--memory", "4096", "--vram", "128"]
  # end

  #provisions the environment
  config.vm.provision "ansible" do |ansible|
    ansible.raw_arguments = "-i provisioning/hosts"
    ansible.playbook = "provisioning/mean.yml"
  end
end
