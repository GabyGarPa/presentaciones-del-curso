# presentaciones-del-curso
presentaciones del curso de temas aplicados de la matemática 

EXPOSICION 1

Serie de Fourier 

Las series de Fourier son una herramienta matemática que permite descomponer una función periódica en una suma infinita de senos y cosenos. Esta descomposición se puede entender como una representación de la función en términos de ondas sinusoidales de diferentes frecuencias.

![image](https://github.com/GabyGarPa/presentaciones-del-curso/assets/144290408/3cdd9d48-cf2d-42e9-8ab2-08184dc16a8c)

Transformada de Fourier 

La transformada de Fourier es una extensión de las series de Fourier para funciones no periódicas. Mientras que las series de Fourier descomponen una función periódica en términos de senos y cosenos, la transformada de Fourier transforma una función del dominio del tiempo (o espacio) al dominio de la frecuencia.

![image](https://github.com/GabyGarPa/presentaciones-del-curso/assets/144290408/0d078777-db5d-4ea6-842d-a43702ca656a)
![image](https://github.com/GabyGarPa/presentaciones-del-curso/assets/144290408/716f58bf-11be-4875-abd6-8e5cab04a3ac)
![image](https://github.com/GabyGarPa/presentaciones-del-curso/assets/144290408/e7119719-f64a-4185-8b88-e6f77f97510e)

Problema principal

Al transmitir una señal g(t) a través de un canal, hay problemas que pueden surgir debido al ruido del canal y a la no linealidad de ciertos componentes.
Las señales de baja amplitud pueden quedar "enmascaradas" o no detectadas debido al ruido del canal.
Las señales de alta amplitud pueden ser afectadas por la no linealidad de los componentes, lo que puede llevar a distorsiones.

Solución propuesta

Una solución a este problema es usar un proceso llamado "companding" instantáneo. En lugar de transmitir la señal original g(t), se transmite una señal modificada. Esta modificación se realiza utilizando una función ϕ(x) con propiedades específicas.

Companding= comprensión-expansión 

Señales de baja amplitud se amplifiquen y las señales de alta amplitud se atenúen. 
Entonces esto nos va a permitir que la señal modificada se transmita y después se descomponga en el receptor para recuperar la señal original. 

Señales de banda limitada

Una señal es banda limitada si contiene frecuencias solo en un rango específico. El companding instantáneo puede destruir esta propiedad.
Entones se quiere suponer que las señales de banda limitada transmitidas son idénticas

codigo 

from sympy import symbols, integrate, Function, oo

# Definición de las variables y funciones
t, u = symbols('t u')
g1 = Function('g_1')(t)
g2 = Function('g_2')(t)
phi1 = Function('phi_1')(u)
phi2 = Function('phi_2')(u)

# Expresión para la integral
expr = (phi1.subs(u, g1) - phi2.subs(u, g2)) * (g1 - g2)

# Resolución de la integral
result = integrate(expr, (t, -oo, oo))


























