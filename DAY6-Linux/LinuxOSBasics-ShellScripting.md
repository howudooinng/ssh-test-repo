Day - 6

Linux Operating System and Basics of Shell Scripting 

What is an operating system?  Purchase a Hardware — cpu — ram — i/o(hard disk or ssd)  Gaming Jenkins
Some softwares   You have software which you have to run on the hardware.  OS - bridge between software and hardware.  
LINUX, WINDOWS, MAC OS - all these are Operating systems.

USER —> APPLICATION —> Operating System —>  Hardware   and Vice Versa
  This is the life cycle.
 
Why LINUX?
— its a free OS
— highly secured
— lot of distributions(types of Linux)
— very fast (OS is heart of everything, so speed is needed)

Architecture of LINUX:

— Kernel - heart of the Linux OS 
—> heart of any os, which does device management
—> memory management
—> process management
—> Handling system related calls

— System libraries - Responsible for performing a Task.
— Compilers, User processors, System Related Softwares


What is Shell Scripting ? 
Commands through which we talk to linux os is called as Shell Commands/Scripting

Popular Shell Commands:

rm - remove file
rm -r - remove directory
mkdir - create directory
cat - to see inside a file
ls - list a file
Commands to check performance of the machine:
free -g - understand what is the memory of the server
nproc - no of cpu's in your server
df -h - disk size, usage of the disk size is also available through this command
top - all of the system details at one place.

Interview question - What is the command that you use to manage the cpu, memory?

All About Shell Script and Role of Shell Scripting for a DevOps Engineer? 

Automation — It is a process where we reduce the manual activity. 
Common is any field.

Basically A Tedious repeated task needs to be automated in an industry level enterprise projects.

touch — to create the file
ls -ltr — shows all the files in the directory
man ls — to know the command details in linux
vi/vim — to open the file to write into the file which got created

vi is by default available, vim has to e installed to be used

Why use touch/vi — commands? touch command is used mostly in touch commands
requirements - to create 1000 files, you cant use vim inside your script, as it opens the files during creation, if a lot of files gets opened, linux will run into a problem and that’s why during writing scripts we use touch command to create multiple files as it only creates the file unlike open it if we use vim/vi command.  #!/bin/bash/sh/ksh — called as shebang — need to give this in the script file before writing the script.
Why we do this she-bang ? bash/dash/sh/ksh - these are executables used to run shell scripts 
most commonly used is — bash

always use INSERT mode to edit the file — so press “i” to go into the insert mode.

How to save a file in Linux - press escape and then :wq!
 echo — command to print something

cat — command to see inside the file 

How to execute the script?
sh “filename”
./ “filename”

File Permissions — Who can execute this file. Linux wants to know and main purpose is security 

ls -l — shows permissions of the file 

drwxr-xr-x — if “d” is in front of this then it is a directory, else it is a file.
4 — “r”ead
2 — “w”rite
1  — “x”ecute

chmod — command to grant permission of a file

arguments in chmod command

— what are your permission in the file   — user
— which group has access to the file    — group
— which user has access to the file       — other users 

7 7 7 — user, group, all users 

read, write, execute — user, group, other users

mkdir — to create a folder command

cp <file name>  <destination folder name>

cp <file path> <destination name>

cp -r cloud/ devops/ ( to copy folder to folder)  mv <file name> ../cloud/ ( moves files from the current folder to the cloud folder a step back )

rename - use the move command only to rename 

wc <filename> output - lines, words, bytes

hard link : a shortcut which can be used to recover the main file even if the main file gets deleted.

soft link  : It cannot be recovered if the main file is deleted

ln -s file-path/ softlink-file

ln file-path/ hard link

tee - take input/ output to print on screen and put it into the file also.

diff - to see difference between two files 

syntax — diff <first file> <second file>

ssh(port - 22) - command to login into EC2 instance, 

ssh — connect through keys — key pair 

key pair - private key — local to server 
		    - public key  — server 

ssh-key gen

disk usage - df command 
ls -a — hidden files command

