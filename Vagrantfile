Vagrant.configure(2) do |config|
  vagrant_version = Vagrant::VERSION.sub(/^v/, '')
  config.env.enable
  config.vm.box = "ubuntu/trusty64"

  config.vm.provision "fix-no-tty", type: "shell" do |s|
    s.privileged = false
    s.binary = true
    s.inline = "sudo sed -i '/tty/!s/mesg n/tty -s \\&\\& mesg n/' /root/.profile"
  end

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine. In the example below,
  # accessing "localhost:8080" will access port 80 on the guest machine.
  config.vm.network "forwarded_port", guest: 4000, host: 4000

  # Disable default synced folder
  config.vm.synced_folder ".", "/vagrant", disabled: true

  if vagrant_version >= "1.3.0"
    config.vm.synced_folder "./", "/vagrant", create: true, :owner => "vagrant", :mount_options => [ "dmode=775", "fmode=774" ]
  else
    config.vm.synced_folder "./", "/vagrant", create: true, :owner => "vagrant", :extra => 'dmode=775,fmode=774'
  end

  config.ssh.forward_agent = true

  config.vm.provision :shell, path: "provision.sh", privileged: false, binary: true
  config.vm.provision :shell, path: "project.sh", privileged: false, binary: true

  config.vm.provision :file, source: "~/.gitconfig", destination: ".gitconfig"


end
