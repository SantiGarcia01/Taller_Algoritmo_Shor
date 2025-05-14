# Taller_Algoritmo_Shor

### Descripción de las funciones y análisis:

## 1. Función findPeriod(a, N)

def findPeriod(a, N):
    powers = powersAModuloNRecursive(a, N)
    return powers.index(1, 1)

Objetivo: Encuentra el período de las potencias de a módulo N.

Explicación: La función obtiene las potencias de a módulo N a través de la llamada a powersAModuloNRecursive(a, N) y luego busca el primer índice en el que el valor de esa lista sea 1, comenzando desde el segundo índice. El valor que se devuelve es el período, es decir, el primer valor r tal que 𝑎^𝑟 ≡ 1 mod 𝑁.

## 2. Función gcd(a, b)
def gcd(a, b):
    while b != 0:
        t = b
        b = a % b
        a = t
    return a
Objetivo: Calcular el máximo común divisor (MCD) de dos números a y b.

Explicación: Este es un algoritmo de Euclides, que es una manera eficiente de calcular el MCD. Mientras b no sea cero, se realiza una operación de división y se intercambian los valores de a y b, reduciendo progresivamente el tamaño de los números. Cuando b se convierte en 0, a es el MCD.

Uso en el código: Es útil para encontrar los factores de N durante el proceso de factorización.

## 3.  Función main()
def main():
    N = 247
    a = 2
    powers_a_N = powersAModuloNRecursive(a, N)
    xpoints = np.array(range(N))
    ypoints = np.array(powers_a_N)

    print("f_a_N=", powers_a_N)
    period = findPeriod(a, N)
    print("period of f_a_N=", period)

    print("a^(period/2) Mod N = ", (a**(period/2)) % N)
    print("(-1) Mod N= ",  (-1) % N)
    print("factor1= ", gcd((a**(period/2)) + 1, N))
    print("factor2= ", gcd((a**(period/2)) - 1, N))

    print((a**(period/2)) +1)
    print("gcd(161,371)=",gcd(161,371))
    print("We can do this because 160 congruent with 24^39")

    plt.bar(xpoints, ypoints)
    plt.show()
Objetivo: Ejecutar el código principal para determinar el período de las potencias de a módulo N, calcular los factores posibles de N y graficar la secuencia de las potencias.

# Explicación detallada:

Definición de variables:

𝑁 = 247: Este es el número que se quiere factorizar.
a = 2: Este es el número base con el que se calculan las potencias.

Cálculo de las potencias:

powers_a_N = powersAModuloNRecursive(a, N) parece ser una función (que no está definida en el código proporcionado) que calcula las potencias de a módulo N. Debería devolver una lista con los valores a^0 mod N, a^1 mod N, a^2 mod N,...,.

Gráfico:

El gráfico se genera utilizando matplotlib, con los valores de x siendo los índices (de 0 a N−1) y los valores de y siendo las potencias de a módulo N. Esto muestra cómo cambia la secuencia de las potencias de a módulo N.

Cálculo del período:

La función findPeriod(a, N) calcula el período de las potencias de a módulo N. Este es un valor crucial porque el algoritmo de factorización basado en el período usa este valor para encontrar posibles divisores de N.

Cálculos adicionales:

El cálculo de a^periodo/2 mod N y los factores derivados de este valor es un paso típico en los algoritmos de factorización, donde se prueban valores a^periodo/2 ± 1 para encontrar factores de N mediante el cálculo de su MCD con N.

La salida de gcd((a**(period/2)) + 1, N) y gcd((a**(period/2)) - 1, N) ofrece los posibles factores de N.

Otros cálculos:

Hay un valor de ejemplo de gcd(161,371) y una línea de texto explicativa que menciona la congruencia 160≡ 24^39 mod 𝑁 160≡24^39 mod N, que puede ser un recordatorio del proceso de factorización y la relación entre los números involucrados.

### Pre-requisitos

Tener instalado Python en el computador ademas de algun programa el cual permita el funcionamiento como Visual Studio Code ademas de las extenciones de jupyter.

## Lenguaje usado:
* Python
* GIT
* Jupyter

# Archivos
Se encontraran dos archivos los cuales son:
Shors_Algorithm_Workshop.pbyn y Readme
