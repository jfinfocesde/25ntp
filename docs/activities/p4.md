# Semana 8: Análisis de Datos con Pandas - Actividad Práctica

## 🎯 Instrucciones de la Actividad

### 📋 Objetivo
Desarrollar habilidades en el uso de la biblioteca Pandas para análisis y manipulación de datos, implementando funciones que trabajen con Series y DataFrames para resolver problemas prácticos de análisis de datos.

### 🔧 Configuración del Entorno

#### 1. Fork del Repositorio
1. **Hacer Fork**: Haz clic en el botón "Fork" en la esquina superior derecha de este repositorio

```
https://github.com/jfinfocesde/act_ntp_s8.git
```  
2. **Clonar tu Fork**: Clona tu repositorio fork a tu máquina local
   ```bash
   git clone https://github.com/TU_USUARIO/act_ntp_s8.git
   cd act_ntp_s8
   ```

#### 2. Instalación de Dependencias
```bash
pip install pandas requests numpy
```

#### 3. Estructura del Proyecto
```
act_ntp_s8/
├── README.md              # Este archivo con instrucciones
├── activities.json        # Lista de ejercicios
├── evaluations.json       # Criterios de evaluación
├── info.json             # Información del proyecto
├── data/                 # Carpeta para archivos de datos
│   ├── sample_data.csv   # Datos de ejemplo
│   └── users_data.json   # Datos JSON de ejemplo
└── src/                  # Carpeta para tus soluciones
    ├── ejercicio_01.py   # Tu solución al ejercicio 1
    ├── ejercicio_02.py   # Tu solución al ejercicio 2
    ├── ejercicio_03.py   # Tu solución al ejercicio 3
    ├── ejercicio_04.py   # Tu solución al ejercicio 4
    ├── ejercicio_05.py   # Tu solución al ejercicio 5
    ├── ejercicio_06.py   # Tu solución al ejercicio 6
    ├── ejercicio_07.py   # Tu solución al ejercicio 7
    ├── ejercicio_08.py   # Tu solución al ejercicio 8
    ├── ejercicio_09.py   # Tu solución al ejercicio 9
    └── ejercicio_10.py   # Tu solución al ejercicio 10
```

## 🚀 Ejercicios a Resolver

### 📊 SERIES - Ejercicios 1-3

#### **Ejercicio 1: Análisis de Ventas Diarias con Series**
Crea una función que genere una Serie de Pandas con las ventas diarias de una tienda (7 días). La función debe:

- Crear una Serie con ventas diarias (ejemplo: [150, 200, 180, 220, 175, 190, 165])
- Acceder al valor del índice 3 usando `serie[3]`
- Calcular el promedio de ventas usando `.mean()`
- Ordenar por valores usando `.sort_values()`
- Mostrar todos los resultados con `print()`

**Archivo:** `src/ejercicio_01.py`

#### **Ejercicio 2: Series con Índices Personalizados**
Implementa una función que cree una Serie con datos de calificaciones de estudiantes usando índices personalizados (nombres de materias). La función debe:

- Crear una Serie con índices personalizados: `pd.Series([85, 92, 78], index=['Matemáticas', 'Ciencias', 'Historia'])`
- Acceder a un valor específico por índice: `serie['Ciencias']`
- Mostrar información básica de la Serie
- Calcular estadísticas básicas como suma y promedio

**Archivo:** `src/ejercicio_02.py`

#### **Ejercicio 3: Operaciones Matemáticas con Series**
Desarrolla una función que cree dos Series de precios y descuentos, y realice operaciones matemáticas entre ellas. La función debe:

- Crear dos Series: precios [100, 150, 200] y descuentos [10, 20, 15]
- Realizar resta entre precios y descuentos
- Multiplicar la Serie de precios por un valor escalar (ejemplo: precios * 1.16 para IVA)
- Mostrar los resultados de todas las operaciones
- Demostrar que las operaciones se realizan elemento por elemento

**Archivo:** `src/ejercicio_03.py`

---

### 📋 DATAFRAMES - Ejercicios 4-10

