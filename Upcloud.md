Palvelin luotu ip ssh root@94.237.33.39

julkinen avain generoitu, löytyy kansioista `ls -a`

Root tunnuksen poistaminen - `adduser "nimi"` luo oma käyttäjä,  kopioi ssh avaimet omalle käyttäjälle, anna rootilla oikeudet käyttäjälle kansioon-  lukitse rootin salasanakirjautuminen- poista rootin ssh avaimet `sudo rm /root/.ssh -r
`

santeri@santeri-virtualbox:~$ ssh root@94.237.33.39
Linux debian-1cpu-1gb-fi-hel1 6.1.0-25-amd64 #1 SMP PREEMPT_DYNAMIC Debian 6.1.106-3 (2024-08-26) x86_64

The programs included with the Debian GNU/Linux system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Debian GNU/Linux comes with ABSOLUTELY NO WARRANTY, to the extent
permitted by applicable law.
Last login: Tue Feb  4 17:39:23 2025 from 84.251.61.224
root@debian-1cpu-1gb-fi-hel1:~# pwd
/root
root@debian-1cpu-1gb-fi-hel1:~# ĺs -a
-bash: ĺs: command not found
root@debian-1cpu-1gb-fi-hel1:~# ls -a
.  ..  .bash_history  .bashrc  .profile  .ssh
root@debian-1cpu-1gb-fi-hel1:~# cd .ssh
root@debian-1cpu-1gb-fi-hel1:~/.ssh# ls
authorized_keys
root@debian-1cpu-1gb-fi-hel1:~/.ssh# micro authorized_keys 
-bash: micro: command not found
root@debian-1cpu-1gb-fi-hel1:~/.ssh# cat authorized_keys 
ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABgQC0Unony/IZl2TvYIl2qFvcXBtWeGFrU/v+4ECRZARSP33AcYejwBCUkth8hMFYa7I5oEmIOe2pcq0puoatOuYMDR1hs5VOjBEjGQ9pN52+01nLOVDn/GvnDByTLfcy4+vw36W3nxVdt7kTO7AYU2xDKeOQEnDPE5zGGu+SgeDq6AJcw8qKm867cFydg13MMkhb02tAiR0tgIc7N5hzJD1M4Rq1peuAyU7wnbJ6e1wpK3ZiyB/Y3XlMq2T71OLX8GKCrXpMzDxBr3BzA5ORA4bFaN1FYH7iIz/0oHSBi37zS7MPgiMINDvXUyr9CXBNAVL64ssCnUzubrwh/uZjbyB6T94I7d37r60dQvhtsQcPyw/JlLn79CkophcVH6H3yzFpf9VIumL+fBD28ju7ND1ZTj/JGaSGZEhPQYO3WgPJD4Rv5AYAkm9MfF8fWJ0gTtEvkae6baicbD473t9x9nCGOPuF1zDtQyNgcJ7w7EWsDKp1ykG7b8HaRE16RSUenck= santeri@santeri-virtualbox
root@debian-1cpu-1gb-fi-hel1:~/.ssh# cd
root@debian-1cpu-1gb-fi-hel1:~# ls
root@debian-1cpu-1gb-fi-hel1:~# pwd
/root
root@debian-1cpu-1gb-fi-hel1:~# cd /
root@debian-1cpu-1gb-fi-hel1:/# ls
bin   dev  home        initrd.img.old  lib64	   media  opt	root  sbin  sys  usr  vmlinuz
boot  etc  initrd.img  lib	       lost+found  mnt	  proc	run   srv   tmp  var  vmlinuz.old
root@debian-1cpu-1gb-fi-hel1:/# cd
root@debian-1cpu-1gb-fi-hel1:~# ls
root@debian-1cpu-1gb-fi-hel1:~# pwd
/root
root@debian-1cpu-1gb-fi-hel1:~# ls /home/santeri
root@debian-1cpu-1gb-fi-hel1:~# ls -a /home/santeri
.  ..  .bash_logout  .bashrc  .profile
root@debian-1cpu-1gb-fi-hel1:~# cp -n -r /root/.ssh /home/santeri/
root@debian-1cpu-1gb-fi-hel1:~# ls -a /home/santeri/
.  ..  .bash_logout  .bashrc  .profile	.ssh
root@debian-1cpu-1gb-fi-hel1:~# ls -la
total 24
drwx------  3 root root 4096 Feb  4 17:50 .
drwxr-xr-x 18 root root 4096 Feb  4 17:38 ..
-rw-------  1 root root   59 Feb  4 17:50 .bash_history
-rw-r--r--  1 root root  571 Apr 10  2021 .bashrc
-rw-r--r--  1 root root  161 Jul  9  2019 .profile
drwx------  2 root root 4096 Feb  4 17:38 .ssh
root@debian-1cpu-1gb-fi-hel1:~# pwd
/root
root@debian-1cpu-1gb-fi-hel1:~# cd /home/santeri/
root@debian-1cpu-1gb-fi-hel1:/home/santeri# ls
root@debian-1cpu-1gb-fi-hel1:/home/santeri# ls -la
total 24
drwx------ 3 santeri santeri 4096 Feb  4 17:55 .
drwxr-xr-x 3 root    root    4096 Feb  4 17:48 ..
-rw-r--r-- 1 santeri santeri  220 Feb  4 17:48 .bash_logout
-rw-r--r-- 1 santeri santeri 3526 Feb  4 17:48 .bashrc
-rw-r--r-- 1 santeri santeri  807 Feb  4 17:48 .profile
drwx------ 2 root    root    4096 Feb  4 17:55 .ssh
root@debian-1cpu-1gb-fi-hel1:/home/santeri# chown santeri.santeri .ssh -R
chown: warning: '.' should be ':': 'santeri.santeri'
root@debian-1cpu-1gb-fi-hel1:/home/santeri# ls -la
total 24
drwx------ 3 santeri santeri 4096 Feb  4 17:55 .
drwxr-xr-x 3 root    root    4096 Feb  4 17:48 ..
-rw-r--r-- 1 santeri santeri  220 Feb  4 17:48 .bash_logout
-rw-r--r-- 1 santeri santeri 3526 Feb  4 17:48 .bashrc
-rw-r--r-- 1 santeri santeri  807 Feb  4 17:48 .profile
drwx------ 2 santeri santeri 4096 Feb  4 17:55 .ssh
root@debian-1cpu-1gb-fi-hel1:/home/santeri# pwd
/home/santeri
root@debian-1cpu-1gb-fi-hel1:/home/santeri# cd .ssh
root@debian-1cpu-1gb-fi-hel1:/home/santeri/.ssh# ls
authorized_keys
root@debian-1cpu-1gb-fi-hel1:/home/santeri/.ssh# ls -l
total 4
-rw------- 1 santeri santeri 580 Feb  4 17:55 authorized_keys
root@debian-1cpu-1gb-fi-hel1:/home/santeri/.ssh# 
root@debian-1cpu-1gb-fi-hel1:/home/santeri/.ssh# exit
logout
Connection to 94.237.33.39 closed.
santeri@santeri-virtualbox:~$ ssh santeri@94.237.33.39
Linux debian-1cpu-1gb-fi-hel1 6.1.0-25-amd64 #1 SMP PREEMPT_DYNAMIC Debian 6.1.106-3 (2024-08-26) x86_64

