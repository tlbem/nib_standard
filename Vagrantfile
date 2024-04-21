Vagrant.configure("2") do |config|
  config.ssh.forward_agent = true
  config.vm.box = "debian/bookworm64"
  config.vm.network "private_network", type: "dhcp"
  config.vm.network :forwarded_port, :guest => 8080, :host => 8080, auto_correct: true  
  config.vm.provider "virtualbox" do |v|
    v.customize ['modifyvm', :id, '--nictype1', 'virtio']
    v.memory = 8192
    v.cpus = 8
  end
  config.vm.provision "shell", 
    path: "provision.sh"
end
