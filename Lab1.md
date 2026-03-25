# Laboratório 01 - Configuração inicial no PNetLab

**Disciplina:** ENE0025 - Protocolos de Transporte e Roteamento  
**Aluno:** Artur Kohara Guerra 
**Matrícula:** 231025181

---

## Objetivos do laboratório

- Compreender que redes distintas **não se comunicam automaticamente**
    
- Identificar o **papel do roteador** como elemento lógico de interconexão
    
- Diferenciar falha de comunicação por ausência de roteamento de falha física
    
- Relacionar teoria de roteamento com comportamento real da rede
    

---

## Cenário do Laboratório

### Topologia PNETLab
![Topologia da rede](./imagens/topologia_lab1.png)

---

## Recursos no PNetLab

- Escolha usar um router ou SW L3 (Cisco IOL)
    
- 2 hosts VPC
    
- 2 segmentos Ethernet
    
---

## Testes de conectividade sem roteamento

Esta primeira parte consiste em configurar os dispositivos da rede de forma que cada um seja capaz de se comunicar com o roteador (switch layer 3), mas não sejam capzes de comunicar entre si.
Ou seja, o objetivo é estruturar uma conectividade sem roteamento (gateway)

---

### Endereçamento proposto

|Dispositivo|Interface|IP|Máscara|
|---|---|---|---|
|Host A|eth0|192.168.10.10|/24|
|Router|eth0|192.168.10.1|/24|
|Router|eth1|192.168.20.1|/24|
|Host B|eth0|192.168.20.10|/24|

---

### Configuração dos hosts
- Configuração no Host A
    ![Configuração do Host A](./imagens/config_hostA.png)

- Configuração no Host B
    ![Configuração do Host B](./imagens/config_hostB.png)

---

### Configuração do roteador
![Roteador](./imagens/config_router.png)

---

### Testes
- Host A
    ![Teste Host A](./imagens/teste_hostA.png)

- Host B
    ![Teste Host B](./imagens/tetste_hostB.png)

---

### Discussão orientada
- O enlace físico funciona?
    Sim, o enlace físico funciona. Isso pode ser verificado pelo fato que o Host A consegue comunicar com o roteador (ping 192.168.10.1) e o Host B também (ping 192.168.20.1).
    Dessa forma, percebe-se que as interfaces estão ativas e as conexões estão corretas.

- O IP está configurado corretamente?
    Sim, os IPs estão configurados corretamente

- Por que o pacote não chega ao Host B?
    O pacote não chega ao Host B, pois o Host A não sabe onde está a rede 192.168.20.0, ele apenas conhece a sua própria rede do enlace (192.168.10.0/24). Logo, ele descarta o pacote