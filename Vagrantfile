VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.box = "ubuntu/trusty64"

  # This Network configuration creates a Redis server accessible at the specified IP address
  #config.vm.network "private_network", ip: "192.168.30.99"
  # This Network configuration creates a Redis server accessible at "localhost", with only port 6379 being accessible
  config.vm.network :forwarded_port, guest: 6379, host: 6379

  config.vm.provider :virtualbox do |vbox|
    vbox.customize ["modifyvm", :id, "--memory", 1024]
  end

  config.vm.provision :shell, :path => "init.sh"
end
