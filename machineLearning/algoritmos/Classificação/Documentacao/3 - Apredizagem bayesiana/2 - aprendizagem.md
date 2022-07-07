# Aprendizagem

## Como que a tabela é contruida

![tabela-construida](img/tab-construida.png)

- O primeiro passo que precisamos fazer é a contagem do risco
  - colocamos na primeira coluna o que será nossa classe/target
  - as próximas colunas, separamos os atributos
    - História do crédito
      - Separamos em:
        - Boa
        - Desconhecia
        - Ruim
  - precisamos somar, quantas vezes temos o risco de crédito alto
    - Fazemos a contagem
![contagem-alto](img/contagem-alto.png)
         6/14 - risco alto
    - Contagem risco moderado
![contagem-alto](img/contagem-moderado.png)
         3/14 - risco moderado
    - contagem risco baixo
![contagem-alto](img/contagem-baixo.png)
         5/14 - risco baixo
  - Agora precisamos fazer a contagem da história do crédito, se é boa, desconhecida ou ruim
    - Boa $\rightarrow$ 5
    - desconhecida $\rightarrow$ 5
    - ruim $\rightarrow$ 4
    ![historia do crédito](img/historia-credito-cont.png)
  - Agora o que precisamos fazer é intercalar os valores da história do crédito com os riscos, pegaremos as intersecções
    - História boa + risco alto $\rightarrow$ 1/6
    ![boa-alto](img/boa-alto.png)
      > 1 é a quantidade de história boa que temos para o total de 6 riscos altos
    - História boa + risco moderado $\rightarrow$ 1/3
    ![boa-moderado](img/boa-moderado.png)
      > Dos 3 registros do risco moderado, 1 possui história do crédito boa
    - História boa + risco baixo $\rightarrow$ 3/5
    ![boa-baixo](img/boa-baixo.png)
      > Dos 5 registros do risco baixo, 3 possui história do crédito boa
    > Feito isso, fazemos a soma de $1 + 1 + 3$, onde tem que dar o valor total de história boa, no caso 5
    - História desconhecida + risco alto $\rightarrow$ 2/6
    ![desconhecida-alto](img/desconhecida-alto.png)
      > Dos 6 registros de risco alto, 2 deles são desconhecidos
    - História desconhecida + risco moderado
    $\rightarrow$ 1/3
    ![desconhecida-moderado](img/desconhecida-moderado.png)
      > Dos 3 registros de risco moderado, 1 deles são desconhecidos
    - História desconhecida + risco baixo
    $\rightarrow$ 2/5
    ![desconhecida-baixo](img/desconhecida-baixo.png)
      > Dos 5 registros de risco baixo, 2 deles são desconhecidos
    > Fazendo o somatório de $2+1+2$, onde tem que ser igual os valor de desconhecida, no caso igual a 5
    - História ruim + risco alto $\rightarrow$ 2/6
    ![ruim-alto](img/ruim-alto.png)
      > Note que somados as histórias boa, desconhecida e ruim, para o risco alto, temos o valor 6, o equivalente a quantidade de registros de risco alto. Dos 6 registros de risco alto, 3 deles são ruim
    - História ruim + risco moderado $\rightarrow$ 1/3
    ![ruim-moderado](img/ruim-moderado.png)
      > Dos 3 registros de risco moderado, 1 deles são ruim
    - História ruim + risco baixo $\rightarrow$ 0/5
    ![ruim-baixo](img/ruim-baixo.png)
      > Dos 5 registros de risco baixo, 0 deles são ruim

  - Agora vamos para o segundo atributo, a dívida, sendo ela, alta e baixa
    - Calculando primeiramento as dividas, temos 7 em altas e 7 em baixas
    ![dividas-count](img/divida-count.png)
    - Dívida alta + risco alto $\rightarrow$ 4/6
    ![alta-alto](img/alta-alto.png)
    - Dívida alta + risco moderado $\rightarrow$ 1/3
    ![alta-moderado](img/alta-moderado.png)
    - Dívida alta + risco baixo $\rightarrow$ 2/5
    ![alta-baixo](img/alta-baixo.png)
    > Somando o $4+1+2$ temos 7, valor essse referente ao número de registros de dívidas altas
    - Agora vamos pegar as dívidas baixas
    - Dívida baixa + risco alto $\rightarrow$ 2/6
    ![baixa-alto](img/baixa-alto.png)
    > somando o 4 com o 2 do atributo de dívida, tem que dar 6
    - Dívida baixa + risco moderado $\rightarrow$ 2/3
    ![baixa-moderado](img/baixa-moderado.png)
    > somando dívida alta e baixa, tem que dar 3 que corresponde ao npumero de registros de risco moderado
    - Dívida baixa + risco baixo $\rightarrow$ 3/5
    ![baixa-baixo](img/baixa-baixo.png)
    > somando dívida alta e baixa, totaliza 5. E somando o valores do atributo dívida baixa, totaliza 7
  - Agora vamos para o terceiro atributo, as garantias, sendo ela, nenhuma e adequada
    - Calculando primeiramento as garantias, temos 11 em nenhuma e 3 em adequanda
    ![count-garantias](img/count-garantia.png)
    - Garantia nenhuma + risco alto $\rightarrow$ 6/6
    ![nenhuma-alto](img/nenhuma-alto.png)
    - Garantia nenhuma + risco moderado $\rightarrow$ 2/3
    ![nenhuma-moderado](img/nenhuma-moderado.png)
    - Garantia nenhuma + risco baixo $\rightarrow$ 3/5
    ![nenhuma-baixo](img/nenhuma-baixo.png)
    > Realizamos o somatório de 6, 2 e 3 e tenha q dar o número de registros de garantia nenhuma
    - Garantia adequada + risco alto $\rightarrow$ 0/6
    ![adequada-alto](img/adequada-alto.png)
    - Garantia adequada + risco moderado $\rightarrow$ 1/3
    ![adequada-moderado](img/adequada-moderado.png)
    - Garantia adequada + risco baixo $\rightarrow$ 2/5
    ![adequada-baixo](img/adequada-baixo.png)
    > realizando o somatório temos o mesmo valor 3 do atributo agarantias adequada
  - Agora vamos para o quarto atributo, a renda anual, sendo ela, <15, >=15 <=35 e >35
    - Calculando primeiramento a renda anual, temos 3 para <15, 4 para >=15 <=35 e 7 para >35
    ![count-renda](img/count-renda.png)
    - renda < 15 + risco alto $\rightarrow$ 3/6
    ![renda-alto](img/renda1-alto.png)
    > note que para renda inferior a 15 mil anual, todos os registros atribuidos a essa renda, se encontram em risco alto, indicando que tanto risco moderado quanto baixo, não possuem rendas inferiores a 15 mil
    - renda < 15 + risco moderado e baixo respectivamente $\rightarrow$ 0/3 0/5
    ![renda-moderado e baixo](img/renda1-mode-baixo.png)
    - renda >=15 <=35 + risco alto $\rightarrow$ 2/6
    ![renda-alto](img/renda2-alto.png)
    - renda >=15 <=35 + risco moderado $\rightarrow$ 2/3
    ![renda-moderado](img/renda2-moderado.png)
    > perceba que atingimos o valor de atributos para essa faixa de renda, nesse caso o risco baixo não possui nenhum registro nessa faixa de renda
    - renda >=15 <=35 + risco baixo $\rightarrow$ 0/5
    ![renda-baixo](img/renda2-baixo.png)
    - renda >35 + risco alto $\rightarrow$ 1/6
    ![renda-alto](img/renda3-alto.png)
    - renda >35 + risco moderado $\rightarrow$ 1/3
    ![renda-moderado](img/renda3-moderado.png)
    - renda >35 + risco baixo $\rightarrow$ 5/5
    ![renda-baixo](img/renda3-baixo.png)

### nossa tabela do naive bayes está pronta

> O que precisa ficar claro é que a aprendizagem de máquina nesse algoritmo é apenas isso, pegar essa tabela original e os dados históricos e ele vai fazer essas estatística básicas para montar a aprendizagem. Básicamente ele vai gerar essa tabela de probabilidade

[Continua](3%20-%20classifica%C3%A7%C3%A3o.md) $\Rightarrow$
