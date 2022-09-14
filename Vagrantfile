Vagrant.configure("2") do |config|

  config.vm.define "controller" do |controller|
    	controller.vm.box = "ubuntu/focal64"
	controller.vm.network "public_network", ip: "192.168.34.41"
  controller.vm.provider "virtualbox" do |vb|
     	vb.memory = "1024"
  end
	controller.vm.provision "shell", inline: <<-SHELL
		sudo apt update -y
	  	sudo apt install software-properties-common -y
	  	sudo add-apt-repository --yes --update ppa:ansible/ansible
	  	sudo apt install ansible -y
	  	sudo cat /vagrant/hostname_ansible.txt >> /etc/hosts
	SHELL
  end

  config.vm.define "web01" do |web01|
    	web01.vm.box = "generic/centos8"
	web01.vm.network "public_network", ip: "192.168.34.42"
	web01.vm.provision "shell", inline: <<-SHELL
		sudo hostnamectl set-hostname web01
	SHELL
  end
  
  config.vm.define "web02" do |web02|
    	web02.vm.box = "generic/centos8"
	web02.vm.network "public_network", ip: "192.168.34.43"
	web02.vm.provision "shell", inline: <<-SHELL
		sudo hostnamectl set-hostname web02
	SHELL
  end
  
  config.vm.define "web03" do |web03|
    	web03.vm.box = "ubuntu/focal64"
	web03.vm.network "public_network", ip: "192.168.34.44"
	web03.vm.provision "shell", inline: <<-SHELL
		sudo hostnamectl set-hostname web03
	SHELL
  end

  config.vm.define "db01" do |db01|
    	db01.vm.box = "generic/centos8"
    	db01.vm.network "public_network", ip: "192.168.34.45"
	db01.vm.provision "shell", inline: <<-SHELL
		sudo hostnamectl set-hostname db01
	SHELL
  end

end
