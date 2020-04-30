# Running Kubernetes on Microk8s

This tutorial will focus on using a tool called [Microk8s](https://microk8s.io/).

Microk8s works on Linux, MacOS, and Windows you can find the instructions for your OS of choice on the [Getting Started guide for Microk8s](https://microk8s.io/#get-started).

## Linux

#### Install the Microk8s Snap.
```console
sudo snap install microk8s --classic --channel=1.18/stable
```
Don’t have the ```snap``` command? [Get set up for snaps.](https://snapcraft.io/docs/installing-snapd)

#### Join the group
MicroK8s creates a group to enable seamless usage of commands which require admin privilege. To add your current user to the group and gain access to the ```.kube``` caching directory, run the following two commands: 
```console
sudo usermod -a -G microk8s $USER
```
```console
sudo chown -f -R $USER ~/.kube
```
You will also need to re-enter the session for the group update to take place:
```console
su - $USER
```

#### Check the status
MicroK8s has a built-in command to display its status. During installation you can use the ```--wait-ready``` flag to wait for the Kubernetes services to initialise: 
```console
sudo microk8s status --wait-ready
```
… or to see the running services: 
```console
microk8s kubectl get services
```
MicroK8s uses a namespaced ```kubectl``` command to prevent conflicts with any existing installs of kubectl. If you don't have an existing install, it is easier to add an alias (append to ```~/.bash_aliases)``` like this:
```console
alias kubectl='microk8s kubectl'
```

#### Turn on standard services
```console
sudo microk8s enable dns dashboard registry
```
Similarly, ```microk8s disable``` turns off a service. Try ```microk8s enable --help``` for a list of available services built in.

#### Working with Microk8s
Visit the [docs](https://microk8s.io/docs/) to 


## MacOS

#### Install Multipass for MacOS
[Download Multipass for MacOS](https://github.com/canonical/multipass/releases/download/v1.2.1/multipass-1.2.1%2Bmac-Darwin.pkg)

#### Launch a Multipass instance
```console
multipass launch --name microk8s-vm --mem 4G --disk 40G
```
#### Enter the VM instance
```console
multipass shell microk8s-vm
```
#### Install the Microk8s Snap.
```console
sudo snap install microk8s --classic --channel=1.18/stable
```
Don’t have the ```snap``` command? [Get set up for snaps.](https://snapcraft.io/docs/installing-snapd)

#### Join the group
MicroK8s creates a group to enable seamless usage of commands which require admin privilege. To add your current user to the group and gain access to the ```.kube``` caching directory, run the following two commands: 
```console
sudo usermod -a -G microk8s $USER
```
```console
sudo chown -f -R $USER ~/.kube
```
You will also need to re-enter the session for the group update to take place:
```console
su - $USER
```

#### Check the status
MicroK8s has a built-in command to display its status. During installation you can use the ```--wait-ready``` flag to wait for the Kubernetes services to initialise: 
```console
sudo microk8s status --wait-ready
```
… or to see the running services: 
```console
microk8s kubectl get services
```
MicroK8s uses a namespaced ```kubectl``` command to prevent conflicts with any existing installs of kubectl. If you don't have an existing install, it is easier to add an alias (append to ```~/.bash_aliases)``` like this:
```console
alias kubectl='microk8s kubectl'
```

#### Turn on standard services
```console
sudo microk8s enable dns dashboard registry
```
Similarly, ```microk8s disable``` turns off a service. Try ```microk8s enable --help``` for a list of available services built in.

#### Working with Microk8s
Visit the [docs](https://microk8s.io/docs/) to 



## Windows

#### Install Multipass for Windows
[Download Multipass for Windows](https://github.com/canonical/multipass/releases/download/v1.2.1/multipass-1.2.1%2Bwin-win64.exe)

#### Launch a Multipass instance
```console
multipass launch --name microk8s-vm --mem 4G --disk 40G
```
#### Enter the VM instance
```console
multipass shell microk8s-vm
```
#### Install the Microk8s Snap.
```console
sudo snap install microk8s --classic --channel=1.18/stable
```
Don’t have the ```snap``` command? [Get set up for snaps.](https://snapcraft.io/docs/installing-snapd)

#### Join the group
MicroK8s creates a group to enable seamless usage of commands which require admin privilege. To add your current user to the group and gain access to the ```.kube``` caching directory, run the following two commands: 
```console
sudo usermod -a -G microk8s $USER
```
```console
sudo chown -f -R $USER ~/.kube
```
You will also need to re-enter the session for the group update to take place:
```console
su - $USER
```

#### Check the status
MicroK8s has a built-in command to display its status. During installation you can use the ```--wait-ready``` flag to wait for the Kubernetes services to initialise: 
```console
sudo microk8s status --wait-ready
```
… or to see the running services: 
```console
microk8s kubectl get services
```
MicroK8s uses a namespaced ```kubectl``` command to prevent conflicts with any existing installs of kubectl. If you don't have an existing install, it is easier to add an alias (append to ```~/.bash_aliases)``` like this:
```console
alias kubectl='microk8s kubectl'
```

#### Turn on standard services
```console
sudo microk8s enable dns dashboard registry
```
Similarly, ```microk8s disable``` turns off a service. Try ```microk8s enable --help``` for a list of available services built in.

#### Working with Microk8s
Visit the [docs](https://microk8s.io/docs/) to 


