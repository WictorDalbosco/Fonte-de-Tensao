# Fonte-de-Tensao
Projeto da disciplina SSC0180 ([Eletrônica para Computação](https://uspdigital.usp.br/jupiterweb/obterDisciplina?sgldis=SSC0180&codcur=55041&codhab=0)) que visa simular uma fonte de tensão nas especificações recomendadas pelo professor Eduardo Simões

## Especificações: 
A partir da tensão de 127V/220V vinda da tomada, desenvolver uma  fonte que modulariza a corrente alternada (CA) em uma corrente contínua (CC) com saída ajustável de 3V a 12V. Desta forma fornecendo uma capacidade de 100mA.

## Componentes que irão ser utilizados:

|Componente|Especificação|Valor|
|---|---|---|
|Tranformador Trafo 12+12V |127 / 24V|[R$24,99](https://produto.mercadolivre.com.br/MLB-1299130767-transformador-1212v-1a-trafo-bivolt-_JM?matt_tool=82322591&matt_word&gclid=EAIaIQobChMI8srS-8u46gIVBg-RCh0u1QKkEAQYASABEgJmHfD_BwE&quantity=1)|
|4 Diodos (Ponte retificadora)|1N4007|[R$0,25](https://www.baudaeletronica.com.br/diodo-1n4007.html)|
|Capacitor|470 μF 50V|[R$0,33](https://www.baudaeletronica.com.br/capacitor-eletrolitico-470uf-25v.html)|
|Diodo de Zener|1N4745A 16V|[R$0,25](https://www.baudaeletronica.com.br/diodo-zener-1n4745a-16v-1w.html)|
|Potenciômetro Rotativo|5kΩ|[R$1,09](https://www.baudaeletronica.com.br/potenciometro-linear-de-5k-5000.html)|
|Transistor NPN|BC337|[R$0,17](https://www.baudaeletronica.com.br/transistor-npn-bc337.html)|
|Resistor|470Ω|[R$0,08](https://www.baudaeletronica.com.br/resistor-470r-5-1-4w.html)|
|Resistor|1kΩ|[R$0.08](https://www.baudaeletronica.com.br/resistor-1k-5-1-4w.html)|
|Resistor|2kΩ|[0,08](https://www.baudaeletronica.com.br/resistor-2k-5-1-4w.html)|


## Os componentes

- Fonte AC de frequência 60Hz e tensão nominal(Vrms) de 127V, sendo a tensão de pico 127*√2 ≃ 180V;

- Transformador (Trafo) com a VRMS primária de 127V e secundário de 12V, utilizado para a transformação de tensão, reduzindo a amplitude da onda;

- Ponte de diodos completa, composta por 4 diodos, utilizada para retificação (conversão de CA para CC); 

- Capacitor, utilizado para a filtragem (redução de ripple);

- Resistor + diodo zener, o resistor é utilizado para limitar a corrente que chega ao zener, de acordo com a Imax do datasheet. São utilizados para a regulação de tensão;

- Potenciômetro + resistor, o resistor é utilizado para limitar a corrente do ramo caso o potenciômetro esteja com resistência nula. São utilizados para variar a tensão na carga;

- Transistor bipolar NPN, é utilizado para, a partir de uma pequena corrente de base, controlar a corrente que chega a carga;


