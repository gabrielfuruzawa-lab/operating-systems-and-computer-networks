# Operating Systems and Computer Networks

## Atividade 2 — Roteamento entre LANs (Camada 3)

### Visão Geral
Configuração de duas redes locais segmentadas (`192.168.1.0/24` e `192.168.2.0/24`) interligadas por um roteador central (Cisco 1941), validando a comunicação de Camada 3 e o papel dos gateways padrão no sistema operacional dos hosts.

## Tabela de Endereçamento
| Dispositivo | Interface / SVI | Endereço IP | Máscara de Sub-rede | Gateway Padrão |
| :--- | :--- | :--- | :--- | :--- |
| **PC-A** | Eth | `192.168.1.10` | `255.255.255.0` | `192.168.1.1` |
| **SwitchA** | SVI (Vlan1) | `192.168.1.254` | `255.255.255.0` | `192.168.1.1` |
| **Roteador 1941** | GigabitEthernet 0/0 | `192.168.1.1` | `255.255.255.0` | — |
| **Roteador 1941** | GigabitEthernet 0/1 | `192.168.2.1` | `255.255.255.0` | — |
| **SwitchB** | SVI (Vlan1) | `192.168.2.254` | `255.255.255.0` | `192.168.2.1` |
| **PC-B** | Eth | `192.168.2.10` | `255.255.255.0` | `192.168.2.1` |

### Validação de Conectividade 
C:\>ping 192.168.2.10
Pinging 192.168.2.10 with 32 bytes of data:
Reply from 192.168.2.10: bytes=32 time<1ms TTL=127

C:\>ping 192.168.1.254
Pinging 192.168.1.254 with 32 bytes of data:
Reply from 192.168.1.254: bytes=32 time<1ms TTL=255

C:\>ping 192.168.2.254
Pinging 192.168.2.254 with 32 bytes of data:
Reply from 192.168.2.254: bytes=32 time<1ms TTL=254
