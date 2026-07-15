# Red Hat Enterprise Linux 

**Technical Overview (RH024) v10.0**

Kernel + Distro 

- Fedora
- CentOS Stream
- RedHat Enterprise Linux - A production grade OS.   


- rpm is Package Manager for RHEL, Fedora and CentOS

*kvm, systemd and tuned started by RedHat*

Configuration & release schedule - FHS - File Hierchy Standard 

RedHat for all, it gives no cost infrastructure upto 16 servers for learning 

**LifeCycle **
- Release After every 3 years
- Support 
  - Full Support for 5 years (Bug fixes and update)
  - Maintenence Support for next 5 years (security patches) 
  - Extended Support Addon after both support ends (Selected security patches)

## Shell 
Deafult shell is `bash`

*commands + option + argument*

`du -sh /home/baz`

**Man**
- man command for manual
`man 5 crontab` gives you File format & conversetion 

**Command Line Assistant**
AI is builtin in CLI . 
- For Command LIne Assistant , your system should be registered. 

`c chat "Your question to AI"`

This connects to RedHat Server (RHEL LightSpeed)

**Directory Structure** 
- etc 
- var (Variable)
- usr (User data)
  - /usr/share (shared like documentation)
- tmp (temporary and keeps on cleaning)
- root (home of root user)
- mnt (mounting i.e USB)
- run (current status of linux) refresh on evry boot 

**Editig with vim**
Following modes of vim 
- normal (navigating)
- insert (typing )
- Command (quit, save, search)

In normal mode, u for undo , yy for copy, 10p for pasting 10 times, crtl+r for redo 

- `vimtutor` for tutorial of vim 
- `sudo` Super User DO 


**idm**
Indentity like active Directory 

- included in Red hat subscription

** Best practice:  to lock user, rather deleting it. 


`sudo -i` to get root shell
`su -` subsititue user or switch user 

** Best practice: Use sudo -i  


--

`subscription-manager indentity` to check if your system is registered. 
Satellite is proxy for  RedHat CDN 



`dnf search <package-name>` to search package 

### ERRATA 
Update package comes 
- RedHat Bug Advisory (RHBA)
- RedHat Enhancement Advisory (RHEA)
- RedHat Security Advisory (RHSA)
 

 CVE (Common Vulnerabilities & Exposure) a vendor neutral advisory, ranges from 1 to 9.8

`dnf updateinfo list` for list of packages installed 
`dnf updateinfo info RHSA-2025:10854` for showing details of Vulnerabilities

`dnf udpate --Security` only udpate packages related to Security
`dnf udpate --sec-security=Critical`  udpate security related packages of critical level

`dnf needs-restarting -r` for checking restart is needed .if no ouput then no restart needed. 

### Managing Network 
Network manager helps alot 

Profile set of property to interface 

`nmcli con show` to show connections
`nmcli con show <profile-name>` to see details of connections

** Best practice: enp7s0 = Ethernet Port 7 Slot 0 

`nmcli connection add con-name <con-name> type ethernet ifname <enp7s0> ipv4.method manual ipv4.address "192.168.1.114/24" ipv4.gateway 192.168.1.1 ipv4.dns "8.8.8.8,1.1.1.1"` to add network connection

`nmtui` network manager with UI 

### System Startup services with systemd
RedHat contributed to community 

- service (runing app , demon)
- socket (activating things and demands)
- timer (for scheduling)
- patch (watcing file and Directory)
- target (grouping unit )


** Best practice: `systemctl enable --now <service-name>` for starting and enabling service 

`firewall-cmd --add-service http`

** Best practice: !! means previous command 

`!! --permenent` use add http rule in firewall permenently 

systemctl restart http 
^restar^stop - run last command with this option 


### Deploying app runtime to host simple app 

- Installing Opertaing system 
- Update 
- Patch 
- troublesheet 


### bootc 
Make image adn point it. 

`ssh bootc` shell to bootc connection 
`bootc status` show status of boootc

open bootc host on browser

`bootc switch <image-version>` change img

#### Image Builder Tools 
Comes with ith redhat subscription
- Image Builder 
Go to `console.redhat.com` then insight to RHEL section

Vulnerability Management
- security
- compliance 

`sudo insights-client --register` to register


#### Cockpit Web Console 
Web based and can be accessed from anywhere 

sudo systemctl --now cockpit.socket

Goto browser `rhel10:9090`

