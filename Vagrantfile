Vagrant.configure("2") do |config|

    # Maquinaria imaginaria marte 192.168.57.101

    # Configuración de Debian en modo texto (venus)
    config.vm.define "venus" do |venus|
      venus.vm.box = "debian/bookworm64"
      venus.vm.hostname = "venus.sistema.test"
      venus.vm.network "private_network", ip: "192.168.57.102"
      venus.vm.provision "shell", inline: <<-SHELL
        apt-get update
        apt-get install -y bind9 dnsutils
        cp /vagrant/venus/named.conf.local /etc/bind/named.conf.local
        cp /vagrant/venus/named.conf.options /etc/bind/named.conf.options
        systemctl restart bind9
        SHELL
    end

    # Configuración de Debian en modo texto (tierra)
    config.vm.define "tierra" do |tierra|
      tierra.vm.box = "debian/bookworm64"
      tierra.vm.hostname = "tierra.sistema.test"
      tierra.vm.network "private_network", ip: "192.168.57.103"
      tierra.vm.provision "shell", inline: <<-SHELL
        apt-get update
        apt-get install -y bind9 dnsutils
        cp /vagrant/tierra/named.conf.local /etc/bind/named.conf.local
        cp /vagrant/tierra/named.conf.options /etc/bind/named.conf.options
        cp /vagrant/tierra/db.sistema.test /var/lib/bind/db.sistema.test
        cp /vagrant/tierra/db.192.168.57 /var/lib/bind/db.192.168.57
        systemctl restart bind9
        SHELL
      end

    # Maquinaria imaginaria marte 192.168.57.184

end
