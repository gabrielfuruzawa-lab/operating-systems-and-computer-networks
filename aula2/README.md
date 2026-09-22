# Operating Systems and Computer Networks - Aula 2

## Atividade 1 — Comunicação LAN pela camada 2

### Visão Geral
Configuração de LAN e comunicação pela camada 2 entre dois dispositivos ('192.168.1.10' e '192.168.1.11') e configuração de IP do SVI do Switch0.

## Tabela de Endereçamento
| Dispositivo | Interface / SVI | Endereço IP | Máscara de Sub-rede |
| :--- | :--- | :--- | :--- |
| **PC-0** | Eth | `192.168.1.10` | `255.255.255.0` |
| **Switch0** | SVI (Vlan1) | `192.168.1.254` | `255.255.255.0` |
| **PC-1** | Eth | `192.168.1.11` | `255.255.255.0` |

### Validação de Conectividade 
C:\>ping 192.168.1.11
Pinging 192.168.1.11 with 32 bytes of data:
Reply from 192.168.1.11: bytes=32 time<3ms TTL=255

C:\>ping 192.168.1.254
Pinging 192.168.1.254 with 32 bytes of data:
Reply from 192.168.1.254: bytes=32 time<3ms TTL=255
