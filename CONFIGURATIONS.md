# Configurations – VLAN et trunk 802.1Q

Configuration complète de chaque équipement, exportée depuis le fichier Packet Tracer.
Les mots de passe et numéros de série sont masqués ; les interfaces sans configuration sont omises.
Les fichiers bruts (un par équipement) sont dans [`configs/`](configs/).

## Sommaire

- [S1](#s1) – Switch 2960-24TT
- [S2](#s2) – Switch 2960-24TT
- [Postes et serveurs](#postes-et-serveurs)

## Postes et serveurs

| Nom | Type | Adresse IP | Masque | Passerelle | DNS |
|---|---|---|---|---|---|
| PC-A | Pc | 192.168.10.3 | 255.255.255.0 | 192.168.10.1 | – |
| PC-B | Pc | 192.168.10.4 | 255.255.255.0 | 192.168.10.1 | – |

## S1

Switch · modèle 2960-24TT · hostname `S1`

```cisco
!
version 15.0
no service timestamps log datetime msec
no service timestamps debug datetime msec
service password-encryption
!
hostname S1
!
enable secret 5 <redacted>
!
no ip domain-lookup
!
spanning-tree mode pvst
spanning-tree extend system-id
!
interface FastEthernet0/1
 switchport trunk native vlan 1000
 switchport mode trunk
!
interface FastEthernet0/2
 shutdown
!
interface FastEthernet0/3
 shutdown
!
interface FastEthernet0/4
 shutdown
!
interface FastEthernet0/5
 shutdown
!
interface FastEthernet0/6
 switchport access vlan 10
 switchport mode access
!
interface FastEthernet0/7
 shutdown
!
interface FastEthernet0/8
 shutdown
!
interface FastEthernet0/9
 shutdown
!
interface FastEthernet0/10
 shutdown
!
interface FastEthernet0/11
 switchport access vlan 10
 switchport mode access
 shutdown
!
interface FastEthernet0/12
 switchport access vlan 99
 switchport mode access
 shutdown
!
interface FastEthernet0/13
 switchport access vlan 99
 switchport mode access
 shutdown
!
interface FastEthernet0/14
 switchport access vlan 99
 switchport mode access
 shutdown
!
interface FastEthernet0/15
 switchport access vlan 99
 switchport mode access
 shutdown
!
interface FastEthernet0/16
 switchport access vlan 99
 switchport mode access
 shutdown
!
interface FastEthernet0/17
 switchport access vlan 99
 switchport mode access
 shutdown
!
interface FastEthernet0/18
 switchport access vlan 99
 switchport mode access
 shutdown
!
interface FastEthernet0/19
 switchport access vlan 99
 switchport mode access
 shutdown
!
interface FastEthernet0/20
 switchport access vlan 99
 switchport mode access
 shutdown
!
interface FastEthernet0/21
 switchport access vlan 10
 switchport mode access
 shutdown
!
interface FastEthernet0/22
 switchport access vlan 99
 switchport mode access
 shutdown
!
interface FastEthernet0/23
 switchport access vlan 99
 switchport mode access
 shutdown
!
interface FastEthernet0/24
 switchport mode access
 shutdown
!
interface GigabitEthernet0/1
 shutdown
!
interface GigabitEthernet0/2
 shutdown
!
interface Vlan1
 no ip address
!
interface Vlan99
 ip address 192.168.1.11 255.255.255.0
!
banner motd "Warning Unauthorized access only"
!
line con 0
 password 7 <redacted>
 login
!
line vty 0 4
 password 7 <redacted>
 login
line vty 5 15
 password 7 <redacted>
 login
!
end
```

## S2

Switch · modèle 2960-24TT · hostname `S2`

```cisco
!
version 15.0
no service timestamps log datetime msec
no service timestamps debug datetime msec
service password-encryption
!
hostname S2
!
enable secret 5 <redacted>
!
no ip domain-lookup
!
spanning-tree mode pvst
spanning-tree extend system-id
!
interface FastEthernet0/1
 switchport trunk native vlan 1000
 switchport mode trunk
!
interface FastEthernet0/2
 shutdown
!
interface FastEthernet0/3
 shutdown
!
interface FastEthernet0/4
 shutdown
!
interface FastEthernet0/5
 shutdown
!
interface FastEthernet0/6
 shutdown
!
interface FastEthernet0/7
 shutdown
!
interface FastEthernet0/8
 shutdown
!
interface FastEthernet0/9
 shutdown
!
interface FastEthernet0/10
 shutdown
!
interface FastEthernet0/11
 shutdown
!
interface FastEthernet0/12
 shutdown
!
interface FastEthernet0/13
 shutdown
!
interface FastEthernet0/14
 shutdown
!
interface FastEthernet0/15
 shutdown
!
interface FastEthernet0/16
 shutdown
!
interface FastEthernet0/17
 shutdown
!
interface FastEthernet0/18
 switchport access vlan 10
 switchport mode access
!
interface FastEthernet0/19
 shutdown
!
interface FastEthernet0/20
 shutdown
!
interface FastEthernet0/21
 shutdown
!
interface FastEthernet0/22
 shutdown
!
interface FastEthernet0/23
 shutdown
!
interface FastEthernet0/24
 shutdown
!
interface GigabitEthernet0/1
 shutdown
!
interface GigabitEthernet0/2
 shutdown
!
interface Vlan1
 no ip address
!
interface Vlan99
 ip address 192.168.1.12 255.255.255.0
!
banner motd "Warning unauthorized access is strictly prohibited"
!
line con 0
 password 7 <redacted>
 login
!
line vty 0 4
 password 7 <redacted>
 login
line vty 5 15
 password 7 <redacted>
 login
!
end
```
