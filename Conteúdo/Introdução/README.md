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
