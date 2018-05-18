# Linux Package Management


## YUM

> **YUM** (Yellowdog Updater Modified) is an open source command-line as well as graphical based package management tool for **RPM** (RedHat Package Manager) based Linux systems.



[20 Linux YUM (Yellowdog Updater, Modified) Commands for Package Management](https://www.tecmint.com/20-linux-yum-yellowdog-updater-modified-commands-for-package-mangement/)


1. Install a Package with YUM

To install a package called Firefox 14, just run the below command it will automatically find and install all required dependencies for Firefox.

```
# yum install firefox
Loaded plugins: fastestmirror
Dependencies Resolved
================================================================================================
Package                    Arch        Version                    Repository            Size        
================================================================================================
Updating:
firefox                        i686        10.0.6-1.el6.centos     updates             20 M
Updating for dependencies:
xulrunner                     i686        10.0.6-1.el6.centos     updates             12 M
Transaction Summary
================================================================================================
Install       0 Package(s)
Upgrade       2 Package(s)
Total download size: 32 M
Is this ok [y/N]: y
Downloading Packages:
(1/2): firefox-10.0.6-1.el6.centos.i686.rpm                                |  20 MB   01:10
(2/2): xulrunner-10.0.6-1.el6.centos.i686.rpm                              |  12 MB   00:52
------------------------------------------------------------------------------------------------
Total                                                           63 kB/s |  32 MB   02:04
Updated:
firefox.i686 0:10.0.6-1.el6.centos
Dependency Updated:
xulrunner.i686 0:10.0.6-1.el6.centos
Complete!
The above command will ask confirmation before installing any package on your system. If you want to install packages automatically without asking any confirmation, use option -y as shown in below example.

# yum -y install firefox
```

2. Removing a Package with YUM

To remove a package completely with their all dependencies, just run the following command as shown below.

```
# yum remove firefox
Loaded plugins: fastestmirror
Setting up Remove Process
Resolving Dependencies
--> Running transaction check
---> Package firefox.i686 0:10.0.6-1.el6.centos set to be erased
--> Finished Dependency Resolution
Dependencies Resolved
====================================================================================================
Package                    Arch        Version                        Repository            Size        
====================================================================================================
Removing:
firefox                    i686        10.0.6-1.el6.centos            @updates              23 M
Transaction Summary
====================================================================================================
Remove        1 Package(s)
Reinstall     0 Package(s)
Downgrade     0 Package(s)
Is this ok [y/N]: y
Downloading Packages:
Running rpm_check_debug
Running Transaction Test
Transaction Test Succeeded
Running Transaction
Erasing        : firefox-10.0.6-1.el6.centos.i686                                                                                                                          1/1
Removed:
firefox.i686 0:10.0.6-1.el6.centos
Complete!
Same way the above command will ask confirmation before removing a package. To disable confirmation prompt just add option -y as shown in below.

# yum -y remove firefox
```

3. Updating a Package using YUM

Let’s say you have outdated version of MySQL package and you want to update it to the latest stable version. Just run the following command it will automatically resolves all dependencies issues and install them.

```
# yum update mysql
Loaded plugins: fastestmirror
Dependencies Resolved
============================================================================================================
Package            Arch                Version                    Repository                    Size
============================================================================================================
Updating:
vsftpd             i386                2.0.5-24.el5_8.1           updates                       144 k
Transaction Summary
============================================================================================================
Install       0 Package(s)
Upgrade       1 Package(s)
Total size: 144 k
Is this ok [y/N]: y
Downloading Packages:
Running rpm_check_debug
Running Transaction Test
Finished Transaction Test
Transaction Test Succeeded
Running Transaction
Updating       : vsftpd                                                                     1/2
Cleanup        : vsftpd                                                                     2/2
Updated:
vsftpd.i386 0:2.0.5-24.el5_8.1
Complete!
```

4. List a Package using YUM

Use the list function to search for the specific package with name. For example to search for a package called openssh, use the command.

```
# yum list openssh
Loaded plugins: fastestmirror
Loading mirror speeds from cached hostfile
* base: mirror.neu.edu.cn
* epel: mirror.neu.edu.cn
* extras: mirror.neu.edu.cn
* rpmforge: mirror.nl.leaseweb.net
* updates: mirror.nus.edu.sg
Installed Packages
openssh.i386                                       4.3p2-72.el5_6.3                                                                      installed
Available Packages                                 4.3p2-82.el5                                                                          base
To make your search more accurate, define package name with their version, in case you know. For example to search for a specific version openssh-4.3p2 of the package, use the command.

# yum list openssh-4.3p2
```

5. Search for a Package using YUM

If you don’t remember the exact name of the package, then use search function to search all the available packages to match the name of the package you specified. For example, to search all the packages that matches the word .

```
# yum search vsftpd
Loaded plugins: fastestmirror
Loading mirror speeds from cached hostfile
* base: mirror.neu.edu.cn
* epel: mirror.neu.edu.cn
* extras: mirror.neu.edu.cn
* rpmforge: mirror.nl.leaseweb.net
* updates: ftp.iitm.ac.in
============================== Matched: vsftpd ========================
ccze.i386 : A robust log colorizer
pure-ftpd-selinux.i386 : SELinux support for Pure-FTPD
vsftpd.i386 : vsftpd - Very Secure Ftp Daemon
```

6. Get Information of a Package using YUM

Say you would like to know information of a package before installing it. To get information of a package just issue the below command.

```
# yum info firefox
Loaded plugins: fastestmirror
Loading mirror speeds from cached hostfile
* base: mirror.neu.edu.cn
* epel: mirror.neu.edu.cn
* extras: mirror.neu.edu.cn
* rpmforge: mirror.nl.leaseweb.net
* updates: ftp.iitm.ac.in
Available Packages
Name       : firefox
Arch       : i386
Version    : 10.0.6
Release    : 1.el5.centos
Size       : 20 M
Repo       : updates
Summary    : Mozilla Firefox Web browser
URL        : http://www.mozilla.org/projects/firefox/
License    : MPLv1.1 or GPLv2+ or LGPLv2+
Description: Mozilla Firefox is an open-source web browser, designed for standards
: compliance, performance and portability.
```

7. List all Available Packages using YUM

To list all the available packages in the Yum database, use the below command.

```
# yum list | less
```

8. List all Installed Packages using YUM

To list all the installed packages on a system, just issue below command, it will display all the installed packages.

```
# yum list installed | less
```

9. Yum Provides Function
Yum provides function is used to find which package a specific file belongs to. For example, if you would like to know the name of the package that has the /etc/httpd/conf/httpd.conf.

```
# yum provides /etc/httpd/conf/httpd.conf
Loaded plugins: fastestmirror
httpd-2.2.3-63.el5.centos.i386 : Apache HTTP Server
Repo        : base
Matched from:
Filename    : /etc/httpd/conf/httpd.conf
httpd-2.2.3-63.el5.centos.1.i386 : Apache HTTP Server
Repo        : updates
Matched from:
Filename    : /etc/httpd/conf/httpd.conf
httpd-2.2.3-65.el5.centos.i386 : Apache HTTP Server
Repo        : updates
Matched from:
Filename    : /etc/httpd/conf/httpd.conf
httpd-2.2.3-53.el5.centos.1.i386 : Apache HTTP Server
Repo        : installed
Matched from:
Other       : Provides-match: /etc/httpd/conf/httpd.conf
```

10. Check for Available Updates using Yum
To find how many of installed packages on your system have updates available, to check use the following command.

```
# yum check-update
11. Update System using Yum
To keep your system up-to-date with all security and binary package updates, run the following command. It will install all latest patches and security updates to your system.

# yum update
```

12. List all available Group Packages
In Linux, number of packages are bundled to particular group. Instead of installing individual packages with yum, you can install particular group that will install all the related packages that belongs to the group. For example to list all the available groups, just issue following command.

```
# yum grouplist
Installed Groups:
Administration Tools
DNS Name Server
Dialup Networking Support
Editors
Engineering and Scientific
FTP Server
Graphics
Java Development
Legacy Network Server
Available Groups:
Authoring and Publishing
Base
Beagle
Cluster Storage
Clustering
Development Libraries
Development Tools
Eclipse
Educational Software
KDE (K Desktop Environment)
KDE Software Development
```

13. Install a Group Packages
To install a particular package group, we use option as groupinstall. Fore example, to install “MySQL Database“, just execute the below command.

```
# yum groupinstall 'MySQL Database'
Dependencies Resolved
=================================================================================================
Package								Arch      Version			 Repository        Size
=================================================================================================
Updating:
unixODBC                           i386      2.2.11-10.el5      base              290 k
Installing for dependencies:
unixODBC-libs                      i386      2.2.11-10.el5      base              551 k
Transaction Summary
=================================================================================================
Install       1 Package(s)
Upgrade       1 Package(s)
Total size: 841 k
Is this ok [y/N]: y
Downloading Packages:
Running rpm_check_debug
Running Transaction Test
Finished Transaction Test
Transaction Test Succeeded
Running Transaction
Installing     : unixODBC-libs	1/3
Updating       : unixODBC         2/3
Cleanup        : unixODBC         3/3
Dependency Installed:
unixODBC-libs.i386 0:2.2.11-10.el5
Updated:
unixODBC.i386 0:2.2.11-10.el5
Complete!
```

14. Update a Group Packages
To update any existing installed group packages, just run the following command as shown below.

```
# yum groupupdate 'DNS Name Server'
Dependencies Resolved
================================================================================================================
Package			Arch	        Version				Repository           Size
================================================================================================================
Updating:
bind                           i386            30:9.3.6-20.P1.el5_8.2          updates              981 k
bind-chroot                    i386            30:9.3.6-20.P1.el5_8.2          updates              47 k
Updating for dependencies:
bind-libs                      i386            30:9.3.6-20.P1.el5_8.2          updates              864 k
bind-utils                     i386            30:9.3.6-20.P1.el5_8.2          updates              174 k
Transaction Summary
================================================================================================================
Install       0 Package(s)
Upgrade       4 Package(s)
Total size: 2.0 M
Is this ok [y/N]: y
Downloading Packages:
Running rpm_check_debug
Running Transaction Test
Finished Transaction Test
Transaction Test Succeeded
Running Transaction
Updating       : bind-libs            1/8
Updating       : bind                 2/8
Updating       : bind-chroot          3/8
Updating       : bind-utils           4/8
Cleanup        : bind                 5/8
Cleanup        : bind-chroot          6/8
Cleanup        : bind-utils           7/8
Cleanup        : bind-libs            8/8
Updated:
bind.i386 30:9.3.6-20.P1.el5_8.2                  bind-chroot.i386 30:9.3.6-20.P1.el5_8.2
Dependency Updated:
bind-libs.i386 30:9.3.6-20.P1.el5_8.2             bind-utils.i386 30:9.3.6-20.P1.el5_8.2
Complete!
```

15. Remove a Group Packages
To delete or remove any existing installed group from the system, just use below command.

```
# yum groupremove 'DNS Name Server'
Dependencies Resolved
===========================================================================================================
Package                Arch              Version                         Repository          Size
===========================================================================================================
Removing:
bind                   i386              30:9.3.6-20.P1.el5_8.2          installed           2.1 M
bind-chroot            i386              30:9.3.6-20.P1.el5_8.2          installed           0.0
Transaction Summary
===========================================================================================================
Remove        2 Package(s)
Reinstall     0 Package(s)
Downgrade     0 Package(s)
Is this ok [y/N]: y
Downloading Packages:
Running rpm_check_debug
Running Transaction Test
Finished Transaction Test
Transaction Test Succeeded
Running Transaction
Erasing        : bind                                                   1/2
warning: /etc/sysconfig/named saved as /etc/sysconfig/named.rpmsave
Erasing        : bind-chroot                                            2/2
Removed:
bind.i386 30:9.3.6-20.P1.el5_8.2                                        bind-chroot.i386 30:9.3.6-20.P1.el5_8.2
Complete!
```

16. List Enabled Yum Repositories
To list all enabled Yum repositories in your system, use following option.

```
# yum repolist
repo id                     repo name                                            status
base                        CentOS-5 - Base                                      enabled:  2,725
epel                        Extra Packages for Enterprise Linux 5 - i386         enabled:  5,783
extras                      CentOS-5 - Extras                                    enabled:    282
mod-pagespeed               mod-pagespeed                                        enabled:      1
rpmforge                    RHEL 5 - RPMforge.net - dag                          enabled: 11,290
updates                     CentOS-5 - Updates                                   enabled:    743
repolist: 20,824
```

16. List all Enabled and Disabled Yum Repositories
The following command will display all enabled and disabled yum repositories on the system.

```
# yum repolist all
repo id                     repo name                                            status
C5.0-base                   CentOS-5.0 - Base                                    disabled
C5.0-centosplus             CentOS-5.0 - Plus                                    disabled
C5.0-extras                 CentOS-5.0 - Extras                                  disabled
base                        CentOS-5 - Base                                      enabled:  2,725
epel                        Extra Packages for Enterprise Linux 5 - i386         enabled:  5,783
extras                      CentOS-5 - Extras                                    enabled:    282
repolist: 20,824
```

17. Install a Package from Specific Repository
To install a particular package from a specific enabled or disabled repository, you must use –enablerepo option in your yum command. For example to Install PhpMyAdmin 3.5.2 package, just execute the command.

```
# yum --enablerepo=epel install phpmyadmin
Dependencies Resolved
=============================================================================================
Package                Arch           Version            Repository           Size
=============================================================================================
Installing:
phpMyAdmin             noarch         3.5.1-1.el6        epel                 4.2 M
Transaction Summary
=============================================================================================
Install       1 Package(s)
Total download size: 4.2 M
Installed size: 17 M
Is this ok [y/N]: y
Downloading Packages:
phpMyAdmin-3.5.1-1.el6.noarch.rpm                       | 4.2 MB     00:25
Running rpm_check_debug
Running Transaction Test
Transaction Test Succeeded
Running Transaction
Installing : phpMyAdmin-3.5.1-1.el6.noarch             1/1
Verifying  : phpMyAdmin-3.5.1-1.el6.noarch             1/1
Installed:
phpMyAdmin.noarch 0:3.5.1-1.el6
Complete!
```

18. Interactive Yum Shell
Yum utility provides a custom shell where you can execute multiple commands.

```
# yum shell
Loaded plugins: fastestmirror
Setting up Yum Shell
> update httpd
Loading mirror speeds from cached hostfile
* base: mirrors.sin3.sg.voxel.net
* epel: ftp.riken.jp
* extras: mirrors.sin3.sg.voxel.net
* updates: mirrors.sin3.sg.voxel.net
Setting up Update Process
>
```

19. Clean Yum Cache
By default yum keeps all the repository enabled package data in /var/cache/yum/ with each sub-directory, to clean all cached files from enabled repository, you need to run the following command regularly to clean up all the cache and make sure that there is nothing unnecessary space is using. We don’t want to give the output of the below command, because we like to keep cached data as it is.

```
# yum clean all
```

20. View History of Yum
To view all the past transactions of yum command, just use the following command.

```
# yum history
Loaded plugins: fastestmirror
ID     | Login user               | Date and time    | Action(s)      | Altered
-------------------------------------------------------------------------------
10 | root               | 2012-08-11 15:19 | Install        |    3
9 | root               | 2012-08-11 15:11 | Install        |    1
8 | root               | 2012-08-11 15:10 | Erase          |    1 EE
7 | root               | 2012-08-10 17:44 | Install        |    1
6 | root               | 2012-08-10 12:19 | Install        |    2
5 | root               | 2012-08-10 12:14 | Install        |    3
4 | root               | 2012-08-10 12:12 | I, U           |   13 E<
3 | root               | 2012-08-09 13:01 | Install        |    1 >
2 | root               | 2012-08-08 20:13 | I, U           |  292 EE
1 | System            | 2012-08-08 17:15 | Install        |  560
history list
```


We have tried to cover all the basic to advance yum commands with their examples. If anything related to yum commands may have missed out. Please update us through our comment box. So, we keep updating the same based on feedback’s received.

