Vagrant.configure("2") do |config|

  config.vm.define "proxy", primary: true do |proxy|
    proxy.vm.box = "ubuntu/jammy64"
    proxy.vm.network :private_network, ip: "192.168.1.102"
    proxy.vm.define "proxy" do |t|
    end
    proxy.vm.provider "virtualbox" do |v|
      v.name = "proxy"
    end


  end

  config.vm.define "web1" do |web1|
    web1.vm.box = "ubuntu/jammy64"
    web1.vm.network :private_network, ip: "192.168.1.103"
    web1.vm.define "web1" do |t|
    end
    web1.vm.provider "virtualbox" do |v|
      v.name = "web1"
    end

  end

  config.vm.define "web2" do |web2|
    web2.vm.box = "ubuntu/jammy64"
    web2.vm.network :private_network, ip: "192.168.1.104"
    web2.vm.define "web2" do |t|
    end
    web2.vm.provider "virtualbox" do |v|
      v.name = "web2"
    end

  end

  config.vm.define "client" do |client|
    client.vm.box = "gusztavvargadr/ubuntu-desktop"
    client.vm.network :private_network, ip: "192.168.1.105"
    client.ssh.username = 'vagrant'
    client.ssh.password = 'vagrant'
    client.hostsupdater.aliases = {
    '192.168.1.102' => ['ns1.ru'],
    '192.168.1.102' => ['ns2.ru']
    }
    client.vm.define "client" do |t|
    end
    client.vm.provider "virtualbox" do |v|
      v.name = "client"
    end

  end
  


end
