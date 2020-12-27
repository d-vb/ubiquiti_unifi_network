# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "debian/stretch64"
  config.vm.network "public_network"
  config.vm.synced_folder ".", "/vagrant", disabled: true
  config.vm.provision "shell", inline: <<-shell
    sudo apt update
    sudo apt dist-upgrade -y

    wget -qO - https://www.mongodb.org/static/pgp/server-3.6.asc | sudo apt-key add -
    echo "deb http://repo.mongodb.org/apt/debian stretch/mongodb-org/3.6 main" | sudo tee /etc/apt/sources.list.d/mongodb-org-3.6.list
    sudo apt update
    sudo apt install -y mongodb-org

    sudo apt install -y apt-transport-https
    sudo wget -O /etc/apt/trusted.gpg.d/unifi-repo.gpg https://dl.ui.com/unifi/unifi-repo.gpg
    echo 'deb https://www.ui.com/downloads/unifi/debian stable ubiquiti' | sudo tee /etc/apt/sources.list.d/100-ubnt-unifi.list
    sudo apt update
    sudo apt install -y unifi
    sudo systemctl restart unifi.service
    echo https://$(ip address show dev eth1 scope global | awk '/inet / {split($2,var,"/"); print var[1]}'):8443
  shell
end
