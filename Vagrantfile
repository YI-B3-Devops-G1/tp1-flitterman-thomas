Vagrant.configure("2") do |config|
  config.vm.box = "hashicorp/bionic64"
  config.vm.provision :shell, path: "bootstrap.sh"
  config.vm.network "forwarded_port", guest: 80, host: 8080, id: "nginx"
  config.vm.network "forwarded_port", guest: 443, host: 8081, id: "nginx-secure"
  config.vm.network "forwarded_port", guest: 22, host: 8082, id: "ssh"
end
