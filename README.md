# Reto-11
## 1.
### Desarrolle un programa que permita realizar la suma/resta de matrices. El programa debe validar las condiciones necesarias para ejecutar la operación.
```python
  def crear_matriz (f:int, c:int):
    """
    Esta función crea la matriz de acuerdo a los parametros ingresados por el usuario

    Args:
        Se le ingresan los enteros f y c que corresponden a filas y columnas obtenidas
        por entrada del usuario en la función principal
    
    Returns: 
        una matriz con las dimensiones fxc en la que cada item fue ingresado manualmente por el usuario dentro de la función
        
    """
    matriz=[]
    for i in range (f):
        fil=[]
        for j in range(c):
            fil.append(float(input(f"Elemento {j+1} de la fila {i+1}: "))) # Entrada del item ixj en la matriz por el usuario
        matriz.append(fil)
    return matriz

def print_matrices(*args):
    """
    Esta función imprime la matriz de manera legible imprimiendo fila por fila

    Args:
        La función opera con los argumentos enviados desde la función principal
    
    Returns: 
        La función imprime los elementos que se le piden pero no retorna nada a la función principal que la llamo
        
    """
    for i in range(len(args)): # El len(args) es la cantidad de filas de la matriz
        for j in range (len(args[i])): # len(args(i)) es la cantidad de elementos en la lista que corresponde a la fila i
            print(args[i][j])
    print("\n")

def suma_matrices(f:int, c:int, matriz1,matriz2):
    """
    La función suma_matrices realiza la suma entre 2 matrices dadas

    Args:
        A la función le entran como argumentos f(filas), c(columnas), matriz1 y matriz2 que serán sumadas
    
    Returns: 
        La función imprime la matriz resultante de la suma mas no retorna nada a la función que la llamó
        
    """
    matriz=matriz1
    for i in range(f):
        for j in range(c):
            matriz[i][j]+=matriz2[i][j] #Como matriz es igual a matriz1 solo se le tiene que sumar el elemento en la misma posición ixj
    print_matrices(matriz)

def resta_matrices(f:int, c:int, matriz1,matriz2):
    """
    La función resta_matrices realiza la resta entre 2 matrices dadas

    Args:
        A la función le entran como argumentos f(filas), c(columnas), matriz1 y matriz2 que serán sumadas
    
    Returns: 
        La función imprime la matriz resultante de la resta mas no retorna nada a la función que la llamó
        
    """
    matriz=matriz1
    for i in range(f):
        for j in range(c):
            matriz[i][j]-=matriz2[i][j] #Como matriz es igual a matriz1 solo se le tiene que restar el elemento en la misma posición ixj
    print_matrices(matriz)

if __name__=="__main__":
    f=int(input("Que tantas filas quieres: "))
    c=int(input("Con cuantas columnas: "))
    print("Ingresa para matriz 1: ")
    matriz1=crear_matriz(f,c)
    print("Ingresa para matriz 2: ")
    matriz2=crear_matriz(f,c)
    print("Matriz 1: ")
    print_matrices(matriz1)
    print("Matriz 2: ")
    print_matrices(matriz2)
    print("Matriz suma de las matrices: ")
    suma_matrices(f,c,matriz1,matriz2)
    print("Matriz resta de las matrices: ")
    suma_matrices(f,c,matriz1,matriz2)
```
##2.
### Desarrolle un programa que permita realizar el producto de matrices. El programa debe validar las condiciones necesarias para ejecutar la operación.
```python
  def crear_matriz (f:int):
    """
    Esta función crea la matriz de acuerdo a los parametros ingresados por el usuario

    Args:
        Se le ingresa el entero f que corresponden a filas y columnas obtenidas
        por entrada del usuario en la función principal
    
    Returns: 
        una matriz con las dimensiones fxf en la que cada item fue ingresado manualmente por el usuario dentro de la función
        
    """
    
    matriz=[]
    for i in range (f):
        fil=[]
        for j in range(f):
            fil.append(float(input(f"Elemento {j+1} de la fila {i+1}: ")))
        matriz.append(fil)
    return matriz

def print_matrices(*args):
    """
    Esta función imprime la matriz de manera legible imprimiendo fila por fila

    Args:
        La función opera con los argumentos enviados desde la función principal
    
    Returns: 
        La función imprime los elementos que se le piden pero no retorna nada a la función principal que la llamo
        
    """
    for i in range(len(args)): # El len(args) es la cantidad de filas de la matriz
        for j in range (len(args[i])): # len(args(i)) es la cantidad de elementos en la lista que corresponde a la fila i
            print(args[i][j])
    print("\n")

def producto_matrices(f,matriz1, matriz2):
    """
    La función producto_matrices realiza la multiplicación entre 2 matrices dadas

    Args:
        A la función le entran como argumentos f(filas y columnas), matriz1 y matriz2 que serán sumadas
    
    Returns: 
        La función imprime la matriz resultante del producto mas no retorna nada a la función que la llamó
        """
    matriz = []
    for i in range(f):
        fila = []
        for j in range(f):
            fila.append(0)
        matriz.append(fila)
    
    for i in range(f):
        for j in range(f):
            for h in range(f):
                matriz[i][j] += matriz1[i][h] * matriz2[h][j] #Para el producto de matrices se multiplican las filas con las columnas, siendo la suma de los elementos de la fila por los de la columna 
    print_matrices(matriz)

if __name__=="__main__":
    f=int(input("Que tantas filas  y columnas quieres: "))
    print("Ingresa para matriz 1: ")
    matriz1=crear_matriz(f)
    print("Ingresa para matriz 2: ")
    matriz2=crear_matriz(f)
    print("Matriz 1: ")
    print_matrices(matriz1)
    print("Matriz 2: ")
    print_matrices(matriz2)
    print("Matriz producto de las matrices: ")
    producto_matrices(f,matriz1,matriz2)
```
## 3.
### Desarrolle un programa que permita obtener la matriz transpuesta de una matriz ingresada. El programa debe validar las condiciones necesarias para ejecutar la operación.
```python
def crear_matriz (f:int, c:int):
    """
    Esta función crea la matriz de acuerdo a los parametros ingresados por el usuario

    Args:
        Se le ingresan los enteros f y c que corresponden a filas y columnas obtenidas
        por entrada del usuario en la función principal
    
    Returns: 
        una matriz con las dimensiones fxc en la que cada item fue ingresado manualmente por el usuario dentro de la función
        
    """
    matriz=[]
    for i in range (f):
        fil=[]
        for j in range(c):
            fil.append(float(input(f"Elemento {j+1} de la fila {i+1}: ")))
        matriz.append(fil)
    return matriz

def print_matrices(*args):
    """
    Esta función imprime la matriz de manera legible imprimiendo fila por fila

    Args:
        La función opera con los argumentos enviados desde la función principal
    
    Returns: 
        La función imprime los elementos que se le piden pero no retorna nada a la función principal que la llamo
        
    """
    for i in range(len(args)): # El len(args) es la cantidad de filas de la matriz
        for j in range (len(args[i])): # len(args(i)) es la cantidad de elementos en la lista que corresponde a la fila i
            print(args[i][j])
    print("\n")

def trans_matriz(f:int, c:int, matriz1):
    """
    La función trans_matrices realiza la transposición de una matriz, convirtiendo sus filas en columnas y viceversa

    Args:
        A la función le entran como argumentos f(filas), c(columnas) y matriz1 que será transpuesta
    
    Returns: 
        La función retorna la versión transpuesta de la matriz1 que le fue ingresada
    """
    matriz=[]
    for i in range (c):
        fil=[]
        for j in range(f):
            fil.append(matriz1[j][i])# Se añaden los elementos a la nueva matriz vacia con columnas como filas y filas como columnas
        matriz.append(fil)
    return matriz

if __name__=="__main__":
    f=int(input("Que tantas filas quieres: "))
    c=int(input("Con cuantas columnas: "))
    print("Ingresa para matriz 1: ")
    matriz1=crear_matriz(f,c)
    print("Matriz 1: ")
    print_matrices(matriz1)
    matriz2=trans_matriz(f,c, matriz1)
    print("Matriz 1 Transpuesta: ")
    print_matrices(matriz2)

```
## 4.
### Desarrollar un programa que sume los elementos de una columna dada de una matriz.
```python
  def crear_matriz (f:int, c:int):
    """
    Esta función crea la matriz de acuerdo a los parametros ingresados por el usuario

    Args:
        Se le ingresan los enteros f y c que corresponden a filas y columnas obtenidas
        por entrada del usuario en la función principal
    
    Returns: 
        una matriz con las dimensiones fxc en la que cada item fue ingresado manualmente por el usuario dentro de la función
        
    """
    matriz=[]
    for i in range (f):
        fil=[]
        for j in range(c):
            fil.append(float(input(f"Elemento {j+1} de la fila {i+1}: ")))
        matriz.append(fil)
    return matriz

def print_matrices(*args):
    """
    Esta función imprime la matriz de manera legible imprimiendo fila por fila

    Args:
        La función opera con los argumentos enviados desde la función principal
    
    Returns: 
        La función imprime los elementos que se le piden pero no retorna nada a la función principal que la llamo
        
    """
    for i in range(len(args)): # El len(args) es la cantidad de filas de la matriz
        for j in range (len(args[i])): # len(args(i)) es la cantidad de elementos en la lista que corresponde a la fila i
            print(args[i][j])
    print("\n")

def sumar_columna(f:int, c:int, matriz1):
    """
    La función sumar_columna realiza la suma de los elementos de una columna dada

    Args:
        A la función le entran como argumentos f(filas), c(columna a sumar) y matriz1
    
    Returns: 
        La función retorna la suma de todos los elementos en la columna dada
    """
    suma:int=0
    for i in range(f):
        suma+=matriz1[i][c-1]
    return suma

if __name__=="__main__":
    f=int(input("Que tantas filas quieres: "))
    c=int(input("Con cuantas columnas: "))
    print("Ingresa para matriz 1: ")
    matriz1=crear_matriz(f,c)
    print("Matriz 1: ")
    print_matrices(matriz1)
    col=int(input("Ingrese que columna se va a sumar"))
    sumas=sumar_columna(f, col, matriz1)
    print(f"La suma de la columna {col} es igual a: {sumas}")
```
## 5.
### Desarrollar un programa que sume los elementos de una fila dada de una matriz.
```python
  def crear_matriz (f:int, c:int):
    """
    Esta función crea la matriz de acuerdo a los parametros ingresados por el usuario

    Args:
        Se le ingresan los enteros f y c que corresponden a filas y columnas obtenidas
        por entrada del usuario en la función principal
    
    Returns: 
        una matriz con las dimensiones fxc en la que cada item fue ingresado manualmente por el usuario dentro de la función
        
    """
    matriz=[]
    for i in range (f):
        fil=[]
        for j in range(c):
            fil.append(float(input(f"Elemento {j+1} de la fila {i+1}: ")))
        matriz.append(fil)
    return matriz

def print_matrices(*args):
    """
    Esta función imprime la matriz de manera legible imprimiendo fila por fila

    Args:
        La función opera con los argumentos enviados desde la función principal
    
    Returns: 
        La función imprime los elementos que se le piden pero no retorna nada a la función principal que la llamo
        
    """
    for i in range(len(args)): # El len(args) es la cantidad de filas de la matriz
        for j in range (len(args[i])): # len(args(i)) es la cantidad de elementos en la lista que corresponde a la fila i
            print(args[i][j])
    print("\n")

def sumar_fila(f:int, c:int, matriz1):
    """
    La función sumar_fila realiza la suma de los elementos de una fila dada

    Args:
        A la función le entran como argumentos f(fila a sumar), c(columnas) y matriz1
    
    Returns: 
        La función retorna la suma de todos los elementos en la fila dada
    """
    suma:int=0
    for i in range(c):
        suma+=matriz1[i][f-1]
    return suma

if __name__=="__main__":
    f=int(input("Que tantas filas quieres: "))
    c=int(input("Con cuantas columnas: "))
    print("Ingresa para matriz 1: ")
    matriz1=crear_matriz(f,c)
    print("Matriz 1: ")
    print_matrices(matriz1)
    fil=int(input("Ingrese que fil se va a sumar"))
    sumas=sumar_columna(fil, c, matriz1)
    print(f"La suma de la columna {fil} es igual a: {sumas}")
```
