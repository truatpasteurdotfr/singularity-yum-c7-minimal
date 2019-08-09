BootStrap: yum
OSVersion: 7
MirrorURL: http://mirror.centos.org/centos-%{OSVERSION}/%{OSVERSION}/os/x86_64/
Include: yum

# If you want the updates (available at the bootstrap date) to be installed
# inside the container during the bootstrap instead of the General Availability
# point release (7.x) then uncomment the following line
UpdateURL: http://mirror.centos.org/centos-%{OSVERSION}/%{OSVERSION}/updates/$basearch/


%runscript
    echo "This is what happens when you run the container..."


%post
mkdir -p /selinux /misc /net
mkdir -p /pasteur
mkdir -p /local-storage /mnt/beegfs /baycells/home /baycells/scratch /c6/shared /c6/eb /local/gensoft2 /c6/shared/rpm /Bis/Scratch2 /mnt/beegfs
mkdir -p /c7/shared /c7/scratch /c7/home

yum -y update && yum -y clean all

rm -rf /var/cache/yum/*
rm -f /tmp/ks-script*
rm -rf /var/log/*
rm -rf /tmp/*
rm -rf /etc/sysconfig/network-scripts/ifcfg-*

/bin/date +%Y%m%d_%H%M > /etc/BUILDTIME

:> /etc/machine-id