The programs included with the Debian GNU/Linux system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Debian GNU/Linux comes with ABSOLUTELY NO WARRANTY, to the extent
permitted by applicable law.
santeri@debian-1cpu-1gb-fi-hel1:~$ sudo echo moikka
[sudo] password for santeri: 
moikka
santeri@debian-1cpu-1gb-fi-hel1:~$ sudo usermod --lock root
santeri@debian-1cpu-1gb-fi-hel1:~$ exit
logout
Connection to 94.237.33.39 closed.
santeri@santeri-virtualbox:~$ ssh root@94.237.33.39
Linux debian-1cpu-1gb-fi-hel1 6.1.0-25-amd64 #1 SMP PREEMPT_DYNAMIC Debian 6.1.106-3 (2024-08-26) x86_64

The programs included with the Debian GNU/Linux system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Debian GNU/Linux comes with ABSOLUTELY NO WARRANTY, to the extent
permitted by applicable law.
Last login: Tue Feb  4 17:51:02 2025 from 84.251.61.224
root@debian-1cpu-1gb-fi-hel1:~# exit 
logout
Connection to 94.237.33.39 closed.
santeri@santeri-virtualbox:~$ ssh santeri@94.237.33.39
Linux debian-1cpu-1gb-fi-hel1 6.1.0-25-amd64 #1 SMP PREEMPT_DYNAMIC Debian 6.1.106-3 (2024-08-26) x86_64

