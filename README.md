# swapoff
```
$ sudo swapon --show
NAME      TYPE SIZE USED PRIO
/swapfile file 1.1G   0B   -2

$ sudo vi /etc/fstab
# comment out like below:
#/swapfile                                 none            swap    sw              0       0


$ sudo swapoff -a



$ sudo swapon --show
$ free -h
              total        used        free      shared  buff/cache   available
Mem:          7.8Gi       876Mi       6.3Gi        10Mi       593Mi       6.7Gi
Swap:            0B          0B          0B

$ sudo systemctl --type swap --all
  UNIT          LOAD   ACTIVE   SUB  DESCRIPTION
  swapfile.swap loaded inactive dead /swapfile  

LOAD   = Reflects whether the unit definition was properly loaded.
ACTIVE = The high-level unit activation state, i.e. generalization of SUB.
SUB    = The low-level unit activation state, values depend on unit type.

1 loaded units listed.
To show all installed unit files use 'systemctl list-unit-files'.

$ sudo systemctl mask "swapfile.swap"
Created symlink /etc/systemd/system/swapfile.swap → /dev/null.

$ sudo systemctl --type swap --all
  UNIT LOAD ACTIVE SUB DESCRIPTION
0 loaded units listed.
To show all installed unit files use 'systemctl list-unit-files'.


```

