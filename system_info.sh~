#!/bin/bash


DATE=`/bin/date +date_%d-%m-%y_time_%H-%M-%S`
Time(){

###### STARTING PROGRAMMING AND TYPING THE USER INTERFACE ##########
#~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
echo "<br>"
echo " Computer Time : `date` <br>"
echo "<br>"
#~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~#
########### START SCRIPT MAIN PROGRAMMING AND COMMANDS WRITING #####################
}
GenInfo(){
## --------------------------------------<General Infromation>-----------------------------------##
echo "___________________________________________________________________________________<br>"
echo "**** General Information About This Computer ****"
echo "___________________________________________________________________________________<br>"
echo "This Computer Using `uname -m` architecture ;<br>"
echo "The Linux Kernel Used on this computer `uname -r`<br>"
echo -e "This Linux Distro. Used On this computer `head -n1 /etc/issue`<br>"
echo "The Host Name Of this computer is `hostname`<br>"
echo "The Name Of the user Of this computer is `whoami` <br>"
echo "The Number Of The Users That Using This Computer `users | wc -w` Users <br>"
echo "The System Uptime = `uptime | awk '{ gsub(/,/, ""); print $3 }'` (Hrs:Min)<br>"
echo "The Run level Of Current OS is `runlevel`<br>"
echo "The Number OF Running Process :`ps ax | wc -l`<br>"
echo "___________________________________________________________________________________<br>"
## --------------------------------------<General Infromation/end>-------------------------------##
}

CPUInfo(){ ## --------------------------------------<CPU Infromation>---------------------------------------##
echo "___________________________________________________________________________________<br>"
echo "****The CPU Infromation****<br>"
echo "___________________________________________________________________________________<br>"
echo "You Have `grep -c 'processor' /proc/cpuinfo` CPU<br>"
echo "Your CPU model name is `awk -F':' '/^model name/ { print $2 }' /proc/cpuinfo`<br>"
echo "Your CPU vendor`awk -F':' '/^vendor_id/ { print $2 }' /proc/cpuinfo`<br>"
echo "Your CPU Speed`awk -F':' '/^cpu MHz/ { print $2 }' /proc/cpuinfo`<br>"
echo "Your CPU Cache Size`awk -F':' '/^cache size/ { print $2 }' /proc/cpuinfo`<br>"
echo "___________________________________________________________________________________<br>"

## --------------------------------------<CPU Infomation/end>-----------------------------------##

}

MemInfo(){
## --------------------------------------<memory Information>------------------------------------##
echo "___________________________________________________________________________________<br>"
echo " ****The Memory Information****<br>"
echo "___________________________________________________________________________________<br>"
echo "`cat /proc/meminfo`<br>"
echo "___________________________________________________________________________________<br>"
echo "`free -m`<br>"
echo "___________________________________________________________________________________<br>"

## --------------------------------------<memory Infromation/end>--------------------------------##
}

FileSInfo(){

## --------------------------------------<File Systems Infromation>-------------------------------##
echo "___________________________________________________________________________________<br>"
echo "*****File Systems Infromation******<br>"
echo "___________________________________________________________________________________<br>"
echo "`df -h`<br>"
echo "___________________________________________________________________________________<br>"

## --------------------------------------<File Systems Infromation/end>------------------------------##
}

PCIInfo(){
## --------------------------------------<Pci Devices Information script>-------------------------##
echo "___________________________________________________________________________________<br>"
echo "******PCI devices On MOtherboard information {detailed}******<br>"
echo "___________________________________________________________________________________<br>"
echo "`lspci -tv`<br>"
echo "___________________________________________________________________________________<br>"
## --------------------------------------<Pci Devices Information script/end>----------------------##

}

NetInfo(){
## --------------------------------------<Netwrok Infromation>-------------------------------------##
echo "___________________________________________________________________________________<br>"
echo "********Network Information********<br>"
echo "___________________________________________________________________________________<br>"
echo "`/sbin/ifconfig`<br>"
echo "___________________________________________________________________________________<br>"
## --------------------------------------<network Infromation/end>--------------------------------##

}

## --------------------------------------<script ending>-----------------------------------------##

Run(){
echo "<html><body>"
Time
GenInfo
CPUInfo
MemInfo
FileSInfo
PCIInfo
NetInfo
echo "</body></html>"
}
log=Sysinfo_$DATE
Run | tee $log.txt
mv $log.txt $log.html
#~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~#