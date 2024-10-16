Vagrant.configure("2") do |config|

    # Configuración de Debian en modo texto (venus)
    config.vm.define "venus" do |venus|
      venus.vm.box = "debian/bookworm64"
      venus.vm.hostname = "venus.sistema.test"
      venus.vm.network "private_network", ip: "192.168.57.102"
      venus.vm.provider "virtualbox" do |vb|
        vb.memory = "512"
      venus.vm.provision "shell", inline: <<-SHELL
        apt-get update
        apt-get install -y bind9 dnsutils
        SHELL
      end
    end

    # Configuración de Debian en modo texto (tierra)
    config.vm.define "tierra" do |tierra|
      tierra.vm.box = "debian/bookworm64"
      tierra.vm.hostname = "tierra.sistema.test"
      tierra.vm.network "private_network", ip: "192.168.57.103"
      tierra.vm.provider "virtualbox" do |vb|
        vb.memory = "512"
      tierra.vm.provision "shell", inline: <<-SHELL
        apt-get update
        apt-get install -y bind9 dnsutils
        SHELL
      end
    end
    
  end
end
