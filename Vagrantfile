# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/focal64"

  # config.vm.network "private_network", ip: "192.168.33.10"
  # config.vm.synced_folder "../data", "/vagrant_data"

  config.vm.provision "shell", inline: <<-SHELL
    set -x
    apt-get update
    apt-get -y upgrade
    DEBIAN_FRONTEND=noninteractive apt-get install -y apt-transport-https ca-certificates curl gnupg lsb-release
    DEBIAN_FRONTEND=noninteractive apt-get install -y jq tree
    DEBIAN_FRONTEND=noninteractive apt-get install -y docker.io cgroup-tools
    gpasswd -a vagrant docker
    docker pull alpine
    docker pull ubuntu
    docker pull nginx
  SHELL
end
