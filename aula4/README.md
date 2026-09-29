# Operating Systems and Computer Networks - Aula 4

# Atividade: Configuração Básica de Switch, Dispositivos Finais e Camada de Enlace

## Visão Geral
Repositório destinado à documentação da atividade prática da Aula 4, cobrindo a implementação, segurança básica de CLI e validação de uma rede local estruturada com switches de Camada 2, atribuição de endereçamento IP em hosts e configuração de interfaces de gerência (SVI).

### Passos de Configuração Realizados

1. **Segurança e Identidade dos Dispositivos**:
   * Definição de nomes de host (Hostnames), configuração de senhas de console, senhas secretas de administrador (`enable secret`), criptografia de texto simples e aplicação de banners MOTD.
2. **Configuração da Camada de Enlace e Gerência (Switch)**:
   * Criação do endereço IP de gerência na SVI (`Vlan1`) dos switches, ativação das portas físicas através do comando `no shutdown` e estruturação da interconexão via cabo crossover.
3. **Configuração da Camada de Rede (Dispositivos Finais)**:
   * Atribuição de endereços IP estáticos e máscaras de sub-rede nas interfaces de rede (NIC) dos computadores para assegurar a comunicação local na mesma sub-rede.

### Topologia da Rede Local (Sub-rede `192.168.1.0/24`)

| Dispositivo | Interface / SVI | Endereço IP | Máscara de Sub-rede | Gateway Padrão |
| :--- | :--- | :--- | :--- | :--- |
| **Switch0 (S1)** | SVI (Vlan1) | `192.168.1.252` | `255.255.255.0` | — |
| **Switch1 (S2)** | SVI (Vlan1) | `192.168.1.253` | `255.255.255.0` | — |
| **PC0 (PC1)** | NIC | `192.168.1.10` | `255.255.255.0` | — |
| **PC1 (PC2)** | NIC | `192.168.1.20` | `255.255.255.0` | — |

---

### Validação Prática e Conectividade Local
Durante os testes de conectividade utilizando o comando `ping` entre os dispositivos finais e os switches:
* **Conectividade de Camada 2**: Com a interligação física correta entre os switches utilizando cabo cruzado (*crossover*), os quadros Ethernet são comutados com sucesso na mesma sub-rede.
* **Estabilização da Rede**: Os testes de envio de pacotes ICMP evidenciam 0% de perda e respostas imediatas entre os computadores e as interfaces de gerência (SVI).