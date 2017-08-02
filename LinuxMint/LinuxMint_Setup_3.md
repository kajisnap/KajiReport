## Virtual Box

* Network 관련하여 읽을만한 페이지 - https://printf.kr/archives/285



sudo `VBoxManage internalcommands createrawvmdk -filename ``/media/iamnotroot/Data/VirtualBox/usb``.vmdk -rawdisk ``/dev/sdb`

sudo VBoxManage internalcommands createrawvmdk -filename /home/hwi/VMs/usb.vmdk -rawdisk /dev/sdb1



hwi@hwi ~/VMs $ ls -ltr
total 12
drwxr-xr-x 3 hwi  hwi  4096  8월  3 21:13 win10
drwxr-xr-x 3 hwi  hwi  4096  8월  3 21:23 win10_new
-rw------- 1 root root  537  8월  3 21:34 usb.vmdk
hwi@hwi ~/VMs $ chmod 777 usb.vmdk
chmod: changing permissions of 'usb.vmdk': Operation not permitted
hwi@hwi ~/VMs $ sudo 777 usb.vmdk
sudo: 777: command not found
hwi@hwi ~/VMs $ sudo chmod 777 usb.vmdk
hwi@hwi ~/VMs $ ls -ltr
total 12
drwxr-xr-x 3 hwi  hwi  4096  8월  3 21:13 win10
drwxr-xr-x 3 hwi  hwi  4096  8월  3 21:23 win10_new
-rwxrwxrwx 1 root root  537  8월  3 21:34 usb.vmdk

USB 부팅을 위하여

sudo VBoxManage internalcommands createrawvmdk -filename /home/hwi/VMs/usb.vmdk -rawdisk /dev/sdb1



hwi@hwi ~/VMs $ ls -ltr
total 12
drwxr-xr-x 3 hwi  hwi  4096  8월  3 21:13 win10
drwxr-xr-x 3 hwi  hwi  4096  8월  3 21:23 win10_new
-rw------- 1 root root  537  8월  3 21:34 usb.vmdk
hwi@hwi ~/VMs $ chmod 777 usb.vmdk
chmod: changing permissions of 'usb.vmdk': Operation not permitted
hwi@hwi ~/VMs $ sudo 777 usb.vmdk
sudo: 777: command not found
hwi@hwi ~/VMs $ sudo chmod 777 usb.vmdk
hwi@hwi ~/VMs $ ls -ltr
total 12
drwxr-xr-x 3 hwi  hwi  4096  8월  3 21:13 win10
drwxr-xr-x 3 hwi  hwi  4096  8월  3 21:23 win10_new
-rwxrwxrwx 1 root root  537  8월  3 21:34 usb.vmdk


hwi@hwi ~/VMs $ sudo chown hwi:hwi usb.vmdk
hwi@hwi ~/VMs $ ls -ltr
total 12
drwxr-xr-x 3 hwi hwi 4096  8월  3 21:13 win10
-rwxrwxrwx 1 hwi hwi  537  8월  3 21:34 usb.vmdk
drwxr-xr-x 3 hwi hwi 4096  8월  3 21:39 win10_new

권한문제 발생..verr_access_denied

![verr_access_denied](./img/verr_access_denied)



hwi@hwi ~/VMs $ sudo chmod 666 /dev/sdb1
hwi@hwi ~/VMs $ df
Filesystem     1K-blocks     Used Available Use% Mounted on
udev             3898108        0   3898108   0% /dev
tmpfs             783932     9780    774152   2% /run
/dev/sda1      238079624 38274368 187688420  17% /
tmpfs            3919644    26288   3893356   1% /dev/shm
tmpfs               5120        4      5116   1% /run/lock
tmpfs            3919644        0   3919644   0% /sys/fs/cgroup
cgmfs                100        0       100   0% /run/cgmanager/fs
tmpfs             783932       44    783888   1% /run/user/1000
/dev/sdb1        8028492  3581256   4447236  45% /media/hwi/52C86602C865E4A7
hwi@hwi ~/VMs $ 

