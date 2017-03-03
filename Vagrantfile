Vagrant::Config.run do |config|

  config.vm.box = "precise32"
  config.vm.box_url = "http://files.vagrantup.com/precise32.box"

  config.vm.provision "fix-no-tty", type: "shell" do |s|
    s.privileged = false
    s.binary = true
    s.inline = "sudo sed -i '/tty/!s/mesg n/tty -s \\&\\& mesg n/' /root/.profile"
  end

  config.vm.network "forwarded_port", guest: 3000, host: 80, auto_correct: true
  config.vm.provision :shell,
    :inline => "sudo apt-get update && sudo apt-get -y install build-essential git ruby1.9.3 && sudo gem install bundler github-pages --no-ri --no-rdoc"

  config.ssh.forward_agent = true

  config.vm.provision :file, source: "~/.gitconfig", destination: ".gitconfig"
end
