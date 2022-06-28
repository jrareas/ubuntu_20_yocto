$vm_memory = 6144
$vm_cpus = 4
$static_ip = "192.168.60.252"
Vagrant.configure("2") do |config|
  config.vm.provider :virtualbox do |vb|
    vb.gui = false
    vb.cpus = $vm_cpus
    vb.memory = $vm_memory
  end
  config.nfs.map_uid = Process.uid
  config.nfs.map_gid = Process.gid
  config.disksize.size = '100GB'
  #
  # Run Ansible from the Vagrant Host
  #
  config.vm.network :private_network, ip: $static_ip
  config.vm.hostname = "yocto.local"
  config.vm.box = "ubuntu/focal64"
  config.vm.synced_folder './', '/opt/src', :nfs => false, :create => true
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbook.yml"
  end
end
