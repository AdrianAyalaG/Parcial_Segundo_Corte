10 / 10 / 2024
# Corrección Parcial
Se ha realizado la corrección completa del parcial de Control Digital y Movimiento, abordando de manera integral los principales temas del curso. Esto incluye el uso de métodos algebraicos aplicados a la igualación de modelos, el análisis en frecuencia y análisis de los diagramas de Bode. En cada uno de los puntos propuestos, se desarrolla una solución matemática detallada, presentando cada paso del proceso de manera clara y estructurada garantizando la comprensión de la respuesta planteada.

## Parcial Segundo Corte
1. **(3 puntos)** Se tiene la siguiente planta en tiempo discreto:

$$ G_{(z)} = \frac{1.61x10^{-7}z^{2} + 6.25x10^{-7}z + 1.53x10^{-7}}{z^{3} - 2.87z^{2} + 2.75z - 0.88} $$

Calcule el controlador por igualación de modelo, ubique los polos en lazo cerrado en:

$$P_{1} = -100$$
$$P_{2} = -100$$
$$P_{3} = -100$$
$$P_{4} = -2 + 2.73j$$
$$P_{5} = -2 - 2.73j$$

**Nota:** Solo se aceptan soluciones que muestren todo el procedimiento matemático, que la función de transferencia tenga un polinomio en el numerador y un polinomio en el denominador.

2. **(1 puntos)** Para el diagrama de Bode de la figura indique si el sistema es estable en lazo cerrado o no. Justifique su respuesta.

$${\color{Red} IMAGEN}$$
   
3. **(1 puntos)** El diagrama de Bode de la figura contiene la respuesta de un sistema de red de atraso y con red de atraso. Mida el margen de fase del sistema que ya tiene la red de atraso. Inlcuya el procedimiento matemático para llegar a la respuesta.

$${\color{Red} IMAGEN}$$

## Solución
1. 

$$(z + 100)(z + 100)(z + 100)(z + 2 - 2.73j)(z + 2 + 2.73j)$$
$$(z^{2} + 200z + 10^{4})(z + 100)(z^{2} + 2z {\color{Red} + 2.73j} + 2z + 4  {\color{Blue} + 5.46j} {\color{Red} - 2.73jz} {\color{Blue} - 5.46} + 7.45)$$
$$(z^{3} + 100z^{2} + 200z^{2} + 2x10^{4}z + 10^{6} + 10^{4}z)(z^{2} + 4z + 11.45)$$
$$(z^{3} + 300z^{2} + 3x10^{4}z + 10^{6})(z^{2} + 4z + 11.45)$$
$$z^{5} + {\color{Red} 4z^{4}} + {\color{Blue}11.45z^{3}} + {\color{Red} 300z^{4}} + {\color{Blue}1.2x10^{3}z^{3}} + {\color{Green}3.4x10^{3}z^{2}} + {\color{Blue}3x10^{4}z^{3}} + {\color{Green}12x10^{4}z^{2}} + {\color{Orange} 343.5x10^{3}z}+ {\color{Green}10^{6}z^{2}} + {\color{Orange} 4x10^{6}z} + {\color{Magenta} 11.45x10^{6}}$$
$$z^{5} + {\color{Red}z^{4}(4 + 300)} + {\color{Blue}z^3(11.45 + 1.2x10^{3} + 3x10^{4})} + {\color{Green}z^{2}(3.4x10^{3} + 12x10^{4} + 10^{6})} + {\color{Orange} z(343.5x10^{3} + 4x10^{6})} + {\color{Magenta}11.45x10^{6}}$$
$$z^{5} + 304z^{4} + 31.21x10^{3}z^{3} + 1.12x10^{6}z^{2} + 4.34x10^{6}z + 11.45x10^{6}$$

**Lazo Cerrado obtenido:**

$$G_{o(z)} = \frac{1}{z^{5} + 304z^{4} + 31.21x10^{3}z^{3} + 1.12x10^{6}z^{2} + 4.34x10^{6}z + 11.45x10^{6}}$$

**Controlador discrtizado:**

$$C_{(z)}= \frac{G_{o(z)}}{G(z)(1-G_{o(z)})}$$

$$C_{(z)} = \frac{\frac{1}{z^{5} + 304z^{4} + 31.21x10^{3}z^{3} + 1.12x10^{6}z^{2} + 4.34x10^{6}z + 11.45x10^{6}}}{(\frac{1.61x10^{-7}z^{2} + 6.25x10^{-7}z + 1.53x10^{-7}}{z^{3} - 2.87z^{2} + 2.75z - 0.88} )(1 - \frac{1}{z^{5} + 304z^{4} + 31.21x10^{3}z^{3} + 1.12x10^{6}z^{2} + 4.34x10^{6}z + 11.45x10^{6}})}$$
$$C_{(z)} = \frac{z^{3} - 2.87z^{2} + 2.75z - 0.88}{(1.61x10^{-7}z^{2} + 6.25x10^{-7}z + 1.53x10^{-7})(z^{5} + 304z^{4} + 31.21x10^{3}z^{3} + 1.12x10^{6}z^{2} + 4.34x10^{6}z + 11.45x10^{6})}$$

**Igualación de modelo:**

