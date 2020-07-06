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

- Fonte AC de frequência 60Hz e tensão nominal(Vrms) de 127V, sendo a tensão de pico 127*√2 ≃ 180V;

- Transformador (Trafo) com a VRMS primária de 127V e secundário de 12V, utilizado para a transformação de tensão, reduzindo a amplitude da onda;

- Ponte de diodos completa, composta por 4 diodos, utilizada para retificação (conversão de CA para CC); 

- Capacitor, utilizado para a filtragem (redução de ripple);

- Resistor + diodo zener, o resistor é utilizado para limitar a corrente que chega ao zener, de acordo com a Imax do datasheet. São utilizados para a regulação de tensão;

- Potenciômetro + resistor, o resistor é utilizado para limitar a corrente do ramo caso o potenciômetro esteja com resistência nula. São utilizados para variar a tensão na carga;

- Transistor bipolar NPN, é utilizado para, a partir de uma pequena corrente de base, controlar a corrente que chega a carga.

## Escolha dos Componentes

- Para escolher a fonte, utilizamos a tensão que chega às residências, pois o objetivo do projeto é justamente fazer uma fonte que seja de fácil uso;

- Para escolher o transformador, consideramos que ele aguenta 127V no primário, tendo uma saída no secundário de no mínimo 12V, que pode ser adquirido ao utilizar o tap central do trafo escolhido. Além disso, o transformador deve ser capaz de aguentar a corrente do circuito, que é igual a 100mA;

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

![Projeto da fonte feito no EAGLE](https://github.com/WictorDalbosco/Fonte-de-Tensao/blob/master/Imagens%20DataSheets/circuito-eagle.PNG)
![Circuito projetado no EAGLE](https://github.com/WictorDalbosco/Fonte-de-Tensao/blob/master/Imagens%20DataSheets/fonte-esquemático.PNG)

## Slides sobre o projeto
[Ir para os Slides](https://github.com/WictorDalbosco/Fonte-de-Tensao/blob/master/Eletrônica-para-computação.pdf)



