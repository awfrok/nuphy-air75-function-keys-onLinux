# In Arch Linux, Nuphy Air 75, function keys settings
You can use Nuphy Air 75's function keys as F1-F12 in windows-mode of it.


> https://www.reddit.com/r/MechanicalKeyboards/comments/tgjvp2/nuphy_air75_on_linux_issues_with_fn/  
> https://i.imgur.com/qrHQLII.png  
> https://wiki.archlinux.org/title/Apple_Keyboard  

![](https://github.com/awfrok/nuhpy-air75-function-keys/blob/main/NuphyAir75_hid_apple_fnmode=0.png?raw=true)

## you can test it temporarily with root previlage.
```shell
echo 0 >> /sys/module/hid_apple/parameters/fnmode
```

## if this test works, make it permanent.

- make the file /etc/modprobe.d/hid_apple.conf.
- add the following
```shell
options hid_apple fnmode=0
```
- rebuild initramfs image with root previlage. 
```shell
mkinitcpio -P
```
- if you run Ubuntu-based one, run the following command to rebuild initramfs.
```shell
update-initramfs -u.
```