ps 
top — command which shows all the cpu usage and user ids present on the instance/Terminal
fuser
uname — which platform I am using to check command
uptime — to check time and user on the terminal
date — to check date
who — command to tell which users are logged in
whoami — only gives user’s username
which — tells the location of python/bash where it is installed
id — to check group id, user id and other details, if more users are added, it will also be visible using this command
sudo — of all users in Linux, the root user has all access and permissions (superuser). If a user needs elevated permissions, they use sudo
shutdown — to power off the system
reboot — to restart the system
apt — command to manage packages (install, update, remove)
apt-get — lower-level command to fetch/install packages from repositories
yum, dnf, pacman, portage — package managers for other Linux distributions


USER Management in Linux:

useradd — command to add user (-m) sudo useradd -m <username>
passwd — to add password for the user, sudo passwd <username> 

su — switch user (on AWS primary user information is shown on EC2, other user information is not shown like that)

cat /etc/passwd — command to shown recent user additions
cat /etc/group — command to show recent groups

whenever a user is added, a group is also created with that name

sudo gpasswd -a <user nam3> <groupname>
to check if the group is created or not:
cat /etc/group 

Command to add multiple users: 
sudo gpasswd -M <username1>,<Username2> <groupname>

Group delete:
sudo groupdel <groupname>

FILE PERMISSIONS IN LINUX:

ls -l — to check file permissions 

drwxrwxr-x - if “d” is there, then it is a folder, or linux vocabulary calls it as Directory. 

0 —>     —      —        —   
1 —>     —       —        X 
2 —>    —      W         —
3 —>    —      W         X
4 —>    R       —         —
5 —>    R      —          X
6 —>    R      W         —
7 —>     R     W          X

Order — Users Group OtherUsers

umask - gives a no which is the default permission for the files which are getting created in the linux system

chown
chgrp
tar — used for zip
untar — used for unzip


How to copy a file/folder from one server to other  ?

Copying file from Local to EC2 server:  
Syntax:
scp -i “path of your local server/pem_key_name.pem” file_name ubuntu@ec2 server name:/destination path/

Example: scp -i "/Users/howudooinng/Desktop/devops26.pem" secret_file.txt ubuntu@ec2-3-238-197-158.compute-1.amazonaws.com:/home/ubuntu

Copying folder from Local to EC2 server/ Vice Versa —> so in scenarios of copying from EC2 to local and viceversa, in both cases the scp command should be written on the local host/server, as the local server will initiate the connection for the file transfer.

scp -i “path of your local server/pem_key_name.pem” -r ubuntu@ec2 server name:/destination path/folder name .

scp -i "/Users/howudooinng/Desktop/devops26.pem" -r ubuntu@ec2-3-238-197-158.compute-1.amazonaws.com:/home/ubuntu/master_devops_linux .

rsync — command 
rsync -e  ssh -i /Users/howudooinng/Desktop/devops26.pem" -avz master_devops_linux ubuntu@ec2-3-238-197-158.compute-1.amazonaws.com:/home/ubuntu/master_devops_linux


Networking Commands using Linux: Ways to troubleshoot the applications

ping — command to see data is transferred or received correctly and packets are sent.
netstat — shows the network status 
ifconfig — shows network interface, lo — option is local host or loop back server (127.0.0.1)
traceroute youtube.com — shows the route of the request, ip hop 
tracepath youtube.com — shows the path of the request, ip hopping, these commands are used to check the latency, 30 times no reply and after that it says too many hops
mtr — my traceroute shows path and route together.
nslookup — 
telnet — 
ip — 
iwconfig — wireless connections it shows 
ss — same as netstat
dig — 
whois — shows all the domain info and the host website from where the website has been hosted 
nc — 
arp — address resolution protocol
ifplugstatus — 

Main Devops Commands: Day to day usage commands

curl — command to get the data through api 
jq — to modify the output(clean output)
wget — command to download anything from the internet 
watch — command to check the output every “2” seconds you mention

watch -n (time(inseconds)) <command>
example - watch -n 5 top

nmap — to scan the website / deployed applications, most production grade websites keep 80, 443 as open, 80 is for unencrypted/unsecured traffic which gets routed to 443 which is used for secured traffic.