The programs included with the Debian GNU/Linux system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Debian GNU/Linux comes with ABSOLUTELY NO WARRANTY, to the extent
permitted by applicable law.
Last login: Tue Feb  4 17:58:01 2025 from 84.251.61.224
santeri@debian-1cpu-1gb-fi-hel1:~$ cd /
santeri@debian-1cpu-1gb-fi-hel1:/$ ls
bin   dev  home        initrd.img.old  lib64       media  opt   root  sbin  sys  usr  vmlinuz
boot  etc  initrd.img  lib             lost+found  mnt    proc  run   srv   tmp  var  vmlinuz.old
santeri@debian-1cpu-1gb-fi-hel1:/$ cd /root
-bash: cd: /root: Permission denied
santeri@debian-1cpu-1gb-fi-hel1:/$ cd root
-bash: cd: root: Permission denied
santeri@debian-1cpu-1gb-fi-hel1:/$ ls
bin   dev  home        initrd.img.old  lib64       media  opt   root  sbin  sys  usr  vmlinuz
boot  etc  initrd.img  lib             lost+found  mnt    proc  run   srv   tmp  var  vmlinuz.old
santeri@debian-1cpu-1gb-fi-hel1:/$ sudo rm /root/.ssh -r
[sudo] password for santeri: 
santeri@debian-1cpu-1gb-fi-hel1:/$ exit
logout
Connection to 94.237.33.39 closed.
santeri@santeri-virtualbox:~$ ssh root@94.237.33.39
root@94.237.33.39: Permission denied (publickey).
santeri@santeri-virtualbox:~$ ssh santeri@94.237.33.39
Linux debian-1cpu-1gb-fi-hel1 6.1.0-25-amd64 #1 SMP PREEMPT_DYNAMIC Debian 6.1.106-3 (2024-08-26) x86_64

The programs included with the Debian GNU/Linux system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Debian GNU/Linux comes with ABSOLUTELY NO WARRANTY, to the extent
permitted by applicable law.
Last login: Tue Feb  4 17:59:50 2025 from 84.251.61.224
santeri@debian-1cpu-1gb-fi-hel1:~$ ^C
santeri@debian-1cpu-1gb-fi-hel1:~$ 




santeri@debian-1cpu-1gb-fi-hel1:~$ hostname
debian-1cpu-1gb-fi-hel1
santeri@debian-1cpu-1gb-fi-hel1:~$ sudo apt-get update
[sudo] password for santeri: 
Get:1 http://security.debian.org bookworm-security InRelease [48.0 kB]
Get:2 http://deb.debian.org/debian bookworm InRelease [151 kB]
Get:3 http://deb.debian.org/debian bookworm-updates InRelease [55.4 kB]
Get:4 http://security.debian.org bookworm-security/main Sources [140 kB]
Get:5 http://security.debian.org bookworm-security/main amd64 Packages [243 kB]
Get:6 http://security.debian.org bookworm-security/main Translation-en [144 kB]
Get:7 http://deb.debian.org/debian bookworm/main Sources [9496 kB]
Get:8 http://deb.debian.org/debian bookworm/main amd64 Packages [8792 kB]
Get:9 http://deb.debian.org/debian bookworm/main Translation-en [6109 kB]
Get:10 http://deb.debian.org/debian bookworm-updates/main Sources.diff/Index [15.1 kB]
Ign:10 http://deb.debian.org/debian bookworm-updates/main Sources.diff/Index
Get:11 http://deb.debian.org/debian bookworm-updates/main amd64 Packages.diff/Index [15.1 kB]
Ign:11 http://deb.debian.org/debian bookworm-updates/main amd64 Packages.diff/Index
Get:12 http://deb.debian.org/debian bookworm-updates/main Translation-en.diff/Index [15.1 kB]
Get:13 http://deb.debian.org/debian bookworm-updates/main Sources [16.2 kB]
Get:14 http://deb.debian.org/debian bookworm-updates/main amd64 Packages [13.5 kB]
Get:15 http://deb.debian.org/debian bookworm-updates/main Translation-en T-2025-01-14-2009.05-F-2024-09-10-2011.55.pdiff [15.2 kB]
Get:15 http://deb.debian.org/debian bookworm-updates/main Translation-en T-2025-01-14-2009.05-F-2024-09-10-2011.55.pdiff [15.2 kB]
Fetched 25.3 MB in 2s (10.6 MB/s)                     
Reading package lists... Done
N: Repository 'http://deb.debian.org/debian bookworm InRelease' changed its 'Version' value from '12.7' to '12.9'
N: Repository 'Debian bookworm' changed its 'firmware component' value from 'non-free' to 'non-free-firmware'
N: More information about this can be found online in the Release notes at: https://www.debian.org/releases/bookworm/amd64/release-notes/ch-information.html#non-free-split
santeri@debian-1cpu-1gb-fi-hel1:~$ sudo apt-get install ufw
Reading package lists... Done
Building dependency tree... Done
The following additional packages will be installed:
  iptables libip6tc2 libnetfilter-conntrack3 libnfnetlink0