$$C = \frac{A_{0} + A_{1}z + A_{2}z^{2}}{B_{0} + B_{1}z + B_{2}z^{2}}$$

**Lazo Cerrado con el controlador discretizado:**

$$G_{o(z)} = \frac{(\frac{1.61x10^{-7}z^{2} + 6.25x10^{-7}z + 1.53x10^{-7}}{z^{3} - 2.87z^{2} + 2.75z - 0.88})(\frac{A_{0} + A_{1}z + A_{2}z^{2}}{B_{0} + B_{1}z + B_{2}z^{2}})}{1 + (\frac{1.61x10^{-7}z^{2} + 6.25x10^{-7}z + 1.53x10^{-7}}{z^{3} - 2.87z^{2} + 2.75z - 0.88} * \frac{A_{0} + A_{1}z + A_{2}z^{2}}{B_{0} + B_{1}z + B_{2}z^{2}})}$$

$$G_{0(z)} = A_{z}D_{z} + B_{z}N_{z}$$

1) $$1 = A_{2}$$

2) $$304 = 1.61x10^{-7}B_{1} + A_{1} - 2.87A_{2}$$

3) $$31.21x10^{3} = 1.61x10^{-7}B_{1} + 2.65x10^{-7}B_{2} + A_{0} - 2.87A_{1} + 2.75A_{2}$$

4) $$1.12x10^{6} = 1.61x10^{-7}B_{0} + 6.25x10^{-7}B_{1} + 1.57x10^{-7}B_{2} - 2.87A_{0} + 2.75A_{1} - 0.88A_{2}$$

5) $$4.34x10^{6} = 6.25x10^{-7}B_{0} + 1.53x10^{-7}B_{1} + 2.75A_{0} - 0.88A_{1}$$

6) $$11.45x10^{6} = 1.53x10^{-7}B_{0} - 0.88A_{0}$$

### Despejando $$B_{2}$$ en 2:

$$B_{2} = \frac{306.87 - A_{1}}{1.61x10^{-7}}$$

### Reemplazar en 3 y despejar $$A_{0}$$
$$31.21x10^{3} = 1.61x10^{-7}B_{1} + 2.65x10^{-7}(\frac{306.87 - A_{1}}{1.61x10^{-7}}) + A_{0} - 2.87A_{1} + 2.75$$
$$5.02x10^{-3} = 2.59x10^{-14}B_{1} + 1.30x10^{-11} - 4.26x10^{-14}A_{1} + 1.61x10^{-7}A_{0} - 4.62x10^{-7}A_{1} + 4.42x10^{-7}$$
$$A_{0} = \frac{5.01x10^{-3} - 2.59x10^{-14}B_{1} + 4.62x10^{-7}A_{1}}{1.61x10^{-7}}$$

### Reemplazar en 4
$$1.12x10^{-6} = 1.61x10^{-7}B_{0} + 6.25x10^{-7}B_{1} + 1.57x10^{-7}(\frac{306.87 - A_{1}}{1.61x10^{-7}}) - 2.87 (\frac{5.01x10^{-3} - 2.59x10^{-14}B_{1} + 4.62x10^{-7}}{1.61x10^{-7}}) + 2.75A_{1} - 0.88A_{2}$$

$$0.18 = 2.59x10^{-14}B_{0} + 1x10^{-3}B_{1} + 7.75x10^{-12} - 2.52x10^{-14}A_{1} - 2.31x10^{-9} + 1.19x10^{-20}B_{1} - 2.13x10^{-13}A_{1} + 4.42x10^{-7}A_{1} - 1.41x10^{-7}$$

$$B_{1} = \frac{0.18 - 2.59x10^{-14}B_{0} - 4.41x10^{-7}A_{1}}{1x10^{-3}}$$

### Reemplazar en 5
$$4.34x10^{-6} = 6.25x10^{-7}B_{0} + 1.53x10^{-7} (\frac{0.18 - 2.59x10^{-14}B_{0} - 4.41x10^{-7}A_{1}}{1x10^{-3}}) + 2.75 (\frac{5.01x10^{-3} - 2.59x10^{-14}B_{1} + 4.62x10^{-7}A_{1}}{1.61x10^{-7}}) - 0.88A_{1}$$
$$4.34x10^{3} = 6.25x10^{-10}B_{0} + 2.75x10^{-11} - 3.46x10^{-24}B_{0} - 6.74x10^{-17}A_{1} + 85.55 - 4.42x10^{-10} (\frac{0.18 - 2.59x10^{-14}B_{0} - 4.41x10^{-7}A_{1}}{1x10^{-3}}) + 7.88x10^{-3}A_{1} - 0.88A_{1}$$

$$4.34 = 6.25x10^{-13}B_{0} + 2.75x10^{-14} - 3.46x10^{-24}B_{0} - 6.74x10^{-20}A_{1} + 0.88 - 7.95x10^{-11} + 1.14x10^{-26}B_{0} + 1.94x10^{-14}A_{1} + 7.88x10^{-6}A_{1} - 8.8x10^{-4}A_{1}$$

$$B_{0} = \frac{4.26 + 8.72x10^{-4}A_{1}}{6.25x10^{-13}}$$







