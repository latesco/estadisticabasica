# Modelo Linea General
## Regresión Líneal Multiple

A partir de un conjunto de  <i>k</i> variables: 
$x_1, x_2, ..., x_k$, con alguna influencia sobre sobre la variable
respuesta $Y$, se supone un modelo, según el cual, la <i>i_ésima</i> 
observación es descrita por::

$$Y_i=\beta_0+\beta_1 x_{i1}+\beta_2 x_{i2}+...+\beta_k x_{kn}+ \epsilon_i$$
donde $i=1, 2, ..., n$

Las variables $x_1, x_2, ..., x_k$,, son un conjunto de valores fijos,
$\epsilon_i$ es el error aleatorio no observable asociado con $Y_i$ y
$\beta_0, \beta_1, \beta_2, ..., \beta_k$, es decir, $m=k+1$
parámetros lineales desconocidos.

La ecuación arriba descrita recibe por nombre <i>modelo lineal
general</i> y dá origen a lo que se conoce como <i>regresión 
lineal múltiple</i>.

Según sea el diseño de recolección de datos; las observaciones
$Y_i$ son variables aleatorias independientes, normalmente 
distribuidas con:

$$E(Y_i)=\beta_0+\beta_1 x_{i1}+...+\beta_k x_{ik},$$

$$Var(Y_i)=\sigma^2;\;\;\;i=1, 2, ..., n$$

Sobre la base de este supuesto, las distribución de los errores es:


$$\epsilon_i \sim N(0, \sigma^2)$$

Esto es, los errores pertenecen a una distribución normal, con media
cero y varianza constante $\sigma^2$. Este modelo representa un
hiperplano, donde el parametro $\beta_0$ es el valor de respuesta
media cuando todas las variables independientes tienen valor cero.

El paŕámetro $\beta_j$ ($j=1, 2, ..., k$) es
 el efecto parcial de $x_j$ sobre la respuesta $Y$; en otras
palabras, es el cambio en la respuesta promedio para un cambio de una unidad en la 
correspondiente variable de predicción $x_j$, manteniendo las 
demás variables de predicción fijas.

### Coeficientes

A partir de una muestra aleatoria de observaciones $Y_1, Y_2, ...
Y_n$, que son respuestas a  $x_{11}, x_{12}, ..., x_{1k}, x_{21}, x_{22}, ..x_{2k}, ...
x_{n1}, x_{n2}, ...$ 
$x_{n1}, x_{n2}, ...., x_{nk}$, respectivamente, se tendrán las
siguientes ecuaciones:

$$\begin{matrix}
Y_1=\beta_0+\beta_1 x_{11} +\beta_2 x_{12}+...+\beta_k x_{1k} + \epsilon_i\\
Y_2=\beta_0+\beta_1 x_{21} +\beta_2 x_{22}+...+\beta_k x_{2k} + \epsilon_i\\
\vdots\\
Y_n=\beta_0+\beta_1 x_{n1} +\beta_2 x_{n2}+...+\beta_k x_{nk} + \epsilon_i
\end{matrix}
$$

Por mayor comodidad, estas ecuaciones usualmente se expresan  en términos 
matriciales:

$$Y=X\beta+\epsilon$$

Donde:

$$Y=\begin{bmatrix} Y_1\\ Y_2\\ \vdots\\Y_n\end{bmatrix},\;\;
X=\begin{bmatrix} 1 & x_{11}& x_{12}&...&x_{1k} \\ 
1 & x_{21} & x_{22}&...&x_{2k} \\ 
\vdots & \vdots &\vdots&...&\vdots\\
1 & x_{n1} & x_{n2}&...&x_{nk} \end{bmatrix},\;\;
\beta=\begin{bmatrix}
\beta_0\\ \beta_1\\ \vdots\\ \beta_k
\end{bmatrix},\;\;\epsilon=\begin{bmatrix}\epsilon_1\\
\epsilon_2\\
\vdots\\
\epsilon_n
\end{bmatrix}
$$

En el contexto de la regresión múltiple, $X$ es una matrix de 
dimensiones <i>nxm</i>, para las variables de
predicción; $\beta$ es un vector de parámetros desconocidos 
de <i>kx1</i>, mientras que $Y$ y $\epsilon$ son vectores <i>nx1</i> 
que contienen la variable respuesta y los errores.
 
Si se cumplen los supuestos de los <i>Mínimos Cuadrados</I>,
las distribuciones de $Y$  y $\epsilon$, son:

$$Y \sim N(X\beta, \sigma^2I)$$
$$\epsilon \sim N(0, \sigma^2I)$$

Donde:

$$Var(Y)=Var(\epsilon)=\sigma^2I$$

Lo que indica que $Y$ y $\epsilon$, son vectores de variables 
aleatorias independientes normalmente distribuidas.

#### Ecuaciones Normales

$$(X'X)B=X'Y$$

SIendo $X$, una matriz de <i>nxk</i>, entonces tomando 
en cuenta sus dimensiones, la expresión sería:


$$(X_{(kxn)}^{'} X_{(nxk)})B_{(kx1)}=X_{(kxn)}^{'} Y_{(nx1)}$$

El producto matricial $(X'X)$ genera una matriz cuadrada
($(X'X)_{(kxk)}$) de dimensiones <i>kxk</i>, 
es decir tiene inversa, y la solución para $B$ es:

$$B=(X'X)^{-1}X'Y$$

Y la ecuación estimada de regresión:


$$\hat{Y}=XB$$

El vector $\hat{Y}$ (<i>nx1</i> ) contiene los valores 
estimados para la respuesta promedio corrrespondiente a las 
<i>n</i> observaciones presentes en las variables 
de predicción.

- Cada coeficiente $B_j$ tiene distribución normal con media 
$E(B_j)=\beta_j;\;\;\;j=0, 1, 2, ..., k$ y varianza $Var(B_j)=c(j + 1)\sigma^2,\;\;
j=0, 1, 2, ...,k$, donde las  $c(j + 1)$ es el elemento de 
la  diagonal $(j + 1)$ de  $(X'X)^{-1}$

- La $Cov(B_i, B_j)=c(i + 1)(c + j)\sigma^2,\;\;i \neq j = 0, 1, 2, ...k$,
donde $c(i + 1)(j + 1)$ es el elemento de $(X'X)^{-1}$ localizado
en la fila $(i + 1)$ y la columna $(j + 1)$, para $i \neq j$.

Un estimador insesgado de la varianza del error es:


$$s^2=\frac{Y'Y - B'X'Y}{{n - k - 1}}$$

Donde el numerador es la suma de los cuadrados de los 
residuos. El denominador es igual al número de observaciones
menos el número de parámetros del modelo.

Un estimador de la varianza para $B_j$ es:



$$S^2(B_j)=c(j + 1)S^2$$

La siguiente expresión representa una variable aleatoria
t de <i>Student</i>, con $n - k - 1$ grados de libertad:



$$\frac{(B_j - \beta_j)}{{S(B_j)}}$$

Y un intervalo de confianza del $100(1 - \alpha )\% $ para el 
parámetro $\beta_j$ es.




$$b_j \pm t_{(1-\alpha)/2, (n-k-1)}S(B_j), \;\;\;j=0, 1, 2, ..., k$$

Para probar una hipótesis nula de la forma.


$$H_0:\beta_j=0$$

Se utiliza la t de <i>Student</i>:


$$T=\frac{B_j}{{S(B_j)}}, \;\;\;j=0, 1, 2, ..., k$$

Con $n - k - 1$ grados de libertad.

La distribución <i>Fisher (F)</i> se utiliza para los contrastes
 del tipo <i>bondad del ajuste</i>, para probar
si todos los parámetros son cero, exceptuando al intercepto:


$$H_0:\beta_1=\beta_2=... =\beta_k$$

<p style="text-align:center">vs</p>

$$H_1:\beta_j \neq 0,\;para\;algun\;j=1, 2, ..., k$$ 

El estadístico de contraste sera, el cociente entre el cuadrado
medio de la regresión entre el cuadrado medio del error:

$$F=\frac{CMR}{{CME}}=\frac{\frac{SCE}{{k}}}{{\frac{SCR}{{n-k-1}}}}$$

Siendo: 
STC: la sumatoria total de cuadrados. 


$$STC=\sum_{i=1}^n(y_i-\bar{y})^2$$

SCE. Sumatoria de cuadrados del Error


$$SCE=\sum_{i=1}^2(y_i -\hat{y})^2$$

SCR: Sumatoria de cuadrados de la regresión.


$$SCR=\sum_{i=1}^n (\hat{y} - \bar{y})^2$$

Además: $SCT=SCE+SCR$


La proporción de variación total de las observaciones con 
respecto a su media, atribuible a la ecuación de regresión 
estimada; es decir, el coeficiente de determinación.


$$R^2=\frac{SCR}{{STC}}=1 - \frac{SCE}{{STC}}$$