Suggested packages:
  firewalld
The following NEW packages will be installed:
  iptables libip6tc2 libnetfilter-conntrack3 libnfnetlink0 ufw
0 upgraded, 5 newly installed, 0 to remove and 53 not upgraded.
Need to get 603 kB of archives.
After this operation, 3606 kB of additional disk space will be used.
Do you want to continue? [Y/n] 
Get:1 http://deb.debian.org/debian bookworm/main amd64 libip6tc2 amd64 1.8.9-2 [19.4 kB]
Get:2 http://deb.debian.org/debian bookworm/main amd64 libnfnetlink0 amd64 1.0.2-2 [15.1 kB]
Get:3 http://deb.debian.org/debian bookworm/main amd64 libnetfilter-conntrack3 amd64 1.0.9-3 [40.7 kB]
Get:4 http://deb.debian.org/debian bookworm/main amd64 iptables amd64 1.8.9-2 [360 kB]
Get:5 http://deb.debian.org/debian bookworm/main amd64 ufw all 0.36.2-1 [168 kB]
Fetched 603 kB in 0s (11.8 MB/s)
perl: warning: Setting locale failed.
perl: warning: Please check that your locale settings:
	LANGUAGE = (unset),
	LC_ALL = (unset),
	LC_TIME = "fi_FI.UTF-8",
	LC_MONETARY = "fi_FI.UTF-8",
	LC_ADDRESS = "fi_FI.UTF-8",
	LC_TELEPHONE = "fi_FI.UTF-8",
	LC_NAME = "fi_FI.UTF-8",
	LC_MEASUREMENT = "fi_FI.UTF-8",
	LC_IDENTIFICATION = "fi_FI.UTF-8",
	LC_NUMERIC = "fi_FI.UTF-8",
	LC_PAPER = "fi_FI.UTF-8",
	LANG = "en_US.UTF-8"
    are supported and installed on your system.
perl: warning: Falling back to a fallback locale ("en_US.UTF-8").
locale: Cannot set LC_ALL to default locale: No such file or directory
Preconfiguring packages ...
Selecting previously unselected package libip6tc2:amd64.
(Reading database ... 22809 files and directories currently installed.)
Preparing to unpack .../libip6tc2_1.8.9-2_amd64.deb ...
Unpacking libip6tc2:amd64 (1.8.9-2) ...
Selecting previously unselected package libnfnetlink0:amd64.
Preparing to unpack .../libnfnetlink0_1.0.2-2_amd64.deb ...
Unpacking libnfnetlink0:amd64 (1.0.2-2) ...
Selecting previously unselected package libnetfilter-conntrack3:amd64.
Preparing to unpack .../libnetfilter-conntrack3_1.0.9-3_amd64.deb ...
Unpacking libnetfilter-conntrack3:amd64 (1.0.9-3) ...
Selecting previously unselected package iptables.
Preparing to unpack .../iptables_1.8.9-2_amd64.deb ...
Unpacking iptables (1.8.9-2) ...
Selecting previously unselected package ufw.
Preparing to unpack .../archives/ufw_0.36.2-1_all.deb ...
Unpacking ufw (0.36.2-1) ...
Setting up libip6tc2:amd64 (1.8.9-2) ...
Setting up libnfnetlink0:amd64 (1.0.2-2) ...
Setting up libnetfilter-conntrack3:amd64 (1.0.9-3) ...
Setting up iptables (1.8.9-2) ...
update-alternatives: using /usr/sbin/iptables-legacy to provide /usr/sbin/iptables (iptables) in auto mode
update-alternatives: using /usr/sbin/ip6tables-legacy to provide /usr/sbin/ip6tables (ip6tables) in auto mode
update-alternatives: using /usr/sbin/iptables-nft to provide /usr/sbin/iptables (iptables) in auto mode
update-alternatives: using /usr/sbin/ip6tables-nft to provide /usr/sbin/ip6tables (ip6tables) in auto mode
update-alternatives: using /usr/sbin/arptables-nft to provide /usr/sbin/arptables (arptables) in auto mode
update-alternatives: using /usr/sbin/ebtables-nft to provide /usr/sbin/ebtables (ebtables) in auto mode
Setting up ufw (0.36.2-1) ...
locale: Cannot set LC_ALL to default locale: No such file or directory

