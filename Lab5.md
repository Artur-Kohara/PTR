# Relatório – Laboratório 05

## Roteamento Dinâmico com RIP e OSPF

**Disciplina:** ENE0025 - Protocolos de Transporte e Roteamento  
**Professor:** Prof. Dr. Laerte Peotta de Melo

## Identificação

- Nome: **Artur Kohara Guerra**
- Matrícula: **231025181**
- Turma: **01**

---

## 1. Objetivo

O objetivo deste experimento foi configurar e validar o roteamento dinâmico em uma topologia composta por três roteadores, utilizando os protocolos **RIP** e **OSPF**, de forma a comparar seus comportamentos, características e desempenho em um mesmo cenário de rede.

---

## 2. Descrição da Topologia

A topologia implementada no ambiente PNetLab consiste em:

- 3 roteadores:
  - Router-RJ
  - Router-SP
  - Router-BH
- 6 switches (2 por unidade)
- 12 hosts (4 por unidade)
- 2 enlaces WAN:
  - RJ ↔ SP
  - SP ↔ BH

Cada roteador conecta duas redes locais (LANs) e realiza o encaminhamento de pacotes entre as diferentes unidades.

---

## 3. Metodologia

O experimento foi dividido nas seguintes etapas:

1. Montagem da topologia no PNetLab
2. Configuração de endereçamento IP em hosts e roteadores
3. Verificação inicial sem roteamento dinâmico
4. Implementação do protocolo RIP
5. Testes de conectividade com RIP
6. Remoção do RIP
7. Implementação do protocolo OSPF
8. Testes de conectividade com OSPF
9. Análise comparativa entre os protocolos

---

## 4. Configuração Realizada

### 4.1 Configuração dos Hosts

Cada host foi configurado com:

```bash
ip <endereço_ip> <máscara> <gateway>
```
