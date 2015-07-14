VAGRANTFILE_API_VERSION = "2"

ip = "192.168.10.10"
name = "vagrant local"
memory = "1024"
cpu = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
    config.vm.box = "ubuntu/trusty64"
    config.vm.network :private_network, ip: ip
    
    config.vm.provider "virtualbox" do |v|
        v.name = name
        v.customize ["modifyvm", :id, "--memory", memory]
        v.customize ["modifyvm", :id, "--cpus", cpu]
        v.customize ["modifyvm", :id, "--vram", "8"]
    end
    
    config.vm.provision "shell", inline: "sudo apt-get -y update"
end
