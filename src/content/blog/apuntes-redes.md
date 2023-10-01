---
title: 'Apuntes de redes'
description: 'Apuntes de redes'
pubDate: 'Octubre 1 2024'
heroImage: '/blog-placeholder-3.jpg'
---

Modelo OSI ( Modelo abierto de interwork)

### LAS 7 CAPAS DEL MODELO OSI

- Presentación
- Aplicación
- Sesión
- Transporte
- Red
- Enlace de datos
- Física

El modelo OSI proporciona:

- Una forma de entender como opera los dispositivos en una red
- referencia de estándares de red
- Definir interfaces "plug-and-play"

### Encapsulación de datos

Es el proceso en el cual los datos se incorporan al ordenador hasta su transmisión al medio
Se divide en

- DATOS
- SEGMENTOS
- PAQUETES
- TRAMAS
- BITS
- Los datos van desde la capa de de aplicación hasta la de sesión
  los segmentos conforma la capa de transporte
  Los paquetes conforma la capa de red
  Las tramas van en la capa de enlace de datos
  Y por ultimo los bits en la capa física

### funciones de la capa física

EL medio físico y los conectores usados para conectar dispositivos al medio viven definidos a los estandares de la capa fisica.
Los estandares de cableado son **10 BASE T**

### Normativa de cableado 568-A

colores:
B/V V BN A BA N BC C
![Alt text](/image.png)

### Normativa de cableado 568-b

colores;
B/N N BV A BA V BC C

### Rollover

Se conectan en orden inverso
1 2 3 4 5 6 7 8
8 7 6 5 4 3 2 1

### enrutamiento

ejemplo de enrutamiento:

```shell
enable
configure terminal
hostname LEON
line console 0
password cisco
login
line vty 0 4
password cisco
login
enable secret class
service password-encryption
int f 0/0
ip add 192.168.1.1 255.255.255.0
no shut

int s 0/0/0
ip add 20.20.20.1 255.255.255.0
clock rate 128000
no shut

ip route 172.16.0.0 255.255.255.0 s 0/0/0
ip route 20.20.21.0 255.255.2555 s 0/0/0
ip route 10.0.0.0 255.255.255.0 s 0/0/0
```

### Enrutamiento RIP

```shell
enable
configure terminal
hostname NAME
router rip
version 2
no auto-summary
network <IP tipo 192.168.1.0>
network <IP tipo 20.20.20.0>
exit
exit
write memory
```

### Modelo TCP/IP

| Capa OSI        | Capa TCP/IP     | Protocolos                                          |
| --------------- | --------------- | --------------------------------------------------- |
| Aplicación      | Aplicación      | HTTP, FTP, SMTP, DNS, DHCP, TFTP, SNMP, Telnet, SSH |
| Presentación    |                 |                                                     |
| Sesión          |                 |                                                     |
| Transporte      | Transporte      | TCP, UDP                                            |
| Red             | Internet        | IP, ARP, ICMP, IGMP                                 |
| Enlace de datos | Acceso a la red | Ethernet, PPP, HDLC, Frame Relay, ATM               |
| Física          |                 |                                                     |
