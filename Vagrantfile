# Optimized for Vagrant 1.7 and above.
Vagrant.require_version ">= 1.7.0"

Vagrant.configure(2) do |config|

  config.vm.box = "generic/ubuntu1804"
  config.vm.network "forwarded_port", guest: 80, host: 8080

  # set RAM and CPUs
  ######################################################
  config.vm.provider "virtualbox" do |v|
    v.memory = 1024
    v.cpus = 1
  end

  config.vm.provider "libvirt" do |v|
    v.memory = 1024
    v.cpus = 1
  end

  #Use ansible to provision the application on the server
  ######################################################

  config.vm.provision "ansible" do |ansible|

    #ansible.verbose = "v"
    ansible.playbook = "infra-as-code.yml"
    ansible.become = "yes"
    ansible.become_user = "root"
  end
  ######################################################

end
  
