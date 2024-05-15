# Observações
- Cada rede tem o seu próprio broadcast

- Quando houver uma sub rede o bit de 255(256-1) será divido no final da máscara, exemplo: 2 sub redes: 255.255.255.128 (representando em 256 bits = binário(1 binário = 256 bits)), 
representa que há duas redes.

- Cada bit da máscara representa 2 sub rede

- Sub rede serve para separar as máquinas na rede, com máscaras diferentes. (setores por exemplo)

- A sub rede pode dividir uma rede para não ser necessário usar todos os ips(hosts) disponíveis da mesma. Sendo possível usar somente o necessário.

- Nova sub rede sempre vai ter um novo broadcast e gateway, ou seja, perde sempre 2 possibilidades. (256 - 2)

- As sub redes são em multiplos de 2


Quando pega 2 bits = 4 sub redes
4 combinações = 
00 - 0x128+0x64 = 0
01 = 64
10 = 128
11 = 192

Sub rede 1
0.0.1.1.1.1.1

Sub rede 2
0.1.1.1.1.1.1

Sub rede 3
1.0.1.1.1.1.1

Sub rede 4
1.1.1.1.1.1.1

___
representações de 2 bits = 4 sub redes
bits            ¹    ²
máscara             -    -   -   -   -   -   -   -
possibilidades    128  64  32  16  8   4   2   1   = 


| BIT | COMBINAÇÃO | REGRA DE COMBINAÇÃO |
| :---|  :---:     |  ---:               |
0     |     0 0    |    (00 = 0)         |
0     |     0 1    |    (01 = 64)        |
0     |     1 0    |    (10 = 128)       |
0     |     1 1    |    (11 = 192)       |
1     |     0 0    |                     |
1     |     0 1    |                     |
1     |     1 0    |                     |
1     |     1 1    |                     |



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

Rede C
256 possibilidades, 254 hosts = 1 sub rede

3 sub redes = 256/3-2=

________


- Máscara = da esquerda para a direita
________



HOSTS
                  Rede             Hosts
                |---------|  |----------------|

bits                
               | R | R | H | H | H | H | H | H |
máscara        | - | - | - | - | - | - | - | - |
possibilidades |128| 64| 32| 16| 8 | 4 | 2 | 1 |  =
X = 255



15 hosts
Quantos bits vou usar = 4 ->  2 elevado na 4 = 16-2 = 4, seria necessário usar 5 bits

# Como calcular?
## 1) Descobrir quantos bits necessários para descobrir a quantidade de Hosts.
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
- **BYTE**: Possui 8 casas com 32 possibilidades cada, totalizando 256 possibilidades


---

# Calculadora de Sub Redes

[Acesse aqui](https://www.site24x7.com/pt/tools/ipv4-sub-rede-calculadora.html)


___
