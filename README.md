# vagrant-hyperv-ubuntu18.04-docker
Just a repo to keep my stuff in for a Docker test system on a Windows/Hyper-V host.

# Setup
* set VAGRANT_HOME env var to where you want to store boxes
* add vagrant to path, i.e. $Env:Path += ";C:\HashiCorp\Vagrant\bin"
* vagrant init
* vagrant up

* Add the IP of your virtual machine to the ./inventory.yml file

# Unix subystem for Windows
1. Enable this under Windows Programs and Features
2. Install Ubuntu from the Microsoft App store
3. Open the ubuntu bash shell
* `apt update`
* `apt install ansible sshpass -y`
* `ansible-playbook -k -u vagrant -i ./inventory.yml ./docker.yml`