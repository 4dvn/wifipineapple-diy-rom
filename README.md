# GL-INET-6416A wifipineapple NANO V1.1.3

#添加 netgear-WNDR4300 tetra支持 1.1.2

##Update to 1.1.3

##Source 和 file 是针对tetra的 如果不需要建议下载releases。

##openwrt-ar71xx-generic-wifipineapplenano-* 是针对TP-LINK MR10U MR11U MR12U MR13U 703N MR3020 MR3040  改过16M/64M，联想PWR-G60（这个就是大淘宝网上买的非原厂wifipineapple，有SD卡插槽。）<br>也可以使用。都是单网口的。不用启用双网卡支持

##WNDR4300 完全可用

##files文件夹默认是支持gl-inet的。

##添加源代码，默认720N如有需要自己make menuconfig

###其次，720N专用需要各位自己解决lan端口问题。只要在配置文件里面稍微修改就可以使用双网口了。不是什么大问题，我就懒得改了。

##扩展说明。
<pre>
mkdir -p /mnt/sda2<br>
mount /dev/sda2 /mnt/sda2<br>
mkdir -p /tmp/cproot<br>
mount --bind / /tmp/cproot<br>
tar -C /tmp/cproot -cvf - . | tar -C /mnt/sda2 -xf -<br>
umount /tmp/cproot<br>
umount /mnt/sda2<br>
</pre>
vi /etc/config/fstab //添加如下<br>
<pre>
config 'mount'<br>
       option target '/'<br>
       option device '/dev/sda2'<br>
       option fstype 'ext4'<br>
       option options 'rw,sync'<br>
       option enabled '1'<br>
       option enabled_fsck '0'<br>

config 'swap'<br>
       option device '/dev/sda1'<br>
       option enabled '1'<br>
</pre>
