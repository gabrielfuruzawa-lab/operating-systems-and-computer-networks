# Operating Systems and Computer Networks - Aula 5-6

# Atividade: Comutação, Gateway, ARP e Comparação Prática (Switch vs. Hub)

## Visão Geral
Repositório destinado à documentação da atividade prática e teórica das Aulas 5 e 6, cobrindo o fatiamento estático de redes IPv4 por meio do método do bloco, alocação de hosts válidos, configuração de máscaras de sub-rede e validação de isolamento de tráfego via Camada 3 e Packet Tracer.

### Topologia das Sub-redes (Fatiamento /26)
Após aplicar o método do bloco com a máscara `/26` (`255.255.255.192`, bloco de 64), a rede base foi dividida em 4 sub-redes distintas de 62 hosts úteis cada[cite: 2, 3]:

| Sub-rede | Endereço de Rede | Faixa de Hosts Úteis | Endereço de Broadcast | Máscara / Prefixo |
| :--- | :--- | :--- | :--- | :--- |
| **Sub-rede 1** | `192.168.20.0` | `192.168.20.1` a `192.168.20.62` | `192.168.20.63` | `255.255.255.192` (`/26`) |
| **Sub-rede 2** | `192.168.20.64` | `192.168.20.65` a `192.168.20.126` | `192.168.20.127` | `255.255.255.192` (`/26`) |
| **Sub-rede 3** | `192.168.20.128` | `192.168.20.129` a `192.168.20.190` | `192.168.20.191` | `255.255.255.192` (`/26`) |
| **Sub-rede 4** | `192.168.20.192` | `192.168.20.193` a `192.168.20.254` | `192.168.20.255` | `255.255.255.192` (`/26`) |