VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(2) do |config|

  config.vm.box = "ubuntu/trusty64"
  # Providers
  config.vm.provider :virtualbox do |p|
    p.customize ['modifyvm', :id, '--memory', '3056']
  end


# Disable the new default behavior introduced in Vagrant 1.7, to
# ensure that all Vagrant machines will use the same SSH key pair.
# See https://github.com/mitchellh/vagrant/issues/5005
  config.ssh.insert_key = false

  config.vm.provision "ansible" do |ansible|
    ansible.verbose = "vv"
    ansible.playbook = "playbook.yml"
  end
end