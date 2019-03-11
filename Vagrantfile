Vagrant.configure("2") do |config|
    config.vm.define :ansible do |ansible|
        ansible.vm.box = "ubuntu/bionic64"
        ansible.vm.network "private_network", ip: "192.168.1.10"
        ansible.vm.provision "shell", path: "provision/ansible.sh"
        ansible.vm.provider "virtualbox" do |ansible_provider|
            ansible_provider.memory = 512
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

    config.vm.define :jenkins do |jenkins|
        jenkins.vm.box = "ubuntu/xenial64"
        jenkins.vm.network "private_network", ip: "192.168.1.30"
        jenkins.vm.provision "shell", path: "provision/add_ssh_key.sh"
        jenkins.vm.provider "virtualbox" do |jenkins_provider|
            jenkins_provider.memory = 1024
        end
    end

    config.vm.define :sonar do |sonar|
        sonar.vm.box = "ubuntu/xenial64"
        sonar.vm.network "private_network", ip: "192.168.1.40"
        sonar.vm.provision "shell", path: "provision/add_ssh_key.sh"
        sonar.vm.provider "virtualbox" do |sonar_provider|
            sonar_provider.memory = 2048
        end
    end
end