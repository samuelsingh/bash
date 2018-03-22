#!/bin/bash


DATE=`/bin/date +date_%d-%m-%y_time_%H-%M-%S`
Time(){

#~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
#echo "<br>"
echo " Map Of Medicine Server Details "
echo " Computer Time : `date` "
#echo "<br>"
#~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~#

}
GenInfo(){
## --------------------------------------<General Information>-----------------------------------##
echo "___________________________________________________________________________________"
echo "**** General Information About This instance ****"
echo "___________________________________________________________________________________"
echo  "1 - Hostname : `hostname`"
echo 
echo -e "2 - Current OS :\n`lsb_release -a`"
echo 
echo "3 - This Computer Using `uname -m` architecture ;"
#echo -e "This Linux Distro. Used On this computer `head -n1 /etc/issue`"
#echo "The Host Name Of this computer is `hostname`"
#echo "The Name Of the user Of this computer is `whoami` "
#echo "The Number Of The Users That Using This Computer `users | wc -w` Users "
echo 
echo -e "4 - The System Uptime = `uptime | awk '{ gsub(/,/, ""); print $3 }'` (Hrs:Min)"
echo 
echo "5 - The Run level Of Current OS is `runlevel`"
#echo "The Number OF Running Process :`ps ax | wc -l`"

echo 
echo -e "6 -PSTREE:\n`pstree`"
echo 
echo -e "7 -System v interprocess:\n`ipcs -a`"
echo 
echo -e "8 -System Load Avg:\n`w`"
echo 
echo -e "9 -Environment variables:\n`env`"
echo 
echo -e "10 -All users:\n`cat /etc/passwd`"
echo 
echo -e "11 -All groups:\n`cat /etc/group`"
echo 
echo -e "11 -All files under /var/log:\n`la -ltr /var/log`"
echo "___________________________________________________________________________________"
## --------------------------------------<General Infromation/end>-------------------------------##
}

KernelInfo(){ ## --------------------------------------<Kernel Information---------------------------------------##
echo "___________________________________________________________________________________"
echo "****Kernel Information****"
echo "___________________________________________________________________________________"
echo  "1 - Kernel version: `uname -r`"
echo 
echo -e "2 - Sysctl -A:\n`sysctl -A`"
echo "___________________________________________________________________________________"

## --------------------------------------<CPU Infomation/end>-----------------------------------##

}


MemInfo(){
## --------------------------------------<memory Information>------------------------------------##
echo "___________________________________________________________________________________"
echo " ****Memory Information****"
echo 
echo "___________________________________________________________________________________"
echo 
echo -e "1 - MemInfo:\n`cat /proc/meminfo`"
echo "___________________________________________________________________________________"

echo -e "2 - Free:\n `free -m`"
echo "___________________________________________________________________________________"

## --------------------------------------<memory Information/end>--------------------------------##
}

CPUInfo(){ ## --------------------------------------<CPU Information>---------------------------------------##
echo "___________________________________________________________________________________"
echo "****CPU Information****"
echo "___________________________________________________________________________________"
echo 
echo "You Have `grep -c 'processor' /proc/cpuinfo` CPU"
echo 
echo "Your CPU model name is `awk -F':' '/^model name/ { print $2 }' /proc/cpuinfo`"
echo 
echo "Your CPU vendor`awk -F':' '/^vendor_id/ { print $2 }' /proc/cpuinfo`"
echo 
echo "Your CPU Speed`awk -F':' '/^cpu MHz/ { print $2 }' /proc/cpuinfo`"
echo 
echo "Your CPU Cache Size`awk -F':' '/^cache size/ { print $2 }' /proc/cpuinfo`"
echo "___________________________________________________________________________________"

## --------------------------------------<CPU Information/end>-----------------------------------##

}

BootInfo(){ ## --------------------------------------<Boot Information>---------------------------------------##
echo "___________________________________________________________________________________"
echo "****Boot Information****"
echo 
echo "___________________________________________________________________________________"
echo 
echo "`cat /var/log/boot.log`"
echo "___________________________________________________________________________________"

}



DiskInfo(){ ## --------------------------------------<Disk Information>---------------------------------------##
echo "___________________________________________________________________________________"
echo "****Disk Infromation****"
echo "___________________________________________________________________________________"
echo -e "1 - Disks Information:\n`sudo fdisk -l`"
echo "___________________________________________________________________________________"
echo -e "2 - Partition table details:\n`sudo parted --list`"
echo "___________________________________________________________________________________"
echo -e "3 - List of block devices:\n`lsblk`"
echo "___________________________________________________________________________________"
echo -e "4 - List of block device attributes:\n`blkid`"
echo "___________________________________________________________________________________"
echo -e "5 - File system disk space :\n`df -h`"
echo "___________________________________________________________________________________"
echo -e "6 - Inode Information:\n`df -i`"
echo "___________________________________________________________________________________"
echo -e "7 - DMI Setup Information:\n`dmidecode`"
}





PCIInfo(){
## --------------------------------------<Pci Devices Information script>-------------------------##
echo "___________________________________________________________________________________"
echo "******PCI devices On MOtherboard information {detailed}******"
echo "___________________________________________________________________________________"
echo "`lspci -tv`"
echo "___________________________________________________________________________________"
## --------------------------------------<Pci Devices Information script/end>----------------------##

}

NetInfo(){
## --------------------------------------<Network Information>-------------------------------------##
echo "___________________________________________________________________________________"
echo "********Network Information********"
echo "___________________________________________________________________________________"

echo "___________________________________________________________________________________"
cho -e "1 - Network Connections:\n`netstat -ntpl`"
echo "___________________________________________________________________________________"
echo -e "2 - Routing Table details:\n`netstat -nr`"
echo "___________________________________________________________________________________"
echo -e "3 - Interface Stats:\n`ifconfig`"
echo "___________________________________________________________________________________"
echo -e "4 - Multicast groups:\n`netstat -g`"
echo "___________________________________________________________________________________"
echo -e "5 - Iptables/Firewall status :\n`ufw status`"
echo "___________________________________________________________________________________"
echo -e "6 - NTP configuration:\n`cat /etc/ntp.conf`"
echo "___________________________________________________________________________________"
echo -e "7 - DNS configuration:\n`cat /etc/resolv.conf`"
## --------------------------------------<network Information/end>--------------------------------##

}



ApacheInfo(){
## --------------------------------------<Apache  Information>-------------------------------------##
echo "___________________________________________________________________________________"
echo "****Apache Infromation****"
SERVICE='apache2'
 
if ps ax | grep -v grep | grep $SERVICE > /dev/null
then
    echo -e "$SERVICE service running\n"
    echo -e "Installed Package\n:`sudo dpkg -l | grep -i apache`"
else
    #echo "$SERVICE is not running"
    echo "This is not a web server"
    #echo "$SERVICE is not running!" | mail -s "$SERVICE down" root
fi

}

## --------------------------------------<script ending>-----------------------------------------##

Run(){
#echo "<html><body>"
Time
GenInfo
KernelInfo
MemInfo
CPUInfo
BootInfo
DiskInfo
ApacheInfo
#FileSInfo
#PCIInfo
NetInfo
#echo "</body></html>"
}
log=`hostname | cut -d"-" -f1`_$DATE
Run | tee $log.sysinfo
#mv $log.txt $log.html
#~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~#