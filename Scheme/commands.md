# Set up

## Router

enable
config terminal
ip dhcp pool First_Pool
dns-server 8.8.8.8
network 192.168.1.0 255.255.255.0
exit
ip dhcp excluded-address 192.168.1.1 192.168.1.10
int g0/0/0

// Switchport
switchport mode trunk
switchport trunk allowed vlan 10,20,30,40,50,99
no sh
exit

int g0/1/0

// Switchport
switchport mode trunk
switchport trunk allowed vlan 10,20,30,40,50,99
no sh
exit

## Multilayer Switch0

// Switchport

int f0/7
switchport trunk encapsulation dot1q
switchport mode trunk
switchport trunk allowed vlan 10,20,30,40,50,99

// VLANS
int vlan 90
ip address dhcp
no sh


int range f0/1-3
switchport trunk encapsulation dot1q
switchport mode trunk
switchport trunk allowed vlan 10,20,30,40,50,99
no sh


## Multilayer Switch1

