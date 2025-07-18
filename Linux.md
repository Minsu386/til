# Day 1
----
# Day 2
----
# Day 3
----
- Add user to sudo
        `adduser choip`
        `usermod -a -G sudo choip`
    can also be accomplish by modifying the `/etc/sudoers` using the command `visudo`

- change password
        `passwd`

- Change hostname
        `sudo hostnamectl set-hostname mylinuxname`
    In cloud env, to preserve host name edit `/etc/cloud/cloud.cfg` and change "preserve_hostname" to true



