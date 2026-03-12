---
layout: post
title: "Receipe of Manually Creating and Configuring a Virtual Machine with Virtual Box in Ubuntu"
date: 2026-03-12 
tags: [Jekyll, GitHub, 4G, 5G, Mobile Cellular Networking,Evolved Packet Core, EPC, Magma Core, Blog, Website, Linux, Ubuntu, Ubuntu 20.04, virtual machine, Virtual Box, Manual Configuration, VM recipe, PacketRusher]
---
In this tutorial I have demonstrated the creation of a virtual machine with virtual box in Ubuntu 20.04. But the same recipe will hold true for any other Ubuntu version.

This vm has been created to run [PacketRusher][Packet-Rusher] to simulate a telecom network with [Magma Core][magma-core]. But you can modify according to your purpose.

First you need to install virtual box.
Next you need to install an iso image of the operating system which you want to use in the VM.

Now, you need to configure the initial setups for the creation of a virtual machine.

Click New to start the creation.

![Selecting-OS-iso](/assets/virtual-box/first-step.png)

Click next, here we will not be going forward with expert mode.

Enter your username and passwork. Click Next

![Enter u pw](/assets/virtual-box/second-step.png)

Select the amount of memeory and the no. of processors you want to allot. Click Next.
![hardware](/assets/virtual-box/harware.png)


![virtualHardDisk](/assets/virtual-box/virtualHardDisk.png)

Check the summary and click Finish. The virtual machine will be created.

Choose your language. Press Enter to select and move to next step.
![language](/assets/virtual-box/language.png)

![installerUpdate](/assets/virtual-box/installerUpdate.png)

![keyboardLayout](/assets/virtual-box/keyboardLayout.png)

![networkConnection](/assets/virtual-box/networkConnection.png)

![ConfigureProxy](/assets/virtual-box/ConfigureProxy.png)

![archiveMirror](/assets/virtual-box/archiveMirror.png)

Press tab until you reach Done. Click Enter.
![GuidedStorageConfiguration](/assets/virtual-box/GuidedStorageConfiguration.png)

![finalSystemSummary](/assets/virtual-box/finalSystemSummary.png)

![hConfirm](/assets/virtual-box/Confirm.png)

![profileSetup](/assets/virtual-box/profileSetup.png)

![sshSetup](/assets/virtual-box/sshSetup.png)

![featuredServerSnaps](/assets/virtual-box/featuredServerSnaps.png)

![installing](/assets/virtual-box/installing.png)

![rebootNow](/assets/virtual-box/rebootNow.png)

Power OFF vm and setup the networking of the vm.
![powerOffvm](/assets/virtual-box/powerOffvm.png)

![adapter1NAT](/assets/virtual-box/adapter1NAT.png)

![adapter2](/assets/virtual-box/adapter2.png)

Turn on the vm and next we configure ssh to be able to access it remotely from terminal with a lot of freedom.

If all the steps are alright then the visual will be similar to below when you login into your vm.
![alright.png](/assets/virtual-box/alright.png)

{% highlight ruby %}
Following promts to configure ssh:

sudo apt update && sudo apt upgrade -y
sudo apt install -y openssh-server curl wget git

Next we have to configure IP address for the vm:

sudo nano /etc/netplan/00-installer-config.yaml
{% endhighlight ruby %}

![netplan-ip](/assets/virtual-box/netplan-ip.png)

To Save: cltr+shift+o -> press Enter -> cltr+X

{% highlight ruby %}
To apply the configurations:
sudo netplan apply
{% endhighlight ruby %}

Ping is success from another vm. IP configuration a sucsess!
![ping-ip-success](/assets/virtual-box/ping-ip-success.png)

You can ping from host too, to check if ip is alright.

Next ssh into the vm from terminal:
ssh username@ip-address
![sshIntoPacketrusher](/assets/virtual-box/sshIntoPacketrusher.png)

You can clone your VM too, it will save a lot of time when trying to create another vm.

I go on to do a full clone. You can choose according to your purpose.
Keep in mind to chnage ip address of cloned machine to avoid conflicts.

![cloned](/assets/virtual-box/cloned.png)


[Packet-Rusher]: https://github.com/HewlettPackard/PacketRusher
[magma-core]: https://magmacore.org/

