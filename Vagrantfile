Vagrant.configure("2") do |config|
  config.vm.define "redis-consule-1" do |web|
    web.vm.box = "ubuntu/trusty64"
    web.vm.hostname = 'redis-consule-1-host'
    web.vm.box_url = "ubuntu/trusty64"
    # web_config.vm.forward_port 6379:6379
    # web_config.vm.forward_port 8500:8500

    web.vm.network :private_network, ip: "192.168.56.101"

    web.vm.provider :virtualbox do |v|
    #   v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
    #   v.customize ["modifyvm", :id, "--memory", 512]
    #   v.customize ["modifyvm", :id, "--name", "web"]
      v.gui = true
    end

    config.vm.provision "shell",
	    inline: "yum update -y device-mapper-libs"

	  config.vm.provision "docker" do |docker|
	    docker.run "redis"
	  end

	  config.vm.provision "docker" do |docker|
	    docker.run "consul"
	  end
  end

  config.vm.define "redis-consule-2" do |web|
    web.vm.box = "ubuntu/trusty64"
    web.vm.hostname = 'redis-consule-2-host'
    web.vm.box_url = "ubuntu/trusty64"
    # web_config.vm.forward_port 6379:6379
    # web_config.vm.forward_port 8500:8500

    web.vm.network :private_network, ip: "192.168.56.102"

    web.vm.provider :virtualbox do |v|
    #   v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
    #   v.customize ["modifyvm", :id, "--memory", 512]
    #   v.customize ["modifyvm", :id, "--name", "web"]
      v.gui = true
    end
  end

  config.vm.define "redis-consule-3" do |web|
    web.vm.box = "ubuntu/trusty64"
    web.vm.hostname = 'redis-consule-3-host'
    web.vm.box_url = "ubuntu/trusty64"
    # web_config.vm.forward_port 6379:6379
    # web_config.vm.forward_port 8500:8500

    web.vm.network :private_network, ip: "192.168.56.103"

    web.vm.provider :virtualbox do |v|
      # v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      # v.customize ["modifyvm", :id, "--memory", 512]
      # v.customize ["modifyvm", :id, "--name", "web"]
      v.gui = true
    end
  end
end