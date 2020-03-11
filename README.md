# vagrant-vmconfig
This repo contains code with which you can change the vm config in the provider.In this case virtualbox

# What is this repo for

This repo contains code that when executed will create one virtualbox machine that will have a running web server on it.The VM will have the specs listed in the code 2CPUs, 2Gb moemry . How to do that you will see [below](#how-to-use-this-repo).


# Why use this repo

You might want to use this repo to gain a better understanding of how Vagrant can work for you. 
Here we create one vm and modify its specs by using the virtualbox provider.


# How to use this repo

* You need to have vagrant installed on you workstation
   *  for MacOS
   
    ```
    brew install vagrant
    ```
  
   *  for any other OS click [here](https://www.vagrantup.com/downloads.html).

* You also need to have virtualbox installed since this is the virtualization provider we are using in this example.

   * Download [Here](https://www.virtualbox.org/wiki/Downloads)
  
* This "How to" will cover macOS specifically, it may vary for other systems.

* Clone this repo locally to a folder of your choice
```
git clone git@github.com:yordanivh/vagrant-vmconfig.git
```
* Go inside the newly created folder of the repo

```
cd vagrant-vmconfig
```
* Give command to start the machine

```
vagrant up
```
* This is an expected output

```
❯ vagrant up
Bringing machine 'yordanVM' up with 'virtualbox' provider...
==> yordanVM: Importing base box 'yordan/box'...
==> yordanVM: Matching MAC address for NAT networking...
==> yordanVM: Checking if box 'yordan/box' version '1.0.0' is up to date...
==> yordanVM: Setting the name of the VM: yordanVM
==> yordanVM: Clearing any previously set network interfaces...
==> yordanVM: Preparing network interfaces based on configuration...
    yordanVM: Adapter 1: nat
==> yordanVM: Forwarding ports...
    yordanVM: 22 (guest) => 2222 (host) (adapter 1)
==> yordanVM: Running 'pre-boot' VM customizations...
==> yordanVM: Booting VM...
==> yordanVM: Waiting for machine to boot. This may take a few minutes...
    yordanVM: SSH address: 127.0.0.1:2222
    yordanVM: SSH username: vagrant
    yordanVM: SSH auth method: private key
    yordanVM: 
    yordanVM: Vagrant insecure key detected. Vagrant will automatically replace
    yordanVM: this with a newly generated keypair for better security.
    yordanVM: 
    yordanVM: Inserting generated public key within guest...
    yordanVM: Removing insecure key from the guest if it's present...
    yordanVM: Key inserted! Disconnecting and reconnecting using new SSH key...
==> yordanVM: Machine booted and ready!
==> yordanVM: Checking for guest additions in VM...
==> yordanVM: Setting hostname...
==> yordanVM: Mounting shared folders...
    yordanVM: /vagrant => /Users/yhalachev/repos/vagrant-vmconfig
```

* After the above is finished you should have one virtual macine named `yordanVM` . You can confirm this by running `vagrant status`

```
❯ vagrant status
Current machine states:

yordanVM                  running (virtualbox)

The VM is running. To stop this VM, you can run `vagrant halt` to
shut it down forcefully, or you can run `vagrant suspend` to simply
suspend the virtual machine. In either case, to restart it again,
simply run `vagrant up`.
```
* Login to the machine to verify memory and cpu

```
vagrant ssh
```
* Here is the memory and cpu infromation from the machine

```
vagrant@yordanVM:~$ free -m 
              total        used        free      shared  buff/cache   available
Mem:           2000          34        1667           3         298        1813
```
```
vagrant@yordanVM:~$ nproc --all
2
```
* When you are done with this destroy the created environment to save resources

```
vagrant destroy
```
