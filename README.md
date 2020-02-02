# GL-INET-6416A wifipineapple NANO V1.1.3

#Add netgear-WNDR4300 tetra support 1.1.2

 ## Update to 1.1.3

 ## Source and file are for tetra. If not needed, download the releases.

 ## openwrt-ar71xx-generic-wifipineapplenano- * is for TP-LINK MR10U MR11U MR12U MR13U 703N MR3020 MR3040 changed 16M / 64M, Lenovo PWR-G60 (this is a non-original wifipineapple bought on Taobao online, with SD card inserted  Slot.) <br> can also be used.  All are single network ports.  No need to enable dual network card support

 ## WNDR4300 Fully Available

 ## files folders support gl-inet by default.

 ## Add source code, default 720N make menuconfig yourself if necessary

 ### Secondly, 720N dedicated needs you to solve the lan port problem by yourself.  As long as the configuration file is slightly modified, dual network ports can be used.  It's not a big problem, and I'm too lazy to change it.

 ## Extended description.
 <pre>
 mkdir -p / mnt / sda2 <br>
 mount / dev / sda2 / mnt / sda2 <br>
 mkdir -p / tmp / cproot <br>
 mount --bind / / tmp / cproot <br>
 tar -C / tmp / cproot -cvf-. | tar -C / mnt / sda2 -xf-<br>
 umount / tmp / cproot <br>
 umount / mnt / sda2 <br>
 </ pre>
 vi / etc / config / fstab // Add the following <br>
 <pre>
 config 'mount' <br>
        option target '/' <br>
        option device '/ dev / sda2' <br>
        option fstype 'ext4' <br>
        option options 'rw, sync' <br>
        option enabled '1' <br>
        option enabled_fsck '0' <br>

 config 'swap' <br>
        option device '/ dev / sda1' <br>
        option enabled '1' <br>
 </ pre>