EC2 server to local — SCP Transfer 
scp -i /Users/howudooinng/Desktop/devops26.pem ubuntu@ec2-3-238-197-158.compute-1.amazonaws.com:/home/ubuntu/master_devops_linux/linux_advanced/scp_test.txt /Users/howudooinng/Desktop/

Basic Reading of the Above command — scp -i, key location(desktop in this case) followed by EC2 connection: file jo transfer krna hai uska location, followed by file transfer jaha hoga uska location —> easy and nice

local to EC2 server — SCP transfer
scp -i /Users/howudooinng/Desktop/devops26.pem /Users/howudooinng/Desktop/AgenticAI/agent_aws.py ubuntu@ec2-3-238-197-158.compute-1.amazonaws.com:/home/ubuntu

Basic Reading of the Above command — scp -i key location(desktop in this case) followed by path of the file to be transferred followed by the ec2 server address ubuntu@address:destination of the server where the file will be placed

Pro Commands for Linux: Advanced Commands:
 
AWK — 
Scenario where we used AWK commands — we can use AWK if we don’t want to use shell script, You get a logfile and you want to extract some data from that log file, we can use AWK to do that.

awk ‘{print $1,$2,$3}’ app.log in awk we need formatted data, like , separated values (CSV), tab separated values tab separated.

to refer awk commands go to commands notes in this.

same output   awk '/INFO/ {print}' app.log 
                          sed -n '/INFO/p' app.log

Difference - Awk works on structured data, Sed works line by Line, structured or unstructured

SED — stream editor

GREP — global regular expression pattern

grep INFO app.log

Use case - 
grep -i -c info app.log (-i case insensitive)
ps aux — gives all processes
ps aux | grep ubuntu


Linux Volume Management :

What is Volume in Linux — there is an instance, then there is storage which is done on blocks/disk, in linux case it is called as Volume(storage of data)

AWS allows you to create volumes like external volume which we can attach to the aws ec2 instance.

mount — / (volume has been bind to a location)
attach —
mount and attach are different 
backup is called as snapshot
 Recommended device names for Linux: /dev/sda1 for root volume. /dev/sd[f-p] for data volumes.

You attached the volumes but not mounted yet

When you created the volume, you need to create them into physical volumes, so to use them.
I can combine the multiple volumes and create a volume group
and can create small slices for logical volumes(partitions you can manage according to usage)

lvm — logical volume manager
pvs — to see physical volumes/disks/blocks

pvcreate /dev/xvdf /dev/xvdg /dev/xvdh
 #Create Physical Volumes
sudo pvcreate /dev/nvme1n1
sudo pvcreate /dev/nvme2n1
sudo pvcreate /dev/nvme3n1

#Verify Physical Volumes
sudo pvdisplay

now create volume group - 
vgcreate tws_vg1 /dev/nvme1n1  /dev/nvme3n1
vgs - to see the volume group

now, lvcreate
lvcreate -L 10G -n tws_lv1 tws_vg1
lvs - to see the group

pvdisplay
lvdisplay

Mounting the volumes:

mkdir /mnt/tws_lv_mount — command to create a path for mounting

sudo mkfs.ext4 /dev/tws_vg1/tws_lv1 — command to format the volume group and logical volume

/dev/mapper/tws_vg1-tws_lv1  9.8G   24K  9.3G   1% /mnt/tws_lv_mount

sudo mount /dev/tws_vg1/tws_lv1 /mnt/tws_lv_mount — mount command 

cat /mnt/tws_lv_mount/hello.txt

umount /mnt/tws_lv_mount — data doesn’t get lost while unmounting 

if you have volume attached, we can only use that attached volume, after mounting that volume

unmounting doesn’t lead to data loss 

Commands to directly mount a disk to EC2 instance:  mkdir /mnt/tws_disk_mount — create a path first 

mkfs -t ext4 /dev/nvme4n1 — format
mount /dev/nvme4n1 /mnt/tws_disk_mount/

/dev/mapper/tws_vg1-tws_lv1  9.8G   32K  9.3G   1% /mnt/tws_lv_mount
/dev/nvme4n1                  12G   24K   12G   1% /mnt/tws_disk_mount


lvs, lvdisplay — these run inside lvm






 
















