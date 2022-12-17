Vagrant.configure("2") do |config|

    ## 2 ubuntu VMs 
    (10..13).each do |i|
      config.vm.define "ubuntu#{i}" do | ubuntu |
        ubuntu.vm.box = "ubuntu/hirsute64"
        ubuntu.vm.hostname = "ubuntu#{i}"

        ubuntu.vm.network "public_network", ip: "192.168.1.#{i+250}"
        ubuntu.vm.network "private_network", ip: "192.168.56.#{i}"

      end
    end 
  
  
    ## Performance options ##
    # tweak or remove these as you see fit:
    config.vm.box_check_update = false
  
    # provider (hypervisor in vagrant parlance):
      # docs: https://www.vagrantup.com/docs/providers/basic_usage.html#default-provider
      # vagrant will search for first configured provider, unless you use one of these overrides:
        # `--provider` CLI option
        # `VAGRANT_DEFAULT_PROVIDER` environment variable
      # VirtualBox is a great cross platform, free hypervisor 
        # I recommend using it 
        # If you change providers, make sure the boxes above have a build for said provider.
    config.vm.provider "virtualbox" do |v|
  
      # add vboxmanage customizations here:
      # https://www.vagrantup.com/docs/virtualbox/configuration.html
      # "convenience shortcuts for memory and CPU settings:" (per link above), tweak to your machine's capabilities to speed up VMs:
        v.memory = 2048
        v.cpus = 2
  
    end
  
  end
   
