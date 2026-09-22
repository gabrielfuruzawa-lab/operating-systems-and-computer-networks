# Operating Systems and Computer Networks - Aula 1 

## Atividade 1

### Visão Geral
A atividade simula a configuração de IPs de dois end-devices e configuração de IP do Switch para teste de ping.

### Topologia
- **PC0** - IP '192.168.1.10'/24 (Switch0 porta 'Fa0/1')
- **PC1** - IP '192.168.1.11/24' (Switch0 porta 'Fa0/2')
- **Switch0 (SVI Vlan1)** - IP '192.168.1.254/24'

### Validação de Conectividade
```text
C:\> ping 192.168.1.11
Reply from 192.168.1.11: bytes=32 time<1ms TTL=128

C:\> ping 192.168.1.254
Reply from 192.168.1.254: bytes=32 time<1ms TTL=128