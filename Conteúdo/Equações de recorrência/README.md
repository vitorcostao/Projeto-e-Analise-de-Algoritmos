# Projeto e Análise de Algoritmos (PAA)

## Problema abordado

Projete duas funções para resolver a seguinte expressão sendo uma recursiva e outra iterativa, além disso, conte o número de multiplicações

$$f(n) =
\begin{cases}
1, & \text{se } n = 0 \\
n \cdot f(n-1), & \text{se } n > 0
\end{cases}$$

### Resolução 

```
int fat(n)
  if n == 0
     return 1;
  else
      return n * fat(n-1)

int fat(n)
  int resp = 1
  for(i = n; i > 0; i--)
    resp = resp*i
  return resp
```

Para ambos os casos, haverá n multiplicações. Para isso, basta realizar os somatórios devidos para função recursiva e iterativa o que é trivial.

## Faça para ambos os casos 

$$T(n) =
\begin{cases}
1, & \text{se } n = 1 \\
T\left(\frac{n}{2}\right) + 1, & \text{se } n > 1
\end{cases}$$


$$T(n) =
\begin{cases}
2, & \text{se } n \leq 2 \\
T(n-1) + 1, & \text{se } n > 2
\end{cases}$$

### Primeiro caso

Na primeira função, basta utilizar equações de recorrência para resolver as contagens. Nesse caso, é possível perceber que a cada chamada ou iteração, a o termo de parâmetro da função se reduz pela metade,
o que pode ser escrito de forma genérica como $\frac{n}{2^i}$. Prosseguindo, basta igualar este valor ao último termo em que a função será chamada, que é o número dois. Isolando o $i$ e aplicando log tem-se que $i = \log_2(n) - 1$.
Portanto, tem-se:

$$\sum_{i=0}^{\log_2(N)-1} (1) + 1$$
> OBS: O mais um se refere ao último valor do passo base ser um.


### Segundo caso

Para o segundo caso, a ideia é a mesma do primeiro, ou seja, encontrar termo genérico, igualar o último termo em que a função será chamada e isolar o $i$ para encontrar o limite superior. Após isso, basta aplicar o somatório. Desse modo,
o termo genérico é representado por $n - i$, o último termo de chamada da função é três, logo $i = n - 3$. Portanto, tem-se:

$$\sum_{i=0}^{n-3} (1) + 2$$
