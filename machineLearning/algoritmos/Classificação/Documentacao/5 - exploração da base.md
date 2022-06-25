# Exploração da base de dados

## importação da base

- Antes de realizar a importação, é necessário o upload da base nos arquivos do projeto do google colab
- após o upload, ai sim realizamos a importação

```python
base_credit = pd.read_csv('/content/credit_data.csv')
```

## visualização da base

- digitando `base_credit`, exibimos os dados em forma de dataframe, onde podemos ver a relação do default, que são os clientes que pagaram ou não pagaram o empréstimo(loan), 0 para quem pagou e 1 para quem não pagou
- com o `.head()`, exibimos apenas os 5 primeiros, ou da cabeça do dataframe, porém podemos definir quantos queremos visualizar, como nesse caso, `base_credit.head(10)`
- com o `.tail()`, podemos visualizar os 5 últimos registros do dataframe, seguindo o mesmo caso do head, podemos definir quantos queremos visualizar
- `base_credit.describe()`, é responsável por exibir algumas relações dos registros, como:
  - count, o número total de elementos para cada coluna
  - mean, a média para cada coluna
  - std, o desvio padrão para cada coluna
  - min, o menor valor para cada coluna
  - max, o maior valor para cada coluna
- Visualizando registros com base em atributos específicos
  - Visualizamos que o maior income(renda anual), era de 69995.685578, e gostariamos de ter todos os dados sobre esse registro, saber quem é o cliente, e para isso, usamos, `base_credit[base_credit['income'] >= 69995.685578]`, definimos qual coluna queremos pegar o atributo desejado e assim exibimos todo o registro
  - O mesmo foi feito para o menor valor de loan(empréstimo), `base_credit[base_credit['loan'] <= 1.377630]`

```python
base_credit #defaulted
base_credit.head(10)
base_credit.tail(8)
base_credit.describe()
base_credit[base_credit['income'] >= 69995.685578]
base_credit[base_credit['loan'] <= 1.377630]
```