#### **Ejercicio 4: DataFrame desde Diccionario**
Desarrolla una función que cree un DataFrame desde un diccionario con datos de productos. La función debe:

- Crear un diccionario con las claves: 'Producto', 'Precio', 'Categoria'
- Incluir al menos 3 productos con sus datos (ej: Laptop, Smartphone, Tablet)
- Convertir el diccionario a DataFrame usando `pd.DataFrame(diccionario)`
- Mostrar el DataFrame completo
- Acceder a una columna específica (ejemplo: `df['Precio']`)
- Mostrar información básica del DataFrame con `df.info()`

**Archivo:** `src/ejercicio_04.py`

#### **Ejercicio 5: DataFrame desde Lista de Diccionarios**
Crea una función que genere un DataFrame desde una lista de diccionarios. La función debe:

- Crear una lista que contenga diccionarios, cada uno representando un empleado
- Cada diccionario debe tener las claves: 'empleado', 'salario', 'departamento'
- Incluir al menos 3 empleados con sus datos
- Convertir la lista a DataFrame usando `pd.DataFrame(lista_diccionarios)`
- Mostrar el DataFrame resultante
- Acceder a filas específicas usando índices

**Archivo:** `src/ejercicio_05.py`

#### **Ejercicio 6: DataFrame desde Lista de Listas**
Implementa una función que cree un DataFrame desde una lista de listas. La función debe:

- Crear una lista de listas donde cada sublista representa datos de un libro
- Definir los nombres de las columnas: ['Titulo', 'Autor', 'Año']
- Crear el DataFrame usando `pd.DataFrame(datos, columns=nombres_columnas)`
- Incluir al menos 3 libros con sus datos
- Mostrar el DataFrame y sus dimensiones con `df.shape`

**Archivo:** `src/ejercicio_06.py`

#### **Ejercicio 7: Lectura de Archivo CSV**
Desarrolla una función que:

- Cree un archivo CSV usando la biblioteca `csv` de Python
- Escriba datos de al menos 3 cursos con columnas: curso, instructor, duracion
- Lea el archivo CSV usando `pd.read_csv('cursos.csv')`
- Muestre el DataFrame resultante
- Implemente manejo de errores para el caso de que el archivo no exista

**Archivo:** `src/ejercicio_07.py`

#### **Ejercicio 8: DataFrame desde Archivo JSON**
Crea una función que:

- Genere un archivo JSON con una estructura de lista de objetos
- Cada objeto debe representar un vehículo con propiedades: marca, modelo, año
- Guarde el archivo usando la biblioteca `json` de Python
- Lea el archivo usando `pd.read_json('vehiculos.json')`
- Muestre el DataFrame resultante y sus tipos de datos con `df.dtypes`

**Archivo:** `src/ejercicio_08.py`

#### **Ejercicio 9: DataFrame desde Array NumPy**
Implementa una función que cree un DataFrame desde un array de NumPy. La función debe:

- Crear un array de NumPy 2D usando `np.array()` con datos de ventas trimestrales
- El array debe tener al menos 3 filas y 3 columnas con datos numéricos
- Especificar los nombres de las columnas al crear el DataFrame
- Usar `pd.DataFrame(array_numpy, columns=['Q1', 'Q2', 'Q3'])`
- Mostrar el DataFrame y verificar sus tipos de datos

**Archivo:** `src/ejercicio_09.py`

#### **Ejercicio 10: DataFrame desde API REST**
Desarrolla una función que consuma datos desde la API `https://playground.mockoon.com/users`. La función debe:

- Importar la biblioteca `requests`
- Realizar una petición GET a la URL usando `requests.get()`
- Verificar que el código de estado sea 200
- Convertir la respuesta JSON a DataFrame usando `pd.DataFrame(response.json())`
- Mostrar las primeras 5 filas con `df.head()`
- Implementar manejo de errores con try/except para problemas de conexión
- Mostrar información del DataFrame obtenido

**Archivo:** `src/ejercicio_10.py`

---

