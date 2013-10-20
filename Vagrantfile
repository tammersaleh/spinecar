# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"
VM_COUNT=2

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  # Tiny machines
  config.vm.provider "vmware_fusion" do |v|
    v.vmx["memsize"] = "512"
    v.vmx["numvcpus"] = "1"
  end

  config.vm.box = "coreos"
  config.vm.box_url = "http://storage.core-os.net/coreos/amd64-generic/109.0.0/coreos_production_vagrant_vmware_fusion.box"

  (1..VM_COUNT).each do |i|
    config.vm.define vm_name = "vm#{i}" do |config|
      config.vm.hostname = vm_name
      config.vm.network :private_network, ip: "192.168.20.#{i+1}"
    end
  end
end

