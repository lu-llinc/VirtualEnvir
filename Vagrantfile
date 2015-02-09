# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
	config.vm.box = "ubuntu/trusty64"
  config.vm.box_url = "https://vagrantcloud.com/ubuntu/trusty64"
  config.vm.provision :shell, :path => "provision.sh"

	config.vm.provider :virtualbox do |vb, override|
    ## Forward ports

    # IPython Notebook
    override.vm.network :forwarded_port, host: 8888, guest: 8888

    # Rstudio server
    override.vm.network :forwarded_port, host: 8787, guest: 8787

	end
  
  config.vm.provider "virtualbox" do |vb|
  	#vb.customize ["modifyvm", :id, "--vram", "100"]
    vb.customize ["modifyvm", :id, "--memory", "6000"]
  end
end
