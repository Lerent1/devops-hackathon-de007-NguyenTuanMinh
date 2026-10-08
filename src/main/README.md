C:\Windows\System32>ssh root@221.121.4.70
The authenticity of host '221.121.4.70 (221.121.4.70)' can't be established.
ED25519 key fingerprint is SHA256:ST75FFldzkZqGzutzJn51PQUe1sCyjeDR4maCJSIw0g.
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '221.121.4.70' (ED25519) to the list of known hosts.
root@221.121.4.70's password:
Permission denied, please try again.
root@221.121.4.70's password:
Permission denied, please try again.
root@221.121.4.70's password:
root@221.121.4.70: Permission denied (publickey,password).

C:\Windows\System32>ssh root@221.121.4.70
root@221.121.4.70's password:
Permission denied, please try again.
root@221.121.4.70's password:
Welcome to Ubuntu 24.04.2 LTS (GNU/Linux 6.8.0-63-generic x86_64)

* Documentation:  https://help.ubuntu.com
* Management:     https://landscape.canonical.com
* Support:        https://ubuntu.com/pro

This system has been minimized by removing packages and content that are
not required on a system that users do not log into.

To restore this content, you can run the 'unminimize' command.
Last login: Wed Sep 30 08:48:36 2026 from 103.113.82.24
root@Minhnt:~# adduser nguyentuanminh-cntt4
info: Adding user `nguyentuanminh-cntt4' ...
info: Selecting UID/GID from range 1000 to 59999 ...
info: Adding new group `nguyentuanminh-cntt4' (1000) ...
info: Adding new user `nguyentuanminh-cntt4' (1000) with group `nguyentuanminh-cntt4 (1000)' ...
info: Creating home directory `/home/nguyentuanminh-cntt4' ...
info: Copying files from `/etc/skel' ...
New password:
Retype new password:
passwd: password updated successfully
Changing the user information for nguyentuanminh-cntt4
Enter the new value, or press ENTER for the default
Full Name []: Nguyen Tuan Minh
Room Number []: cntt4
Work Phone []:
Home Phone []:
Other []:
Is the information correct? [Y/n] Y
info: Adding new user `nguyentuanminh-cntt4' to supplemental / extra groups `users' ...
info: Adding user `nguyentuanminh-cntt4' to group `users' ...
root@Minhnt:~# usermod -aG sudo nguyentuanminh-cntt4
root@Minhnt:~# id nguyentuanminh-cntt4
uid=1000(nguyentuanminh-cntt4) gid=1000(nguyentuanminh-cntt4) groups=1000(nguyentuanminh-cntt4),27(sudo),100(users)
root@Minhnt:~# whoami nguyentuanminh-cntt4
whoami: extra operand ‘nguyentuanminh-cntt4’
Try 'whoami --help' for more information.

root@Minhnt:~# ssh nguyentuanminh-cntt4@221.121.4.70
The authenticity of host '221.121.4.70 (221.121.4.70)' can't be established.
ED25519 key fingerprint is SHA256:ST75FFldzkZqGzutzJn51PQUe1sCyjeDR4maCJSIw0g.
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '221.121.4.70' (ED25519) to the list of known hosts.
nguyentuanminh-cntt4@221.121.4.70's password:
Welcome to Ubuntu 24.04.2 LTS (GNU/Linux 6.8.0-63-generic x86_64)

* Documentation:  https://help.ubuntu.com
* Management:     https://landscape.canonical.com
* Support:        https://ubuntu.com/pro

This system has been minimized by removing packages and content that are
not required on a system that users do not log into.

To restore this content, you can run the 'unminimize' command.
New release '26.04.1 LTS' available.
Run 'do-release-upgrade' to upgrade to it.


The programs included with the Ubuntu system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
applicable law.

To run a command as administrator (user "root"), use "sudo <command>".
See "man sudo_root" for details.

nguyentuanminh-cntt4@Minhnt:~$ sudo apt update && sudo apt -y upgrade

nguyentuanminh-cntt4@Minhnt:~$ sudo ufw default deny incoming
Default incoming policy changed to 'deny'
(be sure to update your rules accordingly)
nguyentuanminh-cntt4@Minhnt:~$ sudo ufw default allow outgoing
Default outgoing policy changed to 'allow'
(be sure to update your rules accordingly)
nguyentuanminh-cntt4@Minhnt:~$ sudo ufw allow 22/tcp
Rules updated
Rules updated (v6)
nguyentuanminh-cntt4@Minhnt:~$ sudo ufw allow 443/tcp
Rules updated
Rules updated (v6)
nguyentuanminh-cntt4@Minhnt:~$ sudo ufw allow 8088/tcp
Rules updated
Rules updated (v6)
nguyentuanminh-cntt4@Minhnt:~$ sudo ufw enable
Command may disrupt existing ssh connections. Proceed with operation (y|n)? y
Firewall is active and enabled on system startup
nguyentuanminh-cntt4@Minhnt:~$ sudo ufw status numbered
Status: active

     To                         Action      From
     --                         ------      ----
[ 1] 22/tcp                     ALLOW IN    Anywhere
[ 2] 443/tcp                    ALLOW IN    Anywhere
[ 3] 8088/tcp                   ALLOW IN    Anywhere
[ 4] 22/tcp (v6)                ALLOW IN    Anywhere (v6)
[ 5] 443/tcp (v6)               ALLOW IN    Anywhere (v6)
[ 6] 8088/tcp (v6)              ALLOW IN    Anywhere (v6)

