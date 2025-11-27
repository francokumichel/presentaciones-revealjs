# Primer parcial
## Ejercicio 1

Entre los inversores de la bolsa se conoce:

- $𝑃(𝐴)=0.24$
- $𝑃(𝐵)=0.20$
- $𝑃(𝐴∩𝐵)=0.04$

Donde:
- $A$ = “invierte en Activo A”
- $B$ = “invierte en Activo B”

#### (a) ¿A y B son independientes?
Recordemos que dos eventos son independientes si: 
$P(A∩B)=P(A)P(B)$

Comparamos:
$P(A)P(B)=0.24⋅0.20=0.048$
$P(A∩B)=0.04$

Como: $0.048≠0.04$
⇒ A y B no son independientes.
⇒ Invertir en A “afecta” estadísticamente a invertir en B.

#### (b) Probabilidad de que invierta en A o B

$P(A∪B)=P(A)+P(B)−P(A∩B)=0.24+0.20−0.04=0.40$

Resultado: $P(A∪B)=0.40$

#### (c) Si se eligen 10 inversores, probabilidad de que menos de la mitad invierta en A o B

Sea $X$ = número de inversores (entre 10) que invierten en A o B. Considerando que:

- Hay un número fijo de ensayos (10 inversores)
- Cada ensayo tiene dos resultados (invierte/no invierte)
- La probabilidad de éxito es la misma para cada uno ($p=0.40$)
- Los ensayos son independientes

Entonces: $X∼B(n=10,p=0.40)$
Queremos: $P(X<5)=P(X≤4)$
Entonces, aplicando formula de la binomial: 
$P(X≤4)=\sum_{k=0}^{4}\binom{10}{k} 0.4^k 0.6^{10-k} \approx 0.6331$

# Ejercicio 2

Función de densidad: $f(x)=0.5x−1,2≤x≤4$

#### (a) Probabilidad de que un tornillo mida más de 3.5 cm

$P(X>3.5)= \int_{3.5}^{4}
(0.5x−1)dx = [0.25x^2 - x]_{3.5}^{4} = 0−(3.0625−3.5)=0.4375$

#### (b) Esperanza, Varianza y Desvío Estándar
Cálculo esperanza:
$E(X)= \int_{2}^{4}
x(0.5x−1)dx = \int_{2}^{4}(0.5x^2−x)dx = [\frac{1}{6}x^3 - \frac{1}{2}x^2]_{2}^{4} = \frac{10}{3} \approx 3.3333$

Cálculo de $E(X^2)$
$E(X^2)= \int_{2}^{4}
x^2(0.5x−1)dx = \int_{2}^{4}(0.5x^3−x^2)dx = [\frac{1}{8}x^4 - \frac{1}{3}x^3]_{2}^{4} = \frac{34}{3}$

Entonces:
$Var(X) = E(X^2) - [E(X)]^2 = \frac{34}{3} - (\frac{10}{3})^2 = \frac{2}{9}$

$ \sigma_X = \sqrt{Var(X)} = \frac{\sqrt{2}}{3} \approx 0.4714 $

**c) Si estos tornillos se comercializan en cajas de 50 unidades, ¿cuál es la probabilidad de que la longitud promedio de los tornillos de una caja sea de a lo sumo 3.2?**

La media muestral $ \overline{X} $ tiene (aprox) distribución normal:

$ \overline{X} \sim N(\mu = \frac{10}{3}, \sigma_{\overline{X}} = \frac{\sigma_{X}}{\sqrt{50}} = \frac{\sqrt{2/3}}{50} = \frac{1}{5}) $

Queremos $ P(\overline{X} \le 3.2) $. Calculando el estadístico:
$ z = \frac{3.2 - \mu}{\sigma_{\overline{X}}} = \frac{3.2 - \frac{10}{3}}{\frac{1}{15}} = -2$
$ P(\overline{X} \le 3.2) = \Phi(-2) \approx 0.02275 $

## Ejercicio 3

El tiempo (en minutos) entre llamadas a una línea telefónica en una oficina de reclamos sigue la siguiente densidad:

$$f(w)=0.25e^{−0.25w}, \quad w≥0$$

a) Han transcurrido 5 minutos desde la primera llamada sin que haya ocurrido la segunda. ¿Cuál es la probabilidad de que el tiempo total hasta la llegada de la segunda llamada sea superior a 7 minutos?**

b) Si el operador se toma un descanso entre 13:00 y 13:20, ¿cuál es la probabilidad de que se hayan perdido 3 o 4 llamadas?

**Resolución**

La distribución exponencial con parámetro $λ=0.25$ (por minuto), equivalente a media $ 1/λ=4 $ minutos.

a) Utilizo la propiedad de ausencia de memoria para $ W \sim Exp( \lambda ) $

$P(W > 7 | W > 5) = P(W > 2) = e^{-\lambda \cdot 2} = e^{-0.25 \cdot 2} = e^{-0.5} \approx 0.60653066 $

b) Número de llamadas perdidas en 20 minutos: por el proceso de Poisson asociado, la media en $t$ minutos es $λt$. Aquí $λ=0.25$ (por minuto), $t=20$ min $\to$ $λt=5$. Sea $N∼P(5)$:

$P(N=3)+P(N=4) = e^{−5}(\frac{5^3}{3!}​+\frac{5^4}{4!}​) \approx 0.1403739+0.1754674=0.3158413$

## Ejercicio 4

Pesos en gramos: alfajor dulce de leche $X∼N(40,4)$ (varianza $=4⇒σ=2$). Alfajor de fruta $Y∼N(42,6.25)$ (varianza $= 6.25⇒σ=2.5$). Se asume independencia.

a) $P(Y>X)$ (probabilidad de que uno de fruta pese más que uno de dulce de leche).
b) ¿Cuál de los dos tipos es más probable que pese menos de 
39.5 g?
c) Se seleccionan 59 alfajores de dulce de leche y 41 de fruta. Se toma un alfajor al azar de la muestra y se observa que pesa menos de 39.5 g. ¿Cuál es la probabilidad de que sea de dulce de leche?

**Resolución**

a) Defino $ D = Y - X $. Entonces:
$$ D \sim N(\mu_{D} = \mu_{Y} - \mu_{X} = 2, \sigma^{2}_{D} = \sigma^{2}_{Y} + \sigma^{2}_{X} = 6.25 + 4 = 10.25) $$

Calculo $P(D > 0) = 1 - \Phi(\frac{0-2}{\sqrt{10.25}}) = 1 - \Phi(-0.6247) = \Phi(0.6247)  $

Se busca valor en tabla: $ P(X > Y) \approx 0.7339144 $

b) Calculamos $P(X<39.5)$ y $P(Y<39.5)$

- Para $X$: $z = \frac{39.5 - 40}{2} = -0.25 \to P \approx \Phi(-0.25) = 0.4012937 $
- Para $Y$: $z = \frac{39.5 - 42}{2.5} = -1 \to P \approx \Phi(-1) = 0.1586553 $

Por lo tanto, el alfajor de dulce de leche ($X$) es más probable que pese menos de 39.5 g.

c) \(P(DL)=0.59,\ P(F)=0.41\). Además, contamos con las probabilidades de pesar < 39.5 calculadas antes.

\[
P(DL\mid <39.5)=\frac{0.59\cdot 0.40129}{0.59\cdot 0.40129 + 0.41\cdot 0.15865}\approx 0.7845
\]

Por qué Bayes: se quiere la probabilidad posterior de una categoría dada la observación!