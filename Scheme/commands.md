# Set up

## Router

enable
config terminal
ip dhcp pool First_Pool
dns-server 8.8.8.8
network 192.168.1.0 255.255.255.0
exit
ip dhcp excluded-address 192.168.1.1 192.168.0.10
int g0/0/0
no sh

// для сервака
int g0/0/1
no sh
//

