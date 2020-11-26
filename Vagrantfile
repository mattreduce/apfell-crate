# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/bionic64"

  config.vm.disk :disk, size: "30GB", primary: true

  config.vm.provision :shell, path: "./setup.sh"

  # Expose Mythic admin UI on port 7443
  config.vm.network "forwarded_port", guest: 7443, host: 7443

  # Expose HTTP C2 Profile on host ports 4443 and 8080
  config.vm.network "forwarded_port", guest: 80, host: 8080
  config.vm.network "forwarded_port", guest: 443, host: 4443

  # Expose Websocket C2 Profile on host ports 8081
  config.vm.network "forwarded_port", guest: 8081, host: 8081
end
