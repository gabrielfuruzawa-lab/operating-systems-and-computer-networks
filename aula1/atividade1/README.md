# Operating Systems and Computer Networks - Aula 3

# Atividade 1: Configuração Inicial de LAN, Switch, Roteamento e Resolução ARP

## Visão Geral
Repositório destinado à documentação da atividade prática da Aula 1, cobrindo a implementação e validação de uma rede local estruturada com Switch de Camada 2, Roteamento IP (Camada 3) e o comportamento do protocolo ARP na resolução de endereços físicos.

### Passos de Configuração Realizados

1. **Segurança e Identidade dos Dispositivos**:
   * Definição de nomes de host, configuração de endereçamento IP nas interfaces de rede e validação das conexões físicas dos nós da rede.
2. **Configuração da Camada de Enlace e Gerência (Switch)**:
   * Criação do endereço IP de gerência na SVI (`Vlan1`) dos switches e alocação correta dos gateways padrão para assegurar a comunicação local e inter-redes.
3. **Configuração da Camada de Rede (Roteador)**:
   * Atribuição de endereços IP nas interfaces físicas do roteador central Cisco 1941 e ativação das portas com o comando `no shutdown`.

### Topologia da Rede Local (Sub-rede `192.168.1.0/24`)

| Dispositivo | Interface / SVI | Endereço IP | Máscara de Sub-rede | Gateway Padrão |
| :--- | :--- | :--- | :--- | :--- |
| **Roteador** | GigabitEthernet 0/0 | `192.168.1.1` | `255.255.255.0` | — |
| **SwitchA** | SVI (Vlan1) | `192.168.1.254` | `255.255.255.0` | `192.168.1.1` |
| **PC-A** | Eth | `192.168.1.10` | `255.255.255.0` | `192.168.1.1` |

---

### Validação Prática e Resolução ARP
Durante os testes de conectividade inicial utilizando o comando `ping`, observou-se o comportamento padrão do protocolo ARP:
* **Perda inicial de pacotes**: O primeiro pacote enviado resulta em *Request timed out* devido ao processo de descoberta de endereço MAC (Broadcast ARP).
* **Estabilização da conexão**: Após o preenchimento da tabela ARP, os pacotes subsequentes apresentam 0% de perda de pacotes e tempos de resposta inferiores a 1ms.

