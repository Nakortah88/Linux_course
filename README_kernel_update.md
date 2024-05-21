# Создал ВМ на GCP c операционной системой OpenSUSE 8 Stream.
[nakortah@centos8 ~]$ uname -r
4.18.0-552.1.1.el8.x86_64
# Подлюкчил репозиторий и забрал необходимую версию ядра
[nakortah@centos8 ~]$ sudo yum install -y https://www.elrepo.org/elrepo-release-8.el8.elrepo.noarch.rpm
CentOS Stream 8 - AppStream                                                                                                                                                               19 MB/s |  28 MB     00:01    
CentOS Stream 8 - BaseOS                                                                                                                                                                  18 MB/s |  10 MB     00:00    
CentOS Stream 8 - Extras                                                                                                                                                                  31 kB/s |  18 kB     00:00    
CentOS Stream 8 - Extras common packages                                                                                                                                                  19 kB/s | 7.7 kB     00:00    
Google Compute Engine                                                                                                                                                                     33 kB/s | 8.4 kB     00:00    
Google Cloud SDK                                                                                                                                                                          54 MB/s | 126 MB     00:02    
elrepo-release-8.el8.elrepo.noarch.rpm                                                                                                                                                    79 kB/s |  13 kB     00:00    
Dependencies resolved.
=========================================================================================================================================================================================================================
 Package                                               Architecture                                  Version                                                   Repository                                           Size
=========================================================================================================================================================================================================================
Installing:
 elrepo-release                                        noarch                                        8.3-1.el8.elrepo                                          @commandline                                         13 k

Transaction Summary
=========================================================================================================================================================================================================================
Install  1 Package

Total size: 13 k
Installed size: 5.0 k
Downloading Packages:
Running transaction check
Transaction check succeeded.
Running transaction test
Transaction test succeeded.
Running transaction
  Preparing        :                                                                                                                                                                                                 1/1 
  Installing       : elrepo-release-8.3-1.el8.elrepo.noarch                                                                                                                                                          1/1 
  Verifying        : elrepo-release-8.3-1.el8.elrepo.noarch                                                                                                                                                          1/1 

Installed:
  elrepo-release-8.3-1.el8.elrepo.noarch                                                                                                                                                                                 

Complete!
[nakortah@centos8 ~]$ sudo yum --enablerepo elrepo-kernel install kernel-ml -y
ELRepo.org Community Enterprise Linux Repository - el8                                                                                                                                   228 kB/s | 207 kB     00:00    
ELRepo.org Community Enterprise Linux Kernel Repository - el8                                                                                                                            1.8 MB/s | 2.2 MB     00:01    
Dependencies resolved.
=========================================================================================================================================================================================================================
 Package                                                 Architecture                                 Version                                                  Repository                                           Size
=========================================================================================================================================================================================================================
Installing:
 kernel-ml                                               x86_64                                       6.9.1-1.el8.elrepo                                       elrepo-kernel                                       127 k
Installing dependencies:
 kernel-ml-core                                          x86_64                                       6.9.1-1.el8.elrepo                                       elrepo-kernel                                        40 M
 kernel-ml-modules                                       x86_64                                       6.9.1-1.el8.elrepo                                       elrepo-kernel                                        34 M

Transaction Summary
=========================================================================================================================================================================================================================
Install  3 Packages

Total download size: 74 M
Installed size: 116 M
Downloading Packages:
(1/3): kernel-ml-6.9.1-1.el8.elrepo.x86_64.rpm                                                                                                                                           227 kB/s | 127 kB     00:00    
(2/3): kernel-ml-modules-6.9.1-1.el8.elrepo.x86_64.rpm                                                                                                                                    12 MB/s |  34 MB     00:02    
(3/3): kernel-ml-core-6.9.1-1.el8.elrepo.x86_64.rpm                                                                                                                                       12 MB/s |  40 MB     00:03    
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Total                                                                                                                                                                                     21 MB/s |  74 MB     00:03     
ELRepo.org Community Enterprise Linux Kernel Repository - el8                                                                                                                            1.6 MB/s | 1.7 kB     00:00    
Importing GPG key 0xBAADAE52:
 Userid     : "elrepo.org (RPM Signing Key for elrepo.org) <secure@elrepo.org>"
 Fingerprint: 96C0 104F 6315 4731 1E0B B1AE 309B C305 BAAD AE52
 From       : /etc/pki/rpm-gpg/RPM-GPG-KEY-elrepo.org
Key imported successfully
Running transaction check
Transaction check succeeded.
Running transaction test
Transaction test succeeded.
Running transaction
  Preparing        :                                                                                                                                                                                                 1/1 
  Installing       : kernel-ml-core-6.9.1-1.el8.elrepo.x86_64                                                                                                                                                        1/3 
  Running scriptlet: kernel-ml-core-6.9.1-1.el8.elrepo.x86_64                                                                                                                                                        1/3 
  Installing       : kernel-ml-modules-6.9.1-1.el8.elrepo.x86_64                                                                                                                                                     2/3 
  Running scriptlet: kernel-ml-modules-6.9.1-1.el8.elrepo.x86_64                                                                                                                                                     2/3 
  Installing       : kernel-ml-6.9.1-1.el8.elrepo.x86_64                                                                                                                                                             3/3 
  Running scriptlet: kernel-ml-core-6.9.1-1.el8.elrepo.x86_64                                                                                                                                                        3/3 
  Running scriptlet: kernel-ml-6.9.1-1.el8.elrepo.x86_64                                                                                                                                                             3/3 
  Verifying        : kernel-ml-6.9.1-1.el8.elrepo.x86_64                                                                                                                                                             1/3 
  Verifying        : kernel-ml-core-6.9.1-1.el8.elrepo.x86_64                                                                                                                                                        2/3 
  Verifying        : kernel-ml-modules-6.9.1-1.el8.elrepo.x86_64                                                                                                                                                     3/3 

Installed:
  kernel-ml-6.9.1-1.el8.elrepo.x86_64                                kernel-ml-core-6.9.1-1.el8.elrepo.x86_64                                kernel-ml-modules-6.9.1-1.el8.elrepo.x86_64                               

Complete!

# Установил ядро из репозитория.

[nakortah@centos8 ~]$ sudo yum --enablerepo elrepo-kernel install kernel-ml -y
Last metadata expiration check: 0:03:31 ago on Tue 21 May 2024 09:01:18 AM UTC.
Package kernel-ml-6.9.1-1.el8.elrepo.x86_64 is already installed.
Dependencies resolved.
Nothing to do.
Complete!

# Обновил конфиг загрузчика и установил загрузку нового ядра по дефолту, ребут - ядро обновлено!

[nakortah@centos8 ~]$ uname -r
6.9.1-1.el8.elrepo.x86_64