nguyentuanminh-cntt4@Minhnt:~$ sudo apt install nginx
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
The following packages were automatically installed and are no longer required:
libtirpc-common libtirpc3t64 linux-headers-6.8.0-62 linux-headers-6.8.0-62-generic linux-image-6.8.0-62-generic
linux-modules-6.8.0-62-generic linux-modules-extra-6.8.0-62-generic linux-tools-6.8.0-62
linux-tools-6.8.0-62-generic
Use 'sudo apt autoremove' to remove them.
The following additional packages will be installed:
nginx-common
Suggested packages:
fcgiwrap nginx-doc ssl-cert
The following NEW packages will be installed:
nginx nginx-common
0 upgraded, 2 newly installed, 0 to remove and 0 not upgraded.
Need to get 570 kB of archives.
After this operation, 1602 kB of additional disk space will be used.
Do you want to continue? [Y/n] Y
Get:1 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 nginx-common all 1.24.0-2ubuntu7.18 [45.1 kB]
Get:2 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 nginx amd64 1.24.0-2ubuntu7.18 [525 kB]
Fetched 570 kB in 2s (262 kB/s)
debconf: delaying package configuration, since apt-utils is not installed
Selecting previously unselected package nginx-common.
(Reading database ... 151130 files and directories currently installed.)
Preparing to unpack .../nginx-common_1.24.0-2ubuntu7.18_all.deb ...
Unpacking nginx-common (1.24.0-2ubuntu7.18) ...
Selecting previously unselected package nginx.
Preparing to unpack .../nginx_1.24.0-2ubuntu7.18_amd64.deb ...
Unpacking nginx (1.24.0-2ubuntu7.18) ...
Setting up nginx-common (1.24.0-2ubuntu7.18) ...
debconf: unable to initialize frontend: Dialog
debconf: (No usable dialog-like program is installed, so the dialog based frontend cannot be used. at /usr/share/perl5/Debconf/FrontEnd/Dialog.pm line 79.)
debconf: falling back to frontend: Readline
Created symlink /etc/systemd/system/multi-user.target.wants/nginx.service → /usr/lib/systemd/system/nginx.service.
Setting up nginx (1.24.0-2ubuntu7.18) ...
* Upgrading binary nginx                                                                                        [ OK ]
  Processing triggers for ufw (0.36.2-6) ...
  Scanning processes...
  Scanning candidates...
  Scanning linux images...

Pending kernel upgrade!
Running kernel version:
6.8.0-63-generic
Diagnostics:
The currently running kernel version is not the expected kernel version 6.8.0-146-generic.

Restarting the system to load the new kernel will not be handled automatically, so you should consider rebooting.

Restarting services...

Service restarts being deferred:
/etc/needrestart/restart.d/dbus.service
systemctl restart getty@tty1.service
systemctl restart systemd-logind.service
systemctl restart unattended-upgrades.service

No containers need to be restarted.

User sessions running outdated binaries:
nguyentuanminh-cntt4 @ session #3: sshd[8339,8375]
nguyentuanminh-cntt4 @ user manager service: systemd[8345]
root @ session #1: bash[8113], sshd[8069]
root @ user manager service: systemd[8077]

No VM guests are running outdated hypervisor (qemu) binaries on this host.
nguyentuanminh-cntt4@Minhnt:~$ sudo mkdir -p /var/www/devops-hackathon-de007-nguyentuanminh/
nguyentuanminh-cntt4@Minhnt:~$ sudo chown -R nguyentuanminh-cntt4:nguyentuanminh-cntt4 /var/www/devops-hackathon-de007-nguyentuanminh
nguyentuanminh-cntt4@Minhnt:~$ sudo chmod -P 755 /var/www/devops-hackathon-de007-nguyentuanminh
chmod: invalid option -- 'P'
Try 'chmod --help' for more information.
nguyentuanminh-cntt4@Minhnt:~$ sudo chmod -R 755 /var/www/devops-hackathon-de007-nguyentuanminh
nguyentuanminh-cntt4@Minhnt:~$ nano /var/www/devops-hackathon-de007-nguyentuanminh/index.html
nguyentuanminh-cntt4@Minhnt:~$ nano /var/www/devops-hackathon-de007-nguyentuanminh/404.html
nguyentuanminh-cntt4@Minhnt:~$ sudo nano /etc/nginx/sites-available/devops-hackathon-de007-nguyentuanminh
[sudo] password for nguyentuanminh-cntt4:
nguyentuanminh-cntt4@Minhnt:~$ sudo ln -s /etc/nginx/sites-available/devops-hackathon-de007-nguyentuanminh /etc/nginx/sites-enable/
ln: failed to create symbolic link '/etc/nginx/sites-enable/': No such file or directory
nguyentuanminh-cntt4@Minhnt:~$ sudo ln -s /etc/nginx/sites-available/devops-hackathon-de007-nguyentuanminh /etc/nginx/sites-enable
nguyentuanminh-cntt4@Minhnt:~$ sudo nginx -t
nginx: the configuration file /etc/nginx/nginx.conf syntax is ok
nginx: configuration file /etc/nginx/nginx.conf test is successful
nguyentuanminh-cntt4@Minhnt:~$ sudo systemctl reload nginx