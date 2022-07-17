# Aprendizagem I

Vamos aprender como funciona o processo de treinamento ou da geração de uma árvore de decisão, por meio de uma base de dados

> Conforme foi visto [aqui](1.1%20-%20%C3%81rvores%20de%20decis%C3%A3o%20-%20introdu%C3%A7%C3%A3o.md), o objetivo desse algoritmo de árvore de decisão é fazer a leitura de uma base de dados original e gerar uma árvore de decisão, onde se coloca os atributos ordenados por grau de importância. E para classificar um novo registro, será analisado cada um dos atributos e vai seguindo os ramos da árvore de acordo com suas características

---

## Construção da árvore de decisão

Para essa construção, possuimos duas fórmulas matemáticas

- Primeiro temos o cálculo da entropia:

    $Entropy(S) = \sum_{i=1}^{c} -p_i\log_2p_i$

- Segundo temos a fórmula do ganho de informação:

    $Gain(S,A) = Entropy(S) - \sum_{v\epsilon Values(A)} \frac{|S_v|}{|S|}Entropy(S_v)$

> Essa é a abordagem mais comum que se pode encontrar sobre árvore de decisão. Realizar o cálculo dos atributos, então, analisar atributo por atributo, para descobrir qual deles é mais importante, se utilizando das dusa fórmulas

---

### Entropy

Vamos inicialmente realizar um cálculo de entropia, para minha base de dados inteira, note que pegamos apenas a classe, onde temos o risco alto, moderado e baixo

![risco](img/risco.png)

- Risco Alto
  - Vamos então contar quantas fezes aparecem o risco alto

  ![risco-alto](img/risco-alto.png)

  > Temos 6 de 14, 14 é nosso total de registros

- Risco Moderado
  
  ![risco-moderado](img/risco-moderado.png)

  > temos 3 de 14

- Risco Baixo

  ![risco-baixo](img/risco-baixo.png)

  > Temos 5 de 14

---

Realizada a contagem, o que é preciso fazer agora é o cálculo da entropia

$Entropy(S) = \sum_{i=1}^{c} -p_i\log_2p_i$

> Basicamente ele vai medir, o qual desorganizado os dados então na base de dados. E essa utilização desses cálculos vem da [teoria da informação](http://www.esalq.usp.br/lepse/imgs/conteudo_thumb/Entropia--Ganho-de-informa--o-e-Decision-trees.pdf)

- atribuindo os valores na fórmula:

$Entropy(S) = \frac{-6}{14} \cdot \log(\frac{6}{14})_2-\frac{-3}{14}\cdot \log(\frac{3}{14})_2-\frac{-5}{14}\cdot \log(\frac{5}{14})_2 = 1,53$
