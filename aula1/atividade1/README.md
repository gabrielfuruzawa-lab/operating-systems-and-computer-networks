# Operating Systems and Computer Networks - Aula 5-6

# Atividade: Configuração Inicial de LAN, Switch e divisão em subredes /26

## Visão Geral
Repositório destinado à documentação da atividade prática da Aula 1, cobrindo a implementação e validação de uma rede local estruturada com Switch de Camada 2, Roteamento IP (Camada 3) e o comportamento do protocolo ARP na resolução de endereços físicos.

### Topologia das Sub-redes (Fatiamento /26)
Após aplicar o método do bloco com a máscara `/26` (`255.255.255.192`, bloco de 64), a rede base foi dividida em 4 sub-redes distintas de 62 hosts úteis cada:

| Sub-rede | Endereço de Rede | Faixa de Hosts Úteis | Endereço de Broadcast | Máscara / Prefixo |
| :--- | :--- | :--- | :--- | :--- |
| **Sub-rede 1** | `192.168.20.0` | `192.168.20.1` a `192.168.20.62` | `192.168.20.63` | `255.255.255.192` (`/26`) |
| **Sub-rede 2** | `192.168.20.64` | `192.168.20.65` a `192.168.20.126` | `192.168.20.127` | `255.255.255.192` (`/26`) |
| **Sub-rede 3** | `192.168.20.128` | `192.168.20.129` a `192.168.20.190` | `192.168.20.191` | `255.255.255.192` (`/26`) |
| **Sub-rede 4** | `192.168.20.192` | `192.168.20.193` a `192.168.20.254` | `192.168.20.255` | `255.255.255.192` (`/26`) |
