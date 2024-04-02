---
tags:
  - redes1/anotacoes
Disciplina:
  - Redes de Computadores I
Professor:
  - Ricardo (Figura)
Categoria:
  - Exercicios
sticker: emoji//1f4c4
---
# Anotações Aula 01 27-02-24

**Enlace** = pode ser entendido como o cabo que faz a conexão do canal
**Topologia** = a forma de troca de informação entre os dispositivos, ligações (...)

**Simplex** = um recebe um envia
**Half duplex** = um envia e recebe outro recebe e envia (walkie talk/radio amador)
**Full duplex** = ambos enviam e recebem simultaneamente

---
# Anotações Aula 04 19-03-24

**Bracket** = mini racks [Exemplo](https://http2.mlstatic.com/D_NQ_NP_867095-MLB69861116337_062023-O.webp)
**Racks** = [Exemplo](https://www.ipmetal.com.br/cdn/shop/products/RACK19PARACABEAMENTOESTRUTURADODESMONTAVEL_1000x.jpg?v=1588623777)
**Patch Panel** = Conecta os path cords, entradas fêmeas [Exemplo](https://m.media-amazon.com/images/I/71YA8PsNVgL._AC_UF894,1000_QL80_.jpg)
**U (us)** = são posições no rack, posições e medidas [Exemplo]( https://cdn-diiab.nitrocdn.com/qakoxxNsZsIPYgaLTbFDkfYzpnDtOxBH/assets/images/optimized/rev-7748de2/smartplustecnologia.com/wp-content/uploads/2021/03/Redeeeeeessss-1024x1024.jpg )
**Switch** = é um equipamento que permite que dois ou mais dispositivos de TI, como computadores, comuniquem-se entre si. [Exemplo](https://gtltecnologia.com.br/wp-content/uploads/2024/01/SWITCH-IGS-4804SM_IGS-2408SM.jpg)
**Bandeja** = é indicado para organizar os equipamentos mais leves dentro do rack de cabeamento e servidor, tais como Modem, Roteador e Switch [Exemplo](https://images.tcdn.com.br/img/img_prod/625353/bandeja_fixa_ventilada_1u_x_500_mm_4_pt_preto_1734_2_80dd2a301f0300f239b40794c13b101c.jpg)
**RJ-45** = Plug do cabo de internet [Exemplo](https://centralcabos.vteximg.com.br/arquivos/ids/175508-1000-1000/conector-plug-rj45-ez-vazado-cat5e.jpg?v=637528921707900000)


# OBSERVAÇÕES
- Será utilizado máquina virtual (Win 7 Ult. 64 Bits, 50 GB Armazenamento) e path tracer.
- Deve ser postado todos os projetos da aula, fecha um dia antes da aula e pode ser postado apenas por um integrante.


# PROJETO
Informar como está o rack na sala de equipamentos



---
# **RESUMO PROVA**


> [!NOTE] ## Tipos de Rede
**San** = rede de armazenamento
**Pan** = rede pessoal, interliga sem fio os dispositivos na rede em uma curta distancia
**Wan** = rede geral, pais, continentes...
**Man** = rede distribuida por uma cidade/metropoles
**Lan** = rede local


>[!NOTE] ## Comutações
> - **Comutação de circuitos**: é necessário estabelecer uma conexão do inicio ao fim antes de enviar a informação, como é feito nos telefones residenciais.
>
>- **Comutação de pacotes**: é dividido a mensagem em pacotes menores e enviada por diversos caminhos diferentes


> [!NOTE] ## Linhas de Comunicação
>- Simplex = a comunicação é feita somente por um lado da estação
>- Half-duplex= a comunicação é feita dos dois sentidos, mas um de cada vez
>- Full-duplex= a comunicação é feita nos dois sentidos ao mesmo tempo

> [!WARNING] **Comunicação/enlance = nó (recebe/envia)**


>[!TIP] ## Topologias
>- **Anel**: todas as estações estão conectadas em um caminho fechado. 
> - **Barramento**: as estações são conectadas em t por um caminho fechado.
Topologia lógica é quem organiza, sem considerar a parte física. Quando não há login, ou seja, ninguem é cliente ou servidor a topologia é barramento.

## MEIOS DE TRANSMISSÂO

**Placa de Rede =** interface entre o computador e o cabo da rede

**Cabo Coaxial** = o cabo coaxial utilizado em sistemas de antena de TV ; topologia de barramento ; mais utilizado no passado

**Par Trançado =** desenvolvido para ser utilizado em linhas telefonicas de forma analógica ; vantagem: flexivel, taxa de transmissao alta. Utilizado em cabos de internet. Possui categorizações: CAT de 1 a 8, alterando a taxa de transferencia de dados

**Tipos de Crimpagem Cabo Trançado:** T 568 A e T 568 B (validados pela TIA/EIA)

**Cabo Crossover:** cabo cruzado, permite conexão entre 2 computadores sem hub ou switch

**Equipamentos Cabo Trançado:** Desencapador de cabos, Testador de Cabo, Alicate de Crimpagem, Alicate de push down

**Fibra Optica Estrutura:** Capa Protetora > Casca > Núcleo

**Tipo Fibra Degrau Abrupta:** atende curtas distâncias, mais facil de construir e mais barato (emissores e cabo). é refletido dentro do cabo em V

**Tipo Fibra Indice Gradual:** complexidade media de fabricacao, não possui refração constante, mas se expande do eixo até as bordas

**Tipo de Fibra Monomodo:** alta complexidade de manipulalçao, nucleo finissimo, média e longa distância.

### **VANTAGENS X DESVANTAGENS**
#### Vantagens
• Velocidade
• Isolamento elétrico
• O cabo pode ser longo
• Alta taxa de transferência
#### Desvantagens
• Muito caro
• Difícil de instalar
• Quebra com facilidade
• Difícil de ser remendado


**HUB  =** repetidor, ponto de conexão fisica dos equipamentos da rede, retransmite o que recebe aos disp. Conectados a ele, espelho,

**SWITCH=** permitem o modo full duplex, fecha o canal de comnicação entre dois dispositivos, podendo esses se comunicarem simultaneamente. Antes do switch era utiizado cabo crossover ou a porta up link do hub. É possivel interligar varios switchs desde que esteja conectados em um central


**Bridges:**
Interliga dois segmentos de rede tornando os unicos. EM redes antigas era utilizado a bridge para dividir a rede em menores segmentos aumentando o desempenho da rede.

**Roteadores:**
Interliga varias redes diferentes e encontra a melhor e mais rapida rota, nivel 3 modelo OSI

Algoritmos de roteamento:



**Hierarquia**
Core (nucleo) > Distrubuição (Roteamento entre vlan) > Acesso 


## IP

**IPV4:** Identidade da máquina na rede, composto por 4 octetos (binário) mas visualmente assume outra máscara.
Binário: 0-255 ou seja 256 possibilidades.
Exemplo de IP em binário `--------.--------.--------.--------`

**Host:** Equipamento que possui endereço IP (endereçamento)

Existe diferença entre IP Externo (177.43.22.209) e IP Local (192.168.0.1), externo é a forma como outras redes vão visualizar as requisições. Interno é utilizado para se comunicar na rede LAN e não fica visível na rede externa. Quando o IP local faz uma requisição na WAN a mesma é feita em cima do IP Externo.

Tudo precisa de IP para se comunicar.




>[!NOTE]
> ## CLASSES IP
> 
> **ID Rede |  ID Host**
`192     .  168     [...]`
> ---
>
>**Classe A**: R (126). H (256). H (256). H (256) = **001-126** = 16,77 (256 H x 256 H x 256 H - 1 R) milhões de máquinas na rede
> **Classe B**: R (064). R (256). H (256). H (256) = **128-191** = 65,534 (256 H x 256 H - 2 R) máquinas na rede
> **Classe C**: R (032). R (256). R (256). H (256) = **192-223** = 254 (256 H - 3 R = 254 H) máquinas na rede
>
>  ---
> **Legenda:**
> R = Rede, quantas redes
> H = Host, quantas máquinas dentro da rede
>
>>[!IMPORTANT] Na rede local o IP fica sem classe, ou seja não roteavel.
>
> ---
> >[!TIP]
>> **Roteador**: gerencia os IP não roteável
>> **Roteador de Borda**: gerencia os IP Roteáveis na rede WAN, dita as rotas na rede
>> **Roteamento NAT**: converte o IP não roteavel para roteavel, ou seja o roteador passa a visualizar os IP da rede interna e encaminha a requisição da rede interna para a rede externa.
>>
>>**IP:** Identidade na rede local
>>**Máscara**: Forma da Identidade na rede local
>>**Gateway**: Porta de acesso a rede global (WAN)
>> **Gateway Padrão**: encaminha pacotes / faz o caminho entre a rede interna e rede externa para o NAT
>> **Endereço de LoopBack**: Localhost, de mim para mim mesmo
>> **Network Number**: Identifica a rede, é o 0-255 dos hosts na máscara da rede
>> **Endereço Broadcast**: Comunica todos os hosts da rede pois representa todos os endereços da rede. Exemplo: 200.100.10.255
>> ---
>>> [!IMPORTANT] 
>>> Exemplos
>>>- **Endereço de Rede** -> 122.0.0.0
>>>- **Endereço Broadcast** -> 122.255.255.255
>>>- **Gateway End. Rede** ->122.0.0.1
>>>- **Gateway End. Broadcast** -> 122.255.255.254
> ---
>>[!NOTE]
>> OBS: Os hosts 0 e 255 são reservados, sendo o 0 para a rede e o 255 para o broadcast, não sendo possível hostear máquinas com IPs nessa numeração.
>
	