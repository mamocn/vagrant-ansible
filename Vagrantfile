Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/bionic64"
  config.vm.define :vprod do |vprod|
    vprod.vm.hostname="vprod"
    vprod.vm.network "private_network", ip: "10.10.0.12"
    vprod.vm.network "public_network", bridge: "wlp3s0"
  end
  config.vm.define :vdev do |vdev|
    vdev.vm.hostname="vdev"
    vdev.vm.network "private_network", ip: "10.10.0.11"
    vdev.vm.network "public_network", bridge: "wlp3s0"
	vdev.vm.provision "shell", path: "scripts/boostrap_ansible.sh"
	vdev.vm.provision "shell", path: "scripts/init.sh"
  end
end
