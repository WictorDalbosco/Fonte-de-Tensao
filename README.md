# Fonte-de-Tensao
Projeto da disciplina SSC0180 ([Eletrônica para Computação](https://uspdigital.usp.br/jupiterweb/obterDisciplina?sgldis=SSC0180&codcur=55041&codhab=0)) que visa simular uma fonte de tensão nas especificações recomendadas pelo professor Eduardo Simões

## Especificações: 
A partir da tensão de 127V/220V vinda da tomada, desenvolver uma  fonte que modulariza a corrente alternada (CA) em uma corrente contínua (CC) com saída ajustável de 3V a 12V. Desta forma fornecendo uma capacidade de 100mA.

## Componentes que irão ser utilizados:

|Componente|Especificação|Valor|
|---|---|---|
|Transformador (Trafo)|127 / 24V|[R$24,99](https://produto.mercadolivre.com.br/MLB-1299130767-transformador-1212v-1a-trafo-bivolt-_JM?matt_tool=82322591&matt_word&gclid=EAIaIQobChMI8srS-8u46gIVBg-RCh0u1QKkEAQYASABEgJmHfD_BwE&quantity=1)|
|4 Diodos (Ponte retificadora)|1N4007|[R$0,25](https://www.baudaeletronica.com.br/diodo-1n4007.html)|
|Capacitor Eletrolítico|470 μF 50V|[R$0,33](https://www.baudaeletronica.com.br/capacitor-eletrolitico-470uf-25v.html)|
|Diodo de Zener|1N4743A 13V|[R$0,20](https://www.baudaeletronica.com.br/diodo-zener-1n4743-13v-1w.html)|
|Potenciômetro Rotativo|5kΩ|[R$1,09](https://www.baudaeletronica.com.br/potenciometro-linear-de-5k-5000.html)|
|Transistor NPN|BC337|[R$0,17](https://www.baudaeletronica.com.br/transistor-npn-bc337.html)|
|Resistor|470Ω|[R$0,08](https://www.baudaeletronica.com.br/resistor-470r-5-1-4w.html)|
|Resistor|1kΩ|[R$0.08](https://www.baudaeletronica.com.br/resistor-1k-5-1-4w.html)|
|Resistor|2kΩ|[R$0,08](https://www.baudaeletronica.com.br/resistor-2k-5-1-4w.html)|


## Os componentes

- Fonte AC de frequência 60Hz e tensão nominal(VRMS) de 127V, sendo a tensão de pico 127*√2 ≃ 180V;

- Transformador (Trafo) com a VRMS primária de 127V e secundário de 12V, utilizado para a transformação de tensão, reduzindo a amplitude da onda;

- Ponte de diodos completa, composta por 4 diodos, utilizada para retificação (conversão de CA para CC); 

- Capacitor, utilizado para a filtragem (redução de ripple);

- Resistor + diodo zener, o resistor é utilizado para limitar a corrente que chega ao zener, de acordo com a Imax do datasheet. São utilizados para a regulação de tensão;

- Potenciômetro + resistor, o resistor é utilizado para limitar a corrente do ramo caso o potenciômetro esteja com resistência nula. São utilizados para variar a tensão na carga;

- Transistor bipolar NPN, é utilizado para, a partir de uma pequena corrente de base, controlar a corrente que chega a carga.

## Escolha dos Componentes

- Para escolher a fonte, utilizamos a tensão que chega às residências, pois o objetivo do projeto é justamente fazer uma fonte que seja de fácil uso;

- Para escolher o transformador, consideramos que ele aguenta 127V no primário, tendo uma saída no secundário de no mínimo 13V, que pode ser adquirido ao utilizar o tap central do trafo escolhido. Além disso, o transformador deve ser capaz de aguentar a corrente do circuito, que é igual a 100mA;

- Para escolher os diodos, checamos o datasheet:
![](https://github.com/WictorDalbosco/Fonte-de-Tensao/blob/master/Imagens%20DataSheets/DataSheetDiode.png)

- Para escolher o capacitor, levamos em consideração os valores padrão disponíveis no mercado e que geram uma redução de ripple aceitável para o projeto;

- Para escolher o diodo zener, checamos o datasheet:
![](https://github.com/WictorDalbosco/Fonte-de-Tensao/blob/master/Imagens%20DataSheets/DataSheetZenerNovo.png)

Como a corrente mínima é igual a 19mA e a tensão que chega no circuito é cerca de 18V e a de saída do zener é 13V, deve ter uma queda de 5V no resistor. Colocando um resistor de 470 ohms, facilmente encontrado no mercado, a corrente do zener foi menor que 19mA e atingiu-se o valor final desejado da fonte.

- Para escolher o potenciômetro de 10k e o resistor de 2k, escolhemos valores facilmente encontrados no mercado e que possibilitam atingir o valor desejado na saída da fonte;

- Para escolher o transistor, checamos o datasheet:
![](https://github.com/WictorDalbosco/Fonte-de-Tensao/blob/master/Imagens%20DataSheets/DataSheetTransistor.png)

## Circuito no Eagle


### Projeto esquemático
![Circuito projetado no EAGLE](https://github.com/WictorDalbosco/Fonte-de-Tensao/blob/master/Imagens%20DataSheets/Fonte-esquemático.PNG)

### Projeto do PCB
![Projeto da fonte feito no EAGLE](https://github.com/WictorDalbosco/Fonte-de-Tensao/blob/master/Imagens%20DataSheets/Circuito-EAGLE.PNG)

## Slides sobre o projeto
[Ir para os Slides](https://github.com/WictorDalbosco/Fonte-de-Tensao/blob/master/Eletrônica-para-computação.pdf)

## Video do projeto
[Ir para a apresentação do projeto](https://youtu.be/R_1jAGBPNy4)

## Circuito no falstad

[Simulação do circuito](http://www.falstad.com/circuit/circuitjs.html?cct=$+1+0.000019999999999999998+7.943983955226134+50+5+48%0Av+-96+336+-96+48+0+1+60+127+0+0+0.5%0Aw+96+48+224+48+0%0Ad+224+64+288+128+3+default%0Ad+224+192+288+128+3+default%0Ad+160+128+224+64+3+default%0Ad+160+128+224+192+3+default%0Aw+224+192+224+288+0%0Aw+224+336+96+336+0%0Aw+160+128+160+272+0%0Ac+320+128+320+400+0+0.00047000000000000004+18.632014244246466%0Ar+656+256+656+400+0+120%0Ax+668+305+702+308+4+16+load%0Aw+-96+48+-32+48+0%0Aw+-16+176+-16+48+0%0Aw+-16+48+-32+48+0%0Aw+-16+240+-16+336+0%0Aw+-96+336+-16+336+0%0Aw+64+176+64+48+0%0Aw+64+240+64+336+0%0Aw+64+336+96+336+0%0Aw+64+48+96+48+0%0A34+zvoltage%5Cq12+0+1.7143528192810002e-7+0+2+13%0Az+432+400+432+208+2+zvoltage%5Cq12%0Ag+64+336+64+368+0%0Ag+-96+336+-96+368+0%0AT+-16+176+64+240+0+4+0.16+-0.48196031361902125+-1.6737479457962223e-14+0.999%0Ar+432+128+432+208+0+1000%0Aw+224+48+224+64+0%0Aw+160+272+160+400+0%0Aw+224+288+224+336+0%0Ar+528+400+528+304+0+5200%0Aw+352+400+320+400+0%0Aw+160+400+320+400+0%0Aw+544+400+528+400+0%0Aw+320+128+288+128+0%0A174+528+304+544+224+1+10000+0.005+Resistance%0At+592+240+656+240+0+1+-14.984407632320714+0.6782965312331225+100%0Aw+352+400+432+400+0%0Aw+480+400+528+400+0%0Aw+480+128+528+128+0%0Aw+432+128+480+128+0%0Aw+544+256+592+256+0%0Aw+592+256+592+240+0%0Aw+432+400+480+400+0%0Aw+544+400+560+400+0%0A370+656+400+560+400+1+0%0Ap+720+256+720+400+1+0%0Aw+656+256+720+256+0%0Aw+656+400+720+400+0%0Aw+528+208+432+208+0%0Aw+432+128+320+128+0%0Aw+528+128+656+128+0%0Aw+656+128+656+224+0%0Ao+0+8+0+4098+160+0.00009765625+0+2+0+3%0Ao+10+8+0+4099+5+0.025+1+2+10+3%0A)



