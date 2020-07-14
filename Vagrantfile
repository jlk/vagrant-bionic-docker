$install_docker_script = <<-DOCKER_SCRIPT
    sudo apt-get update
    sudo apt-get upgrade -y
    sudo apt-get install -y apt-transport-https ca-certificates curl gnupg-agent software-properties-common
    curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
    sudo add-apt-repository \
    "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
    $(lsb_release -cs) \
    stable"
    sudo apt-get update
    sudo apt-get install -y docker-ce docker-ce-cli containerd.io
    sudo usermod --append --groups docker vagrant

DOCKER_SCRIPT

$install_docker_compose_script = <<-DOCKER_COMPOSE_SCRIPT
    sudo curl -L "https://github.com/docker/compose/releases/download/1.26.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
    chmod 755 /usr/local/bin/docker-compose

DOCKER_COMPOSE_SCRIPT

Vagrant.configure("2") do |config|
    config.vm.box = "ubuntu/bionic64"
    config.vm.network "public_network"
    config.vm.synced_folder ".", "/vagrant"
    config.vm.provision "shell", inline: $install_docker_script
    config.vm.provision "shell", inline: $install_docker_compose_script
end
