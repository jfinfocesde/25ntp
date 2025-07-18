# Solución

### ejercicio_01.py
```python
# Imprimir los números del 0 al 9 con for
for i in range(10):
    print(i)
```

---

### ejercicio_02.py
```python
# Imprimir los números del 10 al 1 con while
n = 10
while n >= 1:
    print(n)
    n -= 1
```

---

### ejercicio_03.py
```python
# Suma del 1 al 100 con for
total = 0
for i in range(1, 101):
    total += i
print(total)
```

---

### ejercicio_04.py
```python
# Sumar números hasta que el usuario ingrese 0 con while
suma = 0
while True:
    num = float(input("Ingresa número (0 para terminar): "))
    if num == 0:
        break
    suma += num
print("Suma total:", suma)
```

---

### ejercicio_05.py
```python
# Tabla de multiplicar del 7 con for
for i in range(1, 11):
    print(f"7 x {i} = {7 * i}")
```

---

### ejercicio_06.py
```python
# Primeros 15 múltiplos de 3 con while
cont = 1
while cont <= 15:
    print(cont * 3)
    cont += 1
```

---

### ejercicio_07.py
```python
# Contar letras 'a' en "manzana" con for
texto = "manzana"
cant = 0
for letra in texto:
    if letra == 'a':
        cant += 1
print(cant)
```

---

### ejercicio_08.py
```python
# Cuadrados del 1 al 20 con while
n = 1
while n <= 20:
    print(n ** 2)
    n += 1
```

---

### ejercicio_09.py
```python
# Pares del 2 al 50 con for
for n in range(2, 51, 2):
    print(n)
```

---

### ejercicio_10.py
```python
# Contar palabras hasta "fin" con while
cont = 0
while True:
    palabra = input("Palabra (fin para terminar): ")
    if palabra == "fin":
        break
    cont += 1
print("Palabras leídas:", cont)
```

---

### ejercicio_11.py
```python
# Imprimir cada carácter de "python" con for
for ch in "python":
    print(ch)
```

---

### ejercicio_12.py
```python
# Factorial de n con while
n = int(input("Introduce n: "))
factorial = 1
i = 1
while i <= n:
    factorial *= i
    i += 1
print("Factorial:", factorial)
```

---

### ejercicio_13.py
```python
# Números del 1 al 30 de 3 en 3 con for
for n in range(1, 30, 3):
    print(n)
```

---

### ejercicio_14.py
```python
# Adivinar número del 1 al 10 con while
import random
secreto = random.randint(1, 10)
while True:
    intento = int(input("Adivina (1-10): "))
    if intento == secreto:
        print("¡Acertaste!")
        break
    print("Inténtalo de nuevo.")
```

---

### ejercicio_15.py
```python
# Triángulo de asteriscos de 5 filas con for
for i in range(1, 6):
    print("*" * i)
```

---

### ejercicio_16.py
```python
# Reloj de 00:00 a 00:59 con while
minutos = 0
segundos = 0
while minutos < 1:
    print(f"{minutos:02d}:{segundos:02d}")
    segundos += 1
    if segundos == 60:
        segundos = 0
        minutos += 1
```

---

### ejercicio_17.py
```python
# Suma de dígitos de un número con for
num = input("Introduce número: ")
suma = 0
for d in num:
    suma += int(d)
print("Suma de dígitos:", suma)
```

---

### ejercicio_18.py
```python
# Fibonacci hasta superar 1000 con while
a, b = 1, 1
while a <= 1000:
    print(a)
    a, b = b, a + b
```

---

### ejercicio_19.py
```python
# Contar vocales en frase con for
frase = "programacion es divertida"
vocales = "aeiouáéíóú"
cont = 0
for letra in frase.lower():
    if letra in vocales:
        cont += 1
print("Vocales:", cont)
```

---

### ejercicio_20.py
```python
# Edad mayor introducida con while
mayor = -1
while True:
    edad = int(input("Edad (-1 para terminar): "))
    if edad == -1:
        break
    if edad > mayor:
        mayor = edad
print("Edad mayor:", mayor)
```

---

