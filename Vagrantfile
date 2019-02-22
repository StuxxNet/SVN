Vagrant.configure("2") do |config|
    config.vm.define :ansible do |ansible|
        ansible.vm.box = "ubuntu/bionic64"
        ansible.vm.network "private_network", ip: "192.168.1.10"
        ansible.vm.provision "shell", path: "provision/ansible.sh"
        ansible.vm.provider "virtualbox" do |ansible_provider|
            ansible_provider.memory = 1024
        end
    end

    config.vm.define :docker do |docker|
        docker.vm.box = "ubuntu/bionic64"
        docker.vm.network "private_network", ip: "192.168.1.20"
        docker.vm.provision "shell", path: "provision/add_ssh_key.sh"
        docker.vm.provider "virtualbox" do |docker_provider|
            docker_provider.memory = 1024
        end
    end
end