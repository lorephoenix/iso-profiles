## iso-profiles


### profile.conf

~~~
##########################################
###### use this file in the profile ######
##########################################

## use multilib packages; x86_64 only
multilib="false"

## use extra packages as defined in pkglist to activate a full profile
extra="true"

################ install ################

## default displaymanager: none
## supported; lightdm, sddm, gdm, lxdm, mdm
displaymanager="none"

## Set to false to disable autologin in the livecd
# autologin="true"

## use geoip
# geoip="true"

## default system shell is bash
## '/etc/defaults/useradd': " "
## userShell              : "/bin/zsh"
## empty value will not be used
user_shell=""

################# live-session #################

## unset defaults to given value
hostname="manjaro-lite"

## the login shell
## defaults to bash
login_shell=/bin/bash

## unset defaults to given values
## names must match systemd service names
## services in enable_systemd array don't need to be listed here
enable_systemd_live=('manjaro-live' 'pacman-init' 'mirrors-live' 'systemd-networkd' 'systemd-resolved' 'systemd-timesyncd', 'sshd')
disable_systemd_live=('tlp' 'tlp-sleep')

custom_boot_args=()
~~~

### Packages-Root

* Contains root image packages
* ideally no xorg

### Packages-Live

* Contains packages you only want in live session but not installed on the target system with installer
* default files are in shared folder and can be symlinked or defined in a real file
