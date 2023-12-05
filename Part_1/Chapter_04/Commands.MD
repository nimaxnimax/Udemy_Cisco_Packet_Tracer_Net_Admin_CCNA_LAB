Commands:


****************************************************************************************************
Cisco Router Commands >> Interface IP Configuration and Verification

enable

show ip int bri

configure terminal

do show ip int bri

interface FastEthernet0/0

ip address 192.168.11.254 255.255.255.0

no shutdown

interface FastEthernet0/1

ip address 192.168.13.254 255.255.255.0

no shutdown

do write

exit

write memory

show ip route

show ip arp


****************************************************************************************************
Cisco Router Commands >> Telnet Configuration and Verification

line vty 0 15

exec-timeout 30 0

password cisco

login

do write

do show run


****************************************************************************************************
End Device - Windows Commands >> IP Verification and Telnet

ipconfig

ipconfig /all

arp -a

telnet 192.168.11.254

