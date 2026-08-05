# Projeto e Análise de Algoritmos (PAA)

## Introdução

A disciplina de PAA é de extrema importância no que se refere à estratégia para resolver problemas computacionais, procurando soluções eficientes e tratando problemas complexos.
Desse modo, é possível subdividir a matéria em três partes, sendo elas:

- **Análise**: Verificação do custo computacional de uma solução, sendo o custo relacionado ao tempo de execução do algoritmo. Esta etapa é utilizada para identificar problemas difíceis.

- **Tratabilidade**: Utilização de estratégias para atacar problemas difíceis, podendo ser gulosa, dividir para conquistar e etc.

- **Projeto**: Aplicações da análise e da tratabilidade para os problemas computacionais.

Inicialmente, cerca de um terço da disciplina é utilizado para estudar análise e tratabilidade e os outros dois terços ficam para projeto.

---

## Discussão sobre a Análise

O processo de análise de um algoritmo envolve encontrar sua complexidade através de funções matemáticas. Nesse contexto, existem problemas que podem ter complexidade constante, linear, exponencial e entre outros. 
Além disso, é preferível evitar soluções que sejam exponenciais devido ao fenômeno da explosão de respostas - que é uma característica da função exponencial. Nesse cenário, algumas soluções exigem o conjunto potência do espaço de 
soluções (incluindo o conjunto vazio), e, quando algum problema precisa analisar todos elementos do conjunto potência, tem-se um problema difícil.

Dessa forma, existem notações que expressam a complexidade, como por exemplo a big O, que é representada assim: O(g(n)). Nesse sentido, é possível afirmar que uma função f(n) = O(g(n)) pela definição:

$$\exists\ c > 0,\ n_0 \ge 0 , f(n) \le c \cdot g(n), \forall\ n \ge n_0\ $$

Com isso, para determinar se um algoritmo faz parte de determinada complexidade, basta analisar sua função de custo e aplicar a definição, além disso, após a aplicação, é necessário verificar se o limite da constante c resulta em um valor
constante ou se resulta em infinito, tem-se o exemplo abaixo.

---

### Exemplo: Prove que $2n + 4$ = O(n)

Para isto, basta pegar e substituir o O(n) pela constante c multiplicado pela função de dentro do O, no caso o n. Depois disso, isole a constante e aplique os limites para infinito.

$$2n + 4 \le c \cdot n$$

$$c \ge \frac{2n + 4}{n}$$

$$c \ge \frac{2n}{n} + \frac{4}{n}$$

$$c \ge 2 + \frac{4}{n}$$

$$\lim_{n \to \infty}\left(2 + \frac{4}{n}\right) = 2 \text{   } \therefore\  2n + 4 = O(n)$$


### Exemplo: Prove que $n^2 + 100$ O(1)

Neste caso, a afirmação é incorreta e de certo modo é trivial, para provar pela definição faça:

$$n^2 + 100 \le c \cdot n$$

$$c \ge \frac{n^2 + 100}{n}$$

$$c \ge \frac{n^2}{n} + \frac{100}{n}$$

$$c \ge n + \frac{100}{n}$$

$$\lim_{n \to \infty}\left(n + \frac{100}{n}\right) = \infty \text{   } \therefore\  n^2 + 100 \neq O(n)$$

---

### Exemplo: Seja $$f_1(n) = O(g_1(n))$$ e $$f_2(n) = O(g_2(n))$$, mostre que

<br>

- **$$f_1(n) + f_2(n) = O(\max(g_1(n), g_2(n)))$$**

De acordo com a definição, para que uma função qualquer pertença a uma notação $$O(g(n))$$, é necessário que exista uma constante C maior que zero e que 
exista um $$n_0$$ que seja maior que zero - para valores limiares de comparação e para todo $$n$$ maior que $$n_0$$. Desse modo, ao somar duas funções quaisquer $$f_1(n) + f_2(n)$$, tem-se:

  $$f_1(n) + f_2(n) \leq C_1 * g_1(n) + C_2 * g_2(n)$$

Para além disso, dado que no enunciado $$g(n)$$ é o máximo entre as funções $$g$$ de cada função $$f$$, é possível transformar os termos $$g_1(n) \text{ e } g_2(n)$$ em um termo genérico representado
por $$K(n)$$. Com isso, ao colocar esse termo em evidência, tem-se:

  $$f_1(n) + f_2(n) \leq  (C_1 + C_2) * K(n)$$

Prosseguindo, a soma de duas constantes representa uma constante, logo, transformando $$C_1 \text{ e } C_2$$ em $$C_3$$ determina que existe uma constante $$C_3$$ maior que zero, o que é justamente o que a definição formal diz.
Além disso, tem-se:

  $$f_1(n) + f_2(n) \leq  C_3 * K(n) \text{, } \forall\ n \ge n_1 + n_2$$

Por fim, como $$n_1 \text{ e } n_2$$ são constantes, seguindo o mesmo raciocínio, é possível transformar essas constantes em uma única constante $$n_3$$, o que prova que existe, além de um C maior que zero, um $$n_3$$ maior que zero,
portanto satisfazendo a existência para a notação big O.

<br>
<br>

- **$$f_1(n) * f_2(n) = O(g_1(n) * g_2(n))$$**

Para este exemplo, o raciocínio permanece o mesmo, basta substituir $$g_1(n) * g_2(n)$$ por uma função genérica $$K(n)$$ e aplicar a definição. Ao final, a multiplicação das constantes $$C_1$$ e $$C_2$$ se tornará $$C_3$$ e isso será feito para todo $$n$$ que seja maior que o produto de $$n_1$$ e $$n_2$$ que, por sua vez, se torna a constante $$n_3$$ comprovando a definição.

---

### Exemplo: Seja $$f(n) = O(g(n)) \text{ e } k > 0$$, prove que $$K*f(n) = O(g(n))$$

Como notado nos exercícios acima, basta aplicar a definição apresentada multiplicando todos os termos por essa constante K, Desse modo, tem-se:
  
  $$f(n) * K \leq  K * C * g(n)$$

Nesse sentido, o produto de $$K$$ por $$C$$ também é uma constante, que se tornará $$C_1$$, logo é possível afirmar também que isto se aplica para todo $$n$$ que seja maior ou igual a $$n_0 * K$$, o que é apresentado pela definição formal.
  