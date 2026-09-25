# Operating Systems and Computer Networks - Aula 3

# Atividade: Comutação, Gateway, ARP e Comparação Prática (Switch vs. Hub)

## Visão Geral
Repositório destinado à entrega da atividade prática da Aula 3, cobrindo a implementação de uma LAN com Switch de Camada 2, Roteamento, Tabelas MAC, Protocolo ARP, além da análise comparativa comportamental com o uso de um Hub de Camada 1.

### Passos de Configuração Realizados

1. **Segurança e Identidade dos Dispositivos**:
   * Definição de Hostname (`SW1` e `R1`), senhas de console (`line console 0`), senhas de acesso remoto via VTY (`line vty 0 15`), criptografia de senha para o modo privilegiado (`enable secret`) e aplicação de `service password-encryption`[cite: 1, 2].
2. **Configuração da Camada de Enlace e Gerência (Switch)**:
   * Criação do endereço IP de gerência na SVI da VLAN 1 (`192.168.10.2`) e configuração do `ip default-gateway` para assegurar o retorno de pacotes de gerência remota[cite: 1, 2].
3. **Configuração da Camada de Rede (Roteador)**:
   * Atribuição de IP na interface física voltada para a LAN (`G0/0` com `192.168.10.1`) e ativação da interface com o comando `no shutdown`[cite: 1].

### Topologia da Rede Principal (Sub-rede `192.168.10.0/24`)

| Dispositivo | Endereço IP | Máscara de Sub-rede | Gateway Padrão | Porta de Conexão |
| :--- | :--- | :--- | :--- | :--- |
| **Roteador R1** | `192.168.10.1` | `255.255.255.0` | — | `GigabitEthernet0/0` |
| **Switch SW1 (SVI)** | `192.168.10.2` | `255.255.255.0` | `192.168.10.1` | VLAN 1 (Gerência) |
| **PC0** | `192.168.10.10`| `255.255.255.0` | `192.168.10.1` | `FastEthernet0/1` |
| **PC1** | `192.168.10.20` | `255.255.255.0` | `192.168.10.1` | `FastEthernet0/2` |
| **PC2** | `192.168.10.30` | `255.255.255.0` | `192.168.10.1` | `FastEthernet0/3` |

---

### Desafio Extra: Substituição do Switch pelo Hub (Camada 1 vs. Camada 2)
Montou-se um segundo cenário de testes isolado substituindo o switch por um Hub para fins de análise comportamental no modo Simulation:
* **Ausência de Tabela MAC**: O Hub opera estritamente na Camada 1 (Física), não processando endereços de hardware e não mantendo tabelas de comutação.
* **Replicação Cega (*Flooding/Broadcasting* físico)**: Diferente do switch (que direciona quadros em *unicast* estrito para a porta correta), o Hub repete eletricamente cada quadro recebido para todas as portas simultaneamente, gerando um único domínio de colisão e compartilhamento total do meio físico.

### Topologia do Cenário Secundário (Hub - Sub-rede `192.168.10.0/24`)

| Dispositivo | Endereço IP | Máscara de Sub-rede | Gateway Padrão | Porta de Conexão |
| :--- | :--- | :--- | :--- | :--- |
| **Roteador R2**  | `192.168.20.1` | `255.255.255.0` | — | `GigabitEthernet`  |
| **Hub** | Sem IP (Camada 1) | *N/A* | *N/A* | Portas Multi-acesso |
| **PC0** (ou novos PCs) | `192.168.20.10` | `255.255.255.0` | `192.168.20.1` | Porta Física do Hub |
| **PC01** (ou novos PCs) | `192.168.20.20` | `255.255.255.0` | `192.168.20.1` | Porta Física do Hub |