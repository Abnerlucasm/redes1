# Índice

- [1...Observações](#observações)
- [2...Como calcular](#como-calcular)
- [3...Conceitos](#conceitos)
- [4...Calculadora de Sub Redes](#calculadora-de-sub-redes)
- [5...Exemplos](#exemplos)


---


# Observações
Sub rede serve para separar as máquinas na rede, com máscaras diferentes. (setores por exemplo)

- Cada sub rede tem o seu próprio broadcast e gateway, ou seja, de todos os ip's que o alcance (range) da sub rede tem, 2 sempre serão reservados a essa função, por exemplo, se dividirmos a rede em 2 sub redes com 128 ip's cada uma, teremos de subtrair 2 ip's para broadcast e gateway, sobrando 126 ip's para serem distribuídos entre os host's;

- Para criar uma sub rede, é necessário usar bits do octeto dos host's para fazer a divisão das redes;

- A sub rede pode dividir uma rede para não ser necessário usar todos os ips(hosts) disponíveis da mesma. Sendo possível usar somente o necessário;

- As sub redes são em múltiplos de 2;

- Recapitulando a divisão dos octetos em uma rede ipv4 de classe C temos:

| Rede | Rede | Rede | Host |
| ---- | ---- | ---- | ---- |
| 255  | 255  | 255  | 0    |

Em binário:

| Rede (Octe. 1)  | Rede (Octe. 2)  | Rede (Octe. 3)  | Host (Octe. 4)  |
| :-------------: | :-------------: | :-------------: | :-------------: |
| 1.1.1.1.1.1.1.1 | 1.1.1.1.1.1.1.1 | 1.1.1.1.1.1.1.1 | 0.0.0.0.0.0.0.0 |

Isso é um exemplo de uma rede sem sub redes, o ultimo octeto é totalmente dedicado a ser distribuído entre os host's que conectarem nessa rede.

Um exemplo de uma rede dividida em duas sub redes fica:

| Rede | Rede | Rede | Host |
| ---- | ---- | ---- | ---- |
| 255  | 255  | 255  | 128  |

Em binário:

| Rede (Octe. 1)  | Rede (Octe. 2)  | Rede (Octe. 3)  | Sub rede/Host (Octe. 4) |
| :-------------: | :-------------: | :-------------: | :---------------------: |
| 1.1.1.1.1.1.1.1 | 1.1.1.1.1.1.1.1 | 1.1.1.1.1.1.1.1 |     1.0.0.0.0.0.0.0     |

Isso significa que os ip's em que o ultimo octeto fique entre os valores 0 e 127 (0.0.0.0.0.0.0.0 a 0.1.1.1.1.1.1.1) pertencem a primeira sub rede, já os ip's que fiquem entre os valores 128 e 255 (1.0.0.0.0.0.0.0 a 1.1.1.1.1.1.1.1) fazem parte da segunda sub rede.

- Cada bit da máscara representa 2 sub rede, por exemplo:

|       IP        | Quantidades de IP's por rede | IP's disponiveis | Mascara | Bits alocados a sub rede |
| :-------------: | :--------------------------: | :--------------: | :-----: | :----------------------: |
|  255.255.255.0  |             256              |       254        |   /24   |            0             |
| 255.255.255.128 |             128              |       126        |   /25   |            1             |
| 255.255.255.192 |              64              |        62        |   /26   |            2             |
| 255.255.255.224 |              32              |        30        |   /27   |            3             |
| 255.255.255.240 |              16              |        14        |   /28   |            4             |
| 255.255.255.248 |              8               |        6         |   /29   |            5             |
| 255.255.255.252 |              4               |        2         |   /30   |            6             |
| 255.255.255.254 |              2               |        0         |   /31   |            7             |
| 255.255.255.255 |              1               |        0         |   /32   |            8             |

> [!NOTE]
> Ajustar formatação no markdown

Quando pega 2 bits = 4 sub redes
4 combinações = 
00 - 0x128+0x64 = 0
01 = 64
10 = 128
11 = 192


| Descrição       | Combinação     |
| :-------------: |:-------------: |
| Sub rede 1      |  0.0.1.1.1.1.1 |
| Sub rede 2      |  0.1.1.1.1.1.1 |
| Sub rede 3      |  1.0.1.1.1.1.1 |
| Sub rede 4      |  1.1.1.1.1.1.1 |


___

> [!NOTE]
> Ajustar formatação no markdown

representações de 2 bits = 4 sub redes
bits            ¹    ²
máscara             -    -   -   -   -   -   -   -
possibilidades    128  64  32  16  8   4   2   1   = 


| BIT | COMBINAÇÃO | REGRA DE COMBINAÇÃO |
| :---|  :---:     |  ---:               |
|0    |     0 0    |    (00 = 0)         |
|0    |     0 1    |    (01 = 64)        |
|0    |     1 0    |    (10 = 128)       |
|0    |     1 1    |    (11 = 192)       |
|1    |     0 0    |                     |
|1    |     0 1    |                     |
|1    |     1 0    |                     |
|1    |     1 1    |                     |


> [!NOTE]
> Ajustar formatação no markdown

3 bits

¹    ²   ³
-    -   - 
128  64  32

000=0-31
001=32-63
010=64-95
011=96-127
100=128-159
101=160-191
110=192-223
111=224-255
Perde 16 endereços


_______

> [!NOTE]
> Ajustar formatação no markdown

Rede C
256 possibilidades, 254 hosts = 1 sub rede

3 sub redes = 256/3-2=

________


- Máscara = da esquerda para a direita
________

> [!NOTE]
> Ajustar formatação no markdown

- HOSTS
|  Rede     |      Hosts            |  Total |
|:--------- | :--------------------:| ----:  |
|  R    R   | H  |  H |  H  | H |  H |  H |        |        
|  -    -   | -  | -  | -  | -  | -  | - |        |
| 128   64  | 32 | 16 | 8 |  4  | 2  | 1 | = 255  |


> [!NOTE]
> Ajustar formatação no markdown

15 hosts
Quantos bits vou usar = 4 ->  2 elevado na 4 = 16-2 = 4, seria necessário usar 5 bits

---

# Como calcular
## 1) Quantos bits são necessários para descobrir a quantidade de Hosts?
QTD SUB REDE | BIT   |  POSSIBILIDADES/HOSTS |  (-) BROADCAST E GATEWAY  | TOTAL  |
| :---       | :---: |            ---:       |           :---:           |  ---:  |
1            |  2¹   |       2               |            2              |        |
1            |  2²   |       4               |            2              |        |
1            |  2³   |       8               |            2              |        |
1            |  2⁴   |       16              |            2              |        |
1            |  2⁵   |       32              |            2              |        | 
1            |  2⁶   |       64              |            2              |  [...] |
1            |  2⁷   |       128             |            2              |  126   | 
1            |  2⁸   |       256             |            2              |  254   |

## 2) Passo a passo para calcular a máscara de sub-rede para /24:

### 1 . **Entenda a notação CIDR:** 
- /24 significa que a máscara de sub-rede tem 24 bits definidos como 1.

### 2 . **Escreva a máscara de sub-rede em binário:**
- /24 em binário é: 11111111.11111111.11111111.00000000

### 3 . **Converta a máscara de sub-rede para decimal:**
- O número binário 11111111 corresponde ao número decimal 255.

- Assim, a máscara de sub-rede para /24 é: 255.255.255.0
Portanto, a máscara de sub-rede para uma notação /24 é 255.255.255.0.

### Exemplos adicionais:
- /25: 11111111.11111111.11111111.10000000 -> 255.255.255.128
- /26: 11111111.11111111.11111111.11000000 -> 255.255.255.192
- /27: 11111111.11111111.11111111.11100000 -> 255.255.255.224
  
Cada bit adicional usado para a máscara de sub-rede reduz o número de endereços IP disponíveis para hosts na sub-rede. Para /24, há 256 endereços IP possíveis, dos quais 254 podem ser atribuídos a hosts (os outros dois são usados para o endereço de rede e o endereço de broadcast).

## 3) Passo a passo para calcular a máscara de sub-rede alternativas (sem conversão de binário):
Para sub-redes menos comuns ou diferentes, você pode usar a seguinte fórmula para calcular a máscara de sub-rede:

1. **Determine quantos bits são usados para a parte do host**: Isso é feito subtraindo o número de bits da máscara de sub-rede (o número após a barra) de 32. Por exemplo, para /24: 32 - 24 = 8 bits para hosts.

2. **Calcule o número de hosts possíveis**: Use a fórmula \(2^{\text{número de bits para hosts}} - 2\) para encontrar o número de hosts utilizáveis. Por exemplo, para /24: \(2^8 - 2 = 254\) hosts.

3. **Use a tabela ou fórmula para converter para a máscara de sub-rede**:
   - /24: 255.255.255.0
   - /25: 255.255.255.128
   - /26: 255.255.255.192
   - /27: 255.255.255.224

Essa abordagem é mais rápida e elimina a necessidade de conversão binária. Memorizar algumas das máscaras de sub-rede mais comuns e usar tabelas de referência pode simplificar muito o processo.

---

### Exemplos de Sub redes
##### Rede comum, sem sub-rede

| Rede | Rede | Host | Host |
| :---: | :---: | :---: | :---: |
| 192  | 168  |  15  |  10  |
| 255  | 255  |  0   |  0   |
#### Bits do ultimo octeto do ip, usado para dividir sub-redes

|  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| 128 | 64  | 32  | 16  |  8  |  4  |  2  |  1  |

##### Rede dividida, com 4 sub-redes divididas igualmente

| Sub-redes | Rede | Rede | Host | inicio sub | final sub |
| --------: | :---: | :---: | :---: | :--------: | :-------: |
|    Rede 1 | 255  | 255  |  0   |     0      |    63     |
|    Rede 2 | 255  | 255  |  0   |     64     |    127    |
|    Rede 3 | 255  | 255  |  0   |    128     |    191    |
|    Rede 4 | 255  | 255  |  0   |    192     |    255    |

##### Rede dividida, com 8 sub-redes divididas igualmente

| Sub-redes | Rede | Rede | Host | inicio sub | final sub |
| --------: | :---: | :---: | :---: | :--------: | :-------: |
|    Rede 1 | 255  | 255  |  0   |     0      |    31     |
|    Rede 2 | 255  | 255  |  0   |     32     |    63     |
|    Rede 3 | 255  | 255  |  0   |     64     |    95     |
|    Rede 4 | 255  | 255  |  0   |     96     |    127    |
|    Rede 5 | 255  | 255  |  0   |    128     |    159    |
|    Rede 6 | 255  | 255  |  0   |    160     |    191    |
|    Rede 7 | 255  | 255  |  0   |    192     |    223    |
|    Rede 8 | 255  | 255  |  0   |    224     |    255    |



---
# Conceitos

- **BIT**: Possui 2 valores. (0 e 1)
- **BYTE**: Possui 8 casas/bits com 32 possibilidades cada(bit), totalizando 256 possibilidades.
- **FTP**: File Transfer Protocol, protocolo para transferência de arquivos da rede local para a rede externa
- **DNS**: Armazena o endereço de texto do IP. Exemplo: www.google.com (173.194.219.94)
- **GATEWAY**: IP reservado para comunicação.
- - **Exemplo**: Em uma rede com IP 192.168.1.0, o gateway pode ser 192.168.1.1.
- **DHCP**: Atribui IPs automaticamente.
- - **Exemplo**: Um roteador configura os dispositivos na rede com IPs 192.168.1.2, 192.168.1.3, etc.
- **BROADCAST**: Comunicação para todos dispositivos.
- - **Exemplo**: Enviar um pacote para 192.168.1.255 atinge todos os dispositivos na rede 192.168.1.0/24.
---

# Calculadora de Sub Redes

[Acesse aqui](https://www.site24x7.com/pt/tools/ipv4-sub-rede-calculadora.html)



# Exemplos

- **Problema:** Vamos considerar que pretendem organizar uma LAN Party e querem criar 
6 sub-redes. Como requisito, cada uma das sub-redes deverá suportar 30 hosts 
(máquinas). A vossa rede principal é 192.168.1.0/24 e tem suporte para 254 hosts. 
Como proceder a essa divisão?

<img width="463" alt="image" src="https://github.com/Abnerlucasm/redes1/assets/101808345/502096da-9e83-405a-b7bc-fd37807fba2e">


- Para começar vamos recordar quais os requisitos: 
• Cada sub-rede deve ter suporte para pelo menos 30 hosts; 
• No mínimo devemos ter 6 sub-redes; 

Antes de proceder aos cálculos, vamos verificar se é possível satisfazer tais requisitos. 
Ora se a minha rede principal suporta 254 máquinas então 30 (PC’s) x 6 (sub-redes) = 
180, logo será possível satisfazer o pedido. Foi também tido em conta que serão 
“perdidos” dois endereços por cada sub-rede: o endereço de sub-rede que identificará 
essa sub-rede e o endereço de broadcast de casa sub-rede. 

Dando prioridade à exigência a nível de PC’s, vamos considerar o diagrama seguinte e 
responder à seguinte questão: Em que número da elipse amarela conseguiriam encaixar 
32 PC’s (30 é o números de PCs + 1 que é o endereço para a sub-rede e +1 endereço de 
broadcast, que dá um total de 32). Ora têm 3 possibilidades: no 128, 64 ou 32.

No entanto, a escolha deverá recair sobre 32 por ser o número mais próximo (neste exemplo 
até é igual) do solicitado.

<img width="441" alt="image" src="https://github.com/Abnerlucasm/redes1/assets/101808345/0e2578f4-e23c-4d2c-adc4-75b8a6299865">


Sabendo que a escolha é então 32 podemos então rapidamente afirmar que as sub-rede 
distam 32 endereços umas das outras e que podemos variar 3 bits.

<img width="173" alt="image" src="https://github.com/Abnerlucasm/redes1/assets/101808345/97bd7640-3ed8-4088-aeed-807542bf97c6">

Além disso vamos também ter de alterar a mascara da rede principal e ajustar às sub
redes. Como a máscara original é /24 (255.255.255.0) e como agora passamos a ter mais 
sub-redes e menos endereços disponíveis por cada sub-rede, então a máscara terá de 
avançar para a frente no último octeto. Como estamos a usar mais 3 bits do último 
octeto, basta efectuar a soma o peso dos mesmos (128+64+32 = 224). Então a nova 
máscara a aplicar às novas sub-redes será: 255.255.255.224 (/27).

<img width="418" alt="image" src="https://github.com/Abnerlucasm/redes1/assets/101808345/cc3991f4-51f8-45c5-95af-d28306e60500">

Considerando a rede principal, após a sua divisão em sub-redes com 30 hosts cada 
temos algo do tipo:

<img width="411" alt="image" src="https://github.com/Abnerlucasm/redes1/assets/101808345/4c82a1ac-2f35-4dd4-bfc2-1f7c2edfa426">

Nesta fase já temos todas as informações para responder à pergunta inicial. Para isso 
elaborei um pequeno quadro: 

<img width="410" alt="image" src="https://github.com/Abnerlucasm/redes1/assets/101808345/1c1a86ea-fe4e-4ec0-8cdc-105a3acb5141">

Como podemos verificar, o resultado foram mais de 6 sub-redes mas conseguimos 
cumprir o requisitos de 30 hosts por rede. Das 8 redes agora basta usarem 6. 
___