Creating config file /etc/ufw/before.rules with new version

Creating config file /etc/ufw/before6.rules with new version

Creating config file /etc/ufw/after.rules with new version

Creating config file /etc/ufw/after6.rules with new version
Created symlink /etc/systemd/system/multi-user.target.wants/ufw.service → /lib/systemd/system/ufw.service.
Processing triggers for rsyslog (8.2302.0-1) ...
Processing triggers for libc-bin (2.36-9+deb12u8) ...
santeri@debian-1cpu-1gb-fi-hel1:~$ sudo ufw allow
ERROR: Invalid syntax

Usage: ufw COMMAND

Commands:
 enable                          enables the firewall
 disable                         disables the firewall
 default ARG                     set default policy
 logging LEVEL                   set logging to LEVEL
 allow ARGS                      add allow rule
 deny ARGS                       add deny rule
 reject ARGS                     add reject rule
 limit ARGS                      add limit rule
 delete RULE|NUM                 delete RULE
 insert NUM RULE                 insert RULE at NUM
 prepend RULE                    prepend RULE
 route RULE                      add route RULE
 route delete RULE|NUM           delete route RULE
 route insert NUM RULE           insert route RULE at NUM
 reload                          reload firewall
 reset                           reset firewall
 status                          show firewall status
 status numbered                 show firewall status as numbered list of RULES
 status verbose                  show verbose firewall status
 show ARG                        show firewall report
 version                         display version information

Application profile commands:
 app list                        list application profiles
 app info PROFILE                show information on PROFILE
 app update PROFILE              update PROFILE
 app default ARG                 set default application policy

santeri@debian-1cpu-1gb-fi-hel1:~$ sudo ufw allow 22/tcp
Rules updated
Rules updated (v6)
santeri@debian-1cpu-1gb-fi-hel1:~$ sudo ufw enable
Command may disrupt existing ssh connections. Proceed with operation (y|n)? y
Firewall is active and enabled on system startup
santeri@debian-1cpu-1gb-fi-hel1:~$ sudo ufw status verbose
Status: active
Logging: on (low)
Default: deny (incoming), allow (outgoing), disabled (routed)
New profiles: skip

To                         Action      From
--                         ------      ----
22/tcp                     ALLOW IN    Anywhere                  
22/tcp (v6)                ALLOW IN    Anywhere (v6)   

sudo apt-get install unattended-upgrades -y
sudo apt-get dist-upgrade


santeri@santeri-virtualbox:~$ sudo apt-get install openssh-client^C
santeri@santeri-virtualbox:~$ ssh-keygen^C
santeri@santeri-virtualbox:~$ ls -a
.              Desktop     .ICEauthority  Public                                  .vboxclient-draganddrop-tty7-control.pid     Videos
..             .dmrc       .lesshst       publicsites                             .vboxclient-draganddrop-tty7-service.pid     .Xauthority
.bash_history  Documents   .local         .ssh                                    .vboxclient-hostversion-tty7-control.pid     .xsession-errors
.bash_logout   Downloads   .mozilla       .sudo_as_admin_successful               .vboxclient-seamless-tty7-control.pid        .xsession-errors.old
.bashrc        .face       Music          Templates                               .vboxclient-seamless-tty7-service.pid
.cache         .face.icon  Pictures       .vboxclient-clipboard-tty7-control.pid  .vboxclient-vmsvga-session-tty7-control.pid
.config        .gnupg      .profile       .vboxclient-clipboard-tty7-service.pid  .vboxclient-vmsvga-session-tty7-service.pid
santeri@santeri-virtualbox:~$ cd .ssh
santeri@santeri-virtualbox:~/.ssh$ ls
id_rsa  id_rsa.pub  known_hosts  known_hosts.old
santeri@santeri-virtualbox:~/.ssh$ micro id_rsa.pub 
santeri@santeri-virtualbox:~/.ssh$ 

