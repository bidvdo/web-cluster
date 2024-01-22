Vagrant.configure("2") do |config|
    config.vm.box_check_update = false
  
    #HA Proxy server
    config.vm.define "proxy" do |proxy|
        proxy.vm.hostname = "proxy.local"
        proxy.vm.box = "ubuntu/focal64"
        proxy.vm.network :private_network, ip: "10.0.0.101"
        proxy.vm.network "forwarded_port", guest: 8080, host: 8080
    end
  
    #web01
    config.vm.define "web01" do |web01|
        web01.vm.hostname = "web01.local"
        web01.vm.box = "ubuntu/focal64"
        web01.vm.network :private_network, ip: "10.0.0.102"
    end
  
    #web02
    config.vm.define "web02" do |web02|
        web02.vm.hostname = "web02.local"
        web02.vm.box = "ubuntu/focal64"
        web02.vm.network :private_network, ip: "10.0.0.103"
    end
  
    config.vm.provider "virtualbox" do |vb|
        vb.gui = false
        vb.memory = "1024"
        vb.cpus = 1
    end
  end
