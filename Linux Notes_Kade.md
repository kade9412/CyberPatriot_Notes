# Configuring the Kernel
>Turn on SELinux
>> **/etc/selinux/config**
>>
>>>SELINUX=permisive

>Disable ICMP Responses
>> `sysctl net.ipv4.icmp_echo_ignore_all`
>>**/etc/sysctl.conf**
>>>`net.ipv4.icmp_echo_ignore_all = 1`
>>
>>`sudo sysctl -p`

>Enable Comand Line Logging
# INPROGRESS

# Configure Password Policy
>`sudo pam install libpam-pwquality`
>**/etc/pam.d/common-password**
>>password   requisite   pam_pwquality.so retry=3 minlen=12 maxrepeat=3 ucredit=-1 lcredit=-1 dcredit=-1 ocredit=-1 difok=4 reject_username enforce_for_root
>
>**/etc/pam.d/system-auth**
>>password	requisite 	pam_pwquality.so try_first_pass local_users_only retry=3 authtok_type= minlen=12 lcredit=-1 ucredit=-1 dcredit=-1 ocredit=-1 enforce_for_root
>
>**DON'T forget to reset password to match new requirements after**
>
>Reboot after resetting the password
# Database Management
>Does the Database store the user credentials
>>## PostgreSQL
>You only need to provide the service name and specify the datavase to connect to get access
# SSH Security
>`/etc/sshd/sshd_config`
>> Port 222
>>
>> PermitRootLogin no
>> 
>> MaxAuthTries 3
>>
>> LoginGraceTime 20
>>
>> PasswordAuthentication no
>>
>> PermitEmptyPasswords no
>>
>> ChallengeResponseAuthentication no
>>
>> KerberosAuthentication no
>>
>> GSSAPIAutentication no
>>
>> X11Forwarding no
>>
>> PermitUserEnvironment no
>>
>> AllowAgentForwarding no
>>
>> AllowTcpForwarding no
>>
>> PermitTunnel no
>>
>> Banner `/etc/ssh/banner` // If file does not exist create it
# FTP security
>
# Nginx security
>
# Apache2 security
>
# File security
>
# Environment Variables
>
# Tools
>Stacer (https://oguzhaninan.github.io/Stacer-Web/)
> chmod cheat sheet (https://quickref.me/chmod.html)