# Reto-11
1. Desarrolle un programa que permita realizar la [suma/resta de matrices](https://es.wikipedia.org/wiki/Adici%C3%B3n_matricial). El programa debe validar las condiciones necesarias para ejecutar la operación.
```python
#Primero se pide debe definar las matrices, así que se definen el número de filas, columnas y se hacen listas vacías para las matrices
numero_filas=int((input("Ingrese el número de filas de las matrices ")))
numero_columnas=int((input("Ingrese el número de columnas de las matrices ")))
matriz1=[]
matriz2=[]
matrizFinal=[]
#Las siguientes 2 funciones se encargan de crear cada matriz con los números de antes, el usuario ingresa elemento por elemento.
def fmatriz1 (x:bool) -> (list):
    base1=0
    base2=0
    lista=[]
    while base1<numero_columnas:
        while base2<numero_filas:
            lista.append(int(input("Agregue los números de la fila ")))
            base2+=1
        base1+=1
        base2=0
        matriz1.append(lista)
        lista=[]
        print("Nueva fila: ")

def fmatriz2 (x:bool) -> (list):
    base1=0
    base2=0
    lista=[]
    while base1<numero_columnas:
        while base2<numero_filas:
            lista.append(int(input("Agregue los números de la fila ")))
            base2+=1
            print("Nueva fila: ")
        base1+=1
        base2=0
        matriz2.append(lista)
        lista=[]
#Esta función suma las matrices elemento por elemento, usando indexes que suben y suben
def sumar (x:bool) -> (list):
    index1=0
    index2=0
    base1=0
    base2=0
    lista=[]
    while base1<numero_columnas:
        while base2<numero_filas:
            lista.append((matriz1[index1][index2])+(matriz2[index1][index2]) )
            index2+=1
            base2+=1
        base1+=1
        base2=0
        index2=0
        index1+=1
        matrizFinal.append(lista)
        lista=[]
#Esta  función resta de la misma manera       
def restar (x:bool) -> (list):
    index1=0
    index2=0
    base1=0
    base2=0
    lista=[]
    while base1<numero_columnas:
        while base2<numero_filas:
            lista.append((matriz1[index1][index2])-(matriz2[index1][index2]) )
            index2+=1
            base2+=1
        base1+=1
        base2=0
        index2=0
        index1+=1
        matrizFinal.append(lista)
        lista=[]
#Se ejecutan las funciones para crear las matrices       
if __name__ == '__main__':
    prueba=True
    fmatriz1(prueba)
    print("Siguiente Matriz:")
    fmatriz2(prueba)
print(matriz1)
print(matriz2)
#Se pide al usuario si quiere restar o sumar
elección=input("Sumar o restar las matrices? ")
#Se ejecuta la función seleccionada y se imprime la matriz final
if elección=="sumar":
    prueba=True
    sumar(prueba)
elif elección=="restar":
    prueba=True
    restar(prueba)
else:
    print("Por favor, escriba ´sumar´o ´restar´ ")
    
print(matrizFinal)

```
2. Desarrolle un programa que permita realizar el [producto de matrices](https://es.wikipedia.org/wiki/Multiplicaci%C3%B3n_de_matrices). El programa debe validar las condiciones necesarias para ejecutar la operación.
```python
#La primera parte es igual al punto anterior
numero_filas=int((input("Ingrese el número de filas de las matrices ")))
numero_columnas=int((input("Ingrese el número de columnas de las matrices ")))
matriz1=[]
matriz2=[]
matrizFinal=[]

def fmatriz1 (x:bool) -> (list):
    base1=0
    base2=0
    lista=[]
    while base1<numero_columnas:
        while base2<numero_filas:
            print("Nueva fila: ")
            lista.append(int(input("Agregue los números de la fila ")))
            base2+=1
        base1+=1
        base2=0
        matriz1.append(lista)
        lista=[]
    

def fmatriz2 (x:bool) -> (list):
    base1=0
    base2=0
    lista=[]
    while base1<numero_columnas:
        while base2<numero_filas:
            print("Nueva fila: ")
            lista.append(int(input("Agregue los números de la fila ")))
            base2+=1
        base1+=1
        base2=0
        matriz2.append(lista)
        lista=[]

if __name__ == '__main__':
    prueba=True
    fmatriz1(prueba)
    print("Siguiente Matriz:")
    fmatriz2(prueba)
print(matriz1)
print(matriz2)
#Esta es la función del producto, toma cada fila según su índice y la suma, hace igual con las columnay y multiplica los resultados
def producto (x:bool) -> (list):
    index1=0
    index2=0
    index3=0
    base1=0
    base2=0
    lista=[]
    elemento1=1
    elemento2=1
    while base1<numero_columnas:
        while base2<numero_filas:
            elemento1*=matriz1[index1][index3]
            elemento2*=matriz2[index3][index1]
            index2+=1
            index3+=1
            base2+=1
            lista.append(elemento1+elemento2)
        base1+=1
        base2=0
        index1+=1
        index2=0
        index3=0
        matrizFinal.append(lista)
        lista=[]
if __name__ == '__main__':
    prueba=True
    producto(prueba)
    
print(matrizFinal)
```
3. Desarrolle un programa que permita obtener la  [matriz transpuesta](https://es.wikipedia.org/wiki/Matriz_transpuesta) de una matriz ingresada. El programa debe validar las condiciones necesarias para ejecutar la operación.
```python
#La primera parte es igual a los puntos anteriores
numero_filas=int((input("Ingrese el número de filas de las matriz ")))
numero_columnas=int((input("Ingrese el número de columnas de las matriz ")))
matriz1=[]
matrizFinal=[]

def fmatriz1 (x:bool) -> (list):
    base1=0
    base2=0
    lista=[]
    while base1<numero_filas:
        while base2<numero_columnas:
            print("Nueva fila: ")
            lista.append(int(input("Agregue los números de la fila ")))
            base2+=1
        base1+=1
        base2=0
        matriz1.append(lista)
        lista=[]
#Esta función se encarga de hacer la matriz superpuesta, toma los elementos de una misma columna y los pone en una nueva lista, que es una columna
def interpuesta (x:bool) -> (list):
    lista=[]
    base1=0
    base2=0
    while base2<numero_columnas:
          while base1<numero_filas:
                lista.append(matriz1[base1][base2])
                base1+=1
          matrizFinal.append(lista)
          base1=0
          base2+=1
          lista=[]
#Se ejecutan las 2 funciones, se muestra la matriz original y la superpuesta   
if __name__ == '__main__':
    prueba=True
    fmatriz1(prueba)
    interpuesta(prueba)
    print(matriz1)
    print(matrizFinal)
```
4. Desarrollar un programa que sume los elementos de una columna dada de una matriz. y 5. Desarrollar un programa que sume los elementos de una fila dada de
una matriz.
```python
#La primera parte es igual a los puntos anteriores
numero_filas=int((input("Ingrese el número de filas de las matriz ")))
numero_columnas=int((input("Ingrese el número de columnas de las matriz ")))
matriz1=[]

def fmatriz1 (x:bool) -> (list):
    base1=0
    base2=0
    lista=[]
    while base1<numero_filas:
        print("Nueva fila: ")
        while base2<numero_columnas:
            lista.append(int(input("Agregue los números de la fila ")))
            base2+=1
        base1+=1
        base2=0
        matriz1.append(lista)
        lista=[]
#Esta función se encarga de sumar la fila que se pide, si se escoge sumar una fila, toma el número que pide el usuario y le resta uno, este es el índex de la lista que se quiere sumar
def fila (x:bool) -> (list):
    numero=int(input("¿Qué número de fila desea sumar? "))-1
    suma=0
    #Se suman los elementos de la lista
    for i in matriz1[numero]:
          suma+=i
    return print(suma)
#Esta función se encarga de sumar la columna que se pide, si es lo que escoge el usuario, hace lo mismo para el index que se necesita, excepto que es un index en cada lista de la matriz
def columna (x:bool) -> (list):
    numero=int(input("¿Qué número de columna desea sumar? "))-1
    suma=0
    base1=0
    #"base1" representa la lista o fila, numero el index para la columna
    while base1<numero_filas:
          suma+=int(matriz1[base1][numero])
          base1+=1
    print(suma)
#Se pide la matriz, se pide escoger entre fila o columna y se ejecuta la función necesaria, luego da el resultado
if __name__ == '__main__':
    prueba=True
    fmatriz1(prueba)
    print(matriz1)
    eleccion=input("Sumar fila o columna? ")
    if eleccion=="fila":
          fila(prueba)
    elif eleccion=="columna":
          columna(prueba)
    else:
          print("Por favor, elija una de las opciones")
    
    
```
