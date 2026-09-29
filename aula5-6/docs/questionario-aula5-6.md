# Lista de Exercícios Práticos — Aula 05-06: Sub-redes IPv4

Documento contendo os exercícios práticos de fixação sobre endereçamento IPv4, cálculo de sub-redes pelo método do bloco e validação via Packet Tracer.

---

## 📋 Exercício 1 — Sub-redes /27
Divida a rede **192.168.30.0/24** em sub-redes **/27**. Calcule o bloco e preencha a tabela abaixo:

* **Bloco** = 256 − ______ = ______        
* **Hosts por sub-rede** = 2^5 - 2 = ______

| Sub-rede (/27) | Primeiro host | Último host | Broadcast |
| :--- | :--- | :--- | :--- |
| `192.168.30.0` | `192.168.30.1` | `192.168.30.30` | `192.168.30.31` |
| `192.168.30.32` | `192.168.30.33` | `192.168.30.62` | `192.168.30.63` |
| `192.168.30.64` | `192.168.30.65` | `192.168.30.94` | `192.168.30.95` |
| `192.168.30.96` | `192.168.30.97` | `192.168.30.126` | `192.168.30.127` |
| `192.168.30.128` | `192.168.30.129` | `192.168.30.158` | `192.168.30.159` |
| `192.168.30.160` | `192.168.30.161` | `192.168.30.190` | `192.168.30.191` |
| `192.168.30.192` | `192.168.30.193` | `192.168.30.222` | `192.168.30.223` |
| `192.168.30.224` | `192.168.30.225` | `192.168.30.254` | `192.168.30.255` |

---

## 📋 Exercício 2 — Identificação de Sub-rede de Host
Considere o host **192.168.40.100/26**. Responda:

* **Endereço de rede**: 192.168.40.64
* **Broadcast**: 192.168.40.127
* **Primeiro host**: 192.168.40.65
* **Último host**: 192.168.40.126
* **O host 192.168.40.130 está na mesma sub-rede? Resposta: Não, o host 192.168.40.130 está na rede 192.168.40.128.**

## 🚀 Desafio Extra (Opcional)
A empresa precisa de **3 redes com pelo menos 50 hosts cada**, a partir de **192.168.50.0/24**. Qual prefixo atende? 

* **Prefixo escolhido**: /26    
* **Justificativa (hosts por sub-rede)**: o prefixo /26 garante 62 hosts possíveis e um porta para broadcast sem desperdício de endereços.