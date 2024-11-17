Vagrant.configure("2") do |config|
  # Definir as VMs para o Docker Swarm
  config.vm.define "master" do |master|
    master.vm.box = "ubuntu/bionic64"
    master.vm.network "private_network", type: "dhcp"
    master.vm.network "private_network", type: "static", ip: "192.168.50.10"
    master.vm.provider "virtualbox" do |vb|
      vb.memory = "1024"
    end

    master.vm.provision "docker" do |d|
      d.run "docker", args: "docker-ce docker-ce-cli containerd.io"
    end

    master.vm.provision "shell", inline: <<-SHELL
      # Atualizar pacotes e instalar Docker
      sudo apt-get update
      sudo apt-get install -y docker.io
      sudo systemctl enable docker
      sudo systemctl start docker
    SHELL
  end

  config.vm.define "node01" do |node1|
    node1.vm.box = "ubuntu/bionic64"
    node1.vm.network "private_network", type: "static", ip: "192.168.50.11"
    node1.vm.provider "virtualbox" do |vb|
      vb.memory = "1024"
    end

    node1.vm.provision "docker" do |d|
      d.run "docker", args: "docker-ce docker-ce-cli containerd.io"
    end

    node1.vm.provision "shell", inline: <<-SHELL
      sudo apt-get update
      sudo apt-get install -y docker.io
      sudo systemctl enable docker
      sudo systemctl start docker
    SHELL
  end

  config.vm.define "node02" do |node2|
    node2.vm.box = "ubuntu/bionic64"
    node2.vm.network "private_network", type: "static", ip: "192.168.50.12"
    node2.vm.provider "virtualbox" do |vb|
      vb.memory = "1024"
    end

    node2.vm.provision "docker" do |d|
      d.run "docker", args: "docker-ce docker-ce-cli containerd.io"
    end

    node2.vm.provision "shell", inline: <<-SHELL
      sudo apt-get update
      sudo apt-get install -y docker.io
      sudo systemctl enable docker
      sudo systemctl start docker
    SHELL
  end

  config.vm.define "node03" do |node3|
    node3.vm.box = "ubuntu/bionic64"
    node3.vm.network "private_network", type: "static", ip: "192.168.50.13"
    node3.vm.provider "virtualbox" do |vb|
      vb.memory = "1024"
    end

    node3.vm.provision "docker" do |d|
      d.run "docker", args: "docker-ce docker-ce-cli containerd.io"
    end

    node3.vm.provision "shell", inline: <<-SHELL
      sudo apt-get update
      sudo apt-get install -y docker.io
      sudo systemctl enable docker
      sudo systemctl start docker
    SHELL
  end
end
