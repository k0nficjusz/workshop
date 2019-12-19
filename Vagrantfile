# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  
  config.vm.define "w1" do |c1|
    c1.vm.provision "shell", inline: <<-SHELL
      useradd -m -s /bin/bash -U ansiblesrv -u 666 --groups wheel
      cp -pr /home/vagrant/.ssh /home/ansiblesrv/
      chown -R ansiblesrv:ansiblesrv /home/ansiblesrv
      echo "%ansiblesrv ALL=(ALL) NOPASSWD: ALL" > /etc/sudoers.d/ansiblesrv
      sed -i 's/PasswordAuthentication no/PasswordAuthentication yes/g' /etc/ssh/sshd_config
      systemctl restart sshd
      echo "ansiblesrv" | passwd --stdin ansiblesrv
      SHELL
    c1.vm.box = "centos/7"
    c1.vm.hostname = "w1"
    c1.vm.network "private_network", ip: "192.168.57.51"
    c1.vm.provider "virtualbox" do |vb|
      vb.memory = 2048
    end
  end

  config.vm.define "w2" do |c2|
    c2.vm.provision "shell", inline: <<-SHELL
      useradd -m -s /bin/bash -U ansiblesrv -u 666 --groups wheel
      cp -pr /home/vagrant/.ssh /home/ansiblesrv/
      chown -R ansiblesrv:ansiblesrv /home/ansiblesrv
      echo "%ansiblesrv ALL=(ALL) NOPASSWD: ALL" > /etc/sudoers.d/ansiblesrv
      sed -i 's/PasswordAuthentication no/PasswordAuthentication yes/g' /etc/ssh/sshd_config
      systemctl restart sshd
      echo "ansiblesrv" | passwd --stdin ansiblesrv
      SHELL
    c2.vm.box = "centos/7"
    c2.vm.hostname = "w2"
    c2.vm.network "private_network", ip: "192.168.57.52"
    c2.vm.provider "virtualbox" do |vb|
      vb.memory = 2048
    end
  end

  config.vm.define "w3" do |c3|
    c3.vm.provision "shell", inline: <<-SHELL
      useradd -m -s /bin/bash -U ansiblesrv -u 666 --groups sudo
      cp -pr /home/vagrant/.ssh /home/ansiblesrv/
      chown -R ansiblesrv:ansiblesrv /home/ansiblesrv
      echo "%ansiblesrv ALL=(ALL) NOPASSWD: ALL" > /etc/sudoers.d/ansiblesrv
      sed -i 's/PasswordAuthentication no/PasswordAuthentication yes/g' /etc/ssh/sshd_config
      service ssh restart
      echo -e "ansiblesrv\nansiblesrv" | passwd ansiblesrv
      SHELL
    c3.vm.synced_folder '.', '/vagrant', :disabled => true
    c3.vm.box = "debian/jessie64"
    c3.vm.hostname = "w3"
    c3.vm.network "private_network", ip: "192.168.57.53"
    c3.vm.provider "virtualbox" do |vb|
      vb.memory = 2048
    end
  end

  config.vm.define "w4" do |c4|
    c4.vm.provision "shell", inline: <<-SHELL
      useradd -m -s /bin/bash -U ansiblesrv -u 666 --groups wheel
      cp -pr /home/vagrant/.ssh /home/ansiblesrv/
      chown -R ansiblesrv:ansiblesrv /home/ansiblesrv
      echo "%ansiblesrv ALL=(ALL) NOPASSWD: ALL" > /etc/sudoers.d/ansiblesrv
      sed -i 's/PasswordAuthentication no/PasswordAuthentication yes/g' /etc/ssh/sshd_config
      systemctl restart sshd
      echo "ansiblesrv" | passwd --stdin ansiblesrv
      SHELL
    c4.vm.box = "centos/7"
    c4.vm.hostname = "w4"
    c4.vm.network "private_network", ip: "192.168.57.54"
    c4.vm.provider "virtualbox" do |vb|
      vb.memory = 2048
    end
  end

end




