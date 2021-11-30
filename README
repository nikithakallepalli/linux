Team Members:
Nikitha Kallepalli  - 015355977
Lakshmi Gundlapalli - 015241122

Assignment Source Code: https://github.com/nikithakallepalli/linux/tree/master/cmpe283

Nikitha - 

-Installed VMware Workstation and created a VM with Ubuntu OS with 8 processors and 6GB RAM.
-Then mounted Ubuntu 20.4 iso image to the VM and then installed the Ubuntu Operating system in VMware Workstation.
-Enabled  the nested VM capability feature for the virtual Machine.
-Then, forked the  linux repsoitory from torvalds and then cloned the linux repository.
-Then, Built the latest linux source code 5.15.0+ version succesfully. 
-Once the kernal source code is built, I have added the code for entry based and secondary processor based structure and controls to print the messages for secondary proc based and entry based controls.

Lakshmi

-Installed VMware Workstation and created a VM with Ubuntu OS with 4 processors and 6GB RAM.
-Installed the necessary Devtools required to build, and run the linux source code.
-Installed the succesfully built linux source code into the already running 5.11 version Ubuntu VM to update it to 5.15.0+ version. 
-After running makefile to obtain output for pin based controls, proceeded with appending Exit based controls in detect_vmx_features, and structure definition code for exit based controls and primary processor based  controls, and structure definition.
-After succesful completion of merging the code re-inserted the updated kernel module again to the linux kernel code and verified the print message.
 
Execution Steps for OUTPUT:
-cd linux/cpme283
-make clean
-make 
-ls *.ko
-sudo rmmod cmpe283-1.ko
-sudo insmod cmpe283-1.ko
-dmesg
-when dmesg command is executed it gives the features information of all the pin based, primary proc based, secondary proc based, entry and exit controls.


Execution Steps for linux source code build and installation:
-git clone https://github.com/nikithakallepalli/linux.git
-cd linux
-git status
-git remote -v
-uname -a
-cp /boot/config-5.11.0-38-generic .config
-make prepare
-cd ..
-make -j 4 modules
-make -j 4
-sudo make INSTALL_MOD_STRIP=1 modules_install
-sude make install
-reboot

Steps to intsall the dependencies:
sudo apt install git
sudo apt install make
sudo apt install gcc
sudo apt install flex
sudo apt install bison
sudo apt-get install libssl-dev
sudo apt-get install libelf-dev

Assignment-2:

The assignment files are placed under linux/cmpe283/Assignment -2/

Nikitha:
● I have worked on CPUID leaf node %eax=0x4FFFFFFF.
● Modified the code in vmx.c to get the total number of exits.
●	Modified the code in cpuid.c to to get the total number of exits.
●	Installed the nested virtual machine inside the virtual machine.
● Ran CPUID Package with 0x4FFFFFFF in eax.
● Total number of exits is returned to eax.
Lakshmi:
●	I have worked on CPUID leaf node %eax=0x4FFFFFFE:
●	Modified the code in vmx.c to get the total time taken in handling the exits.
●	Modified the code in cpuid.c to to get the total time taken in handling the exits.
●	Installed CPUID Packege inside the nested VM.
●	Ran CPUID Package with 0x4FFFFFFE in eax.
● Total time taken higher32 bits are returned to ebx and lower32 bits are returned to ecx.

Commands for executing the Assignment2:
● We have edited the code in vmx.c and cpuid.c and ran the below commands
  make modules
  make -j -4 modules
  sudo bash
  sudo make INSTALL_MOD_STRIP=1 modules_install && make install
  sudo rmmod kvm-intel
  sudo rmmod kvm
  modprobe kvm
  modprobe kvm-intel
● Creating Inner Virtual Machine inside a VM using the below commands
  sudo apt update
  sudo apt install qemu-kvm libvirt-daemon-system libvirt-clients bridge-utils
  sudo systemctl status libvirtd
  sudo systemctl enable --now libvirtd
  sudo apt install virt-manager
  sudo virt-manager
  install ubuntu 20.4 iso image
● Installing CPUID Package
  downloaded the CPUID deb Package for AMD64(https://packages.ubuntu.com/bionic/admin/cpuid)
  installed the above package using the command install using sudo dpkg -i cpuid_20170122-1.deb
● We have ran the below commands in the inner VM which is inside a VM
  cpuid -l 0X4fffffff -s exit_number
  cpuid -l 0X4ffffffe -s exit_number
  The output for these commands are in the path: /linux/cmpe283/image/inner_vm.jpeg
● We ran the command dmesg in the outer VM which gave the output in the mentioned path below
  /linux/cmpe283/image/outer_vm.jpeg
  
  Assignment-3:
  
  Nikitha:
● I have worked on CPUID leaf node %eax=0x4FFFFFFC.
● Modified the code in vmx.c to get the total time spent in processing specific exit number provided in ecx.
●	Modified the code in cpuid.c to to get the higher 32 bits of exit processing time in ebx
●	Modified the code in cpuid.c to to get the Lower 32 bits of exit processing time in ecx
● Ran CPUID Package with 0x4FFFFFFC and exit number in ecx.

Lakshmi:
●	I have worked on CPUID leaf node %eax=0x4FFFFFFD:
●	Modified the code in vmx.c to get the number of exits for a given exit nuber in ecx.
●	Modified the code in cpuid.c to to get the total number of exits for a given exit number.
●	Ran CPUID Package with 0x4FFFFFFD and exit number in ecx.

Output:
● We have ran the below commands in the inner VM which is inside a VM
  cpuid -l 0X4ffffffc -s exit_number
  cpuid -l 0X4ffffffd -s exit_number
  
● We ran the command dmesg in the outer VM which gave the output.

Observations:
3. Comment on the frequency of exits – does the number of exits increase at a stable rate? Or are there 
more exits performed during certain VM operations? Approximately how many exits does a full VM 
boot entail?
The frequency of exits is increasing at a stable rate. From the screenshots mentioned in the path(before and after boot) we have observed that VM boot for all the exits entails up to ~6800000.
  
  
4. Of the exit types defined in the SDM, which are the most frequent? Least?

Most Frequent Exits:
●	Exit number 48 - EPT Violation
●	Exit number 32 - WRMSR
●	Exit number 1- External Interrupt
●	Exit number 12- HLT
●	Exit number 49- EPT misconfiguration
●	Exit number 10- CPUID
Least Frequent Exits :
●	Exit number 54 - WBINVD or WBNOINVD
●	Exit number 55 -  XSETBV
●	Exit number 29 - MOV DR

  
  
