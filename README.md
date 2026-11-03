# Red-Corporativa-ospf-vpn-vlan
Red corporativa Cisco: OSPF, VPN IPsec, NAT/PAT, VLANs, EtherChannel, ACLs, SSH, VoIP y WiFi. Packet Tracer y equipos reales.

# OSPF, VPN IPsec y Seguridad

Proyecto del módulo Diseño e Implementación de Proyectos (INA, 2025),
realizado en pareja. Se diseñó e implementó la red de la empresa
Nexanet, con sede central, sucursales nacionales y una sede en Guatemala.

Se simuló en Packet Tracer y se comprobó en equipos Cisco reales.

## Topología

Semi-malla con rutas redundantes: si un enlace falla, el tráfico toma otro camino.
Routers: ORIENTAL, OCCIDENTAL, CENTRAL, EDGE, GUATEMALA, CDT-T e ISP.

## Qué se implementó

**Conectividad**
- Enrutamiento dinámico OSPF (proceso 101, área 0) y rutas estáticas
- VPN IPsec entre la sede central (EDGE) y Guatemala (ISAKMP, AES-256)
- NAT con sobrecarga (PAT) para salida a Internet
- EtherChannel entre switches

**Administración**
- VLANs de datos, voz y gestión con enrutamiento inter-VLAN
- DHCP en routers, con exclusiones de direcciones
- Acceso remoto por SSH versión 2

**Seguridad**
- ACLs en las líneas VTY y para restringir FTP y HTTP
- Port-security con MAC sticky y puertos sin uso apagados
- Banners de advertencia y contraseñas cifradas
- Red inalámbrica WPA2 (5 GHz internos, 2.4 GHz invitados)

**Servicios**
- Telefonía IP (VoIP) con Cisco Unified CME
- Servidores FTP y Web

## Direccionamiento
Subneteo de 192.168.0.0 con máscaras de longitud variable
(/24, /25, /29 y /30). Las tablas completas están en el informe.

## Pruebas y troubleshooting
Pings entre sedes, acceso FTP y Web, llamadas entre teléfonos IP, SSH
y port-security. El anexo documenta 5 errores provocados a propósito
(puerto mal conectado, exclusión DHCP incorrecta, áreas OSPF cambiadas,
option 150 errónea y servicios apagados), con su solución.

## Documentación
Informe técnico completo en [`Documentacion/`](Documentacion/).

## Tecnologías
Cisco IOS, Packet Tracer, OSPF, IPsec, NAT/PAT, VLAN, EtherChannel, SSH, ACL
