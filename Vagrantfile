$node = <<-SCRIPT
sudo curl -fsSL https://deb.nodesource.com/setup_current.x | sudo -E bash -
sudo apt-get install -y nodejs
sudo npm config set unsafe-perm=true
SCRIPT

Vagrant.configure("2") do |config|
  config.vm.box = "hashicorp/bionic64"
  config.vm.network "public_network", ip: "192.168.25.104"
  config.vm.synced_folder ".", "/home/vagrant/development", type: "rsync"
  config.vm.provision "shell", inline: $node
end
