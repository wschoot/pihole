# vi: set ft=ruby ts=4 sw=4 expandtab:

Vagrant.configure("2") do |config|

    config.vm.box = "generic/debian10"
    #config.vm.box = "centos/7"
    config.vm.provider :libvirt do |vb|
        vb.memory = 4096
        vb.cpus = 4
    end

    # Uitgaande iface van je host
    config.vm.network "public_network", bridge: "eno1", dev: "eno1", ip: "192.168.88.200"

    config.vm.define "pihole" do |node|
        config.vm.hostname = "pihole.local"
    end

    config.vm.provision :ansible do |ansible|
        ansible.playbook = "playbook.yml"
        ansible.verbose = true
        ansible.compatibility_mode = "2.0"
    end
end

