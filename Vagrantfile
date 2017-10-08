
Vagrant.configure("2") do |config|

  config.vm.box = "ubuntu/trusty64"
  config.vm.network "private_network", ip: "192.168.33.10"
  #config.vm.synced_folder "\data", "/data"

  config.vm.provider "virtualbox" do |vb|
    vb.memory = "2048"
  end
  
  config.vm.provision "shell", inline: <<-SHELL

		
		apt-get update 
		
		apt-get install -y \
			linux-image-extra-$(uname -r) \
			linux-image-extra-virtual
		
		apt-get install -y \
			apt-transport-https \
			ca-certificates \
			curl \
			software-properties-common
				 
		curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
		
		sudo add-apt-repository \
		   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
		   $(lsb_release -cs) \
		   stable"
		   
		apt-get update 
		
		apt-get install -y docker-ce
   		
  SHELL
end
