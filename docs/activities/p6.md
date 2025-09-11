# Semana 10: Filtrado y Selección de Datos con Pandas - Actividad Práctica

## 🎯 Instrucciones de la Actividad

### 📋 Objetivo
Desarrollar habilidades avanzadas en el filtrado y selección de datos con Pandas, dominando el uso de los métodos `.loc` e `.iloc` para acceder y manipular datos de manera eficiente en DataFrames.

### 🔧 Configuración del Entorno

#### 1. Fork del Repositorio
1. **Hacer Fork**: Haz clic en el botón "Fork" en la esquina superior derecha de este repositorio

```
https://github.com/jfinfocesde/act_ntp_s10.git
```  
2. **Clonar tu Fork**: Clona tu repositorio fork a tu máquina local
   ```bash
   git clone https://github.com/TU_USUARIO/act_ntp_s10.git
   cd act_ntp_s10
   ```

#### 2. Instalación de Dependencias
```bash
pip install pandas numpy datetime
```

#### 3. Estructura del Proyecto
```
act_ntp_s10/
├── README.md              # Este archivo con instrucciones
├── activities.json        # Lista de ejercicios
├── evaluations.json       # Criterios de evaluación
├── info.json             # Información del proyecto
├── data/                 # Carpeta para archivos de datos
│   └── dataset_general.csv # Dataset principal para todos los ejercicios
└── src/                  # Carpeta para tus soluciones
    ├── ejercicio_01.py   # Ejercicio 1 - loc básico
    ├── ejercicio_02.py   # Ejercicio 2 - loc con condiciones
    ├── ejercicio_03.py   # Ejercicio 3 - loc múltiples condiciones
    ├── ejercicio_04.py   # Ejercicio 4 - loc con rangos
    ├── ejercicio_05.py   # Ejercicio 5 - loc modificación datos
    ├── ejercicio_06.py   # Ejercicio 6 - loc con funciones
    ├── ejercicio_07.py   # Ejercicio 7 - loc avanzado
    ├── ejercicio_08.py   # Ejercicio 8 - loc con strings
    ├── ejercicio_09.py   # Ejercicio 9 - loc con fechas
    ├── ejercicio_10.py   # Ejercicio 10 - loc combinado
    ├── ejercicio_11.py   # Ejercicio 11 - iloc básico
    ├── ejercicio_12.py   # Ejercicio 12 - iloc con rangos
    ├── ejercicio_13.py   # Ejercicio 13 - iloc múltiples filas
    ├── ejercicio_14.py   # Ejercicio 14 - iloc columnas específicas
    ├── ejercicio_15.py   # Ejercicio 15 - iloc modificación
    ├── ejercicio_16.py   # Ejercicio 16 - iloc con pasos
    ├── ejercicio_17.py   # Ejercicio 17 - iloc avanzado
    ├── ejercicio_18.py   # Ejercicio 18 - iloc con listas
    ├── ejercicio_19.py   # Ejercicio 19 - iloc combinaciones
    └── ejercicio_20.py   # Ejercicio 20 - iloc complejo
```

## 🚀 Ejercicios a Resolver

### 📊 DataFrame General para Todos los Ejercicios

Todos los ejercicios trabajarán con el mismo DataFrame que contiene información de empleados de una empresa. Este DataFrame incluye las siguientes columnas:

```python
import pandas as pd
import numpy as np
from datetime import datetime, timedelta

# DataFrame general que usarás en todos los ejercicios
data = {
    'empleado_id': range(1, 101),
    'nombre': [f'Empleado_{i}' for i in range(1, 101)],
    'apellido': [f'Apellido_{i}' for i in range(1, 101)],
    'edad': np.random.randint(22, 65, 100),
    'departamento': np.random.choice(['Ventas', 'Marketing', 'IT', 'RRHH', 'Finanzas'], 100),
    'salario': np.random.randint(30000, 120000, 100),
    'fecha_ingreso': [datetime(2020, 1, 1) + timedelta(days=np.random.randint(0, 1460)) for _ in range(100)],
    'activo': np.random.choice([True, False], 100, p=[0.85, 0.15]),
    'ciudad': np.random.choice(['Bogotá', 'Medellín', 'Cali', 'Barranquilla', 'Cartagena'], 100),
    'experiencia_años': np.random.randint(1, 20, 100)
}

df = pd.DataFrame(data)
df.set_index('empleado_id', inplace=True)
```

**Estructura del DataFrame:**
- **empleado_id**: ID único del empleado (índice)
- **nombre**: Nombre del empleado
- **apellido**: Apellido del empleado
- **edad**: Edad en años
- **departamento**: Departamento donde trabaja
- **salario**: Salario anual en pesos
- **fecha_ingreso**: Fecha de ingreso a la empresa
- **activo**: Estado del empleado (True/False)
- **ciudad**: Ciudad donde trabaja
- **experiencia_años**: Años de experiencia laboral

---

### 🎯 EJERCICIOS LOC - Filtrado por Etiquetas (Ejercicios 1-10)

#### **Ejercicio 1: Selección Básica con .loc**
Implementa una función que use `.loc` para seleccionar datos específicos del DataFrame. La función debe:

- Seleccionar un empleado específico por su ID
- Seleccionar múltiples empleados usando una lista de IDs
- Seleccionar un rango de empleados
- Mostrar todos los resultados con formato claro

**Archivo:** `src/ejercicio_01.py`

#### **Ejercicio 2: Filtrado con Condiciones Simples**
Crea una función que filtre empleados usando condiciones con `.loc`. La función debe:

- Filtrar empleados mayores de 40 años
- Filtrar empleados del departamento 'IT'
- Filtrar empleados con salario mayor a 80000
- Mostrar el número de registros encontrados en cada filtro

**Archivo:** `src/ejercicio_02.py`

#### **Ejercicio 3: Filtrado con Múltiples Condiciones**
Desarrolla una función que combine múltiples condiciones con `.loc`. La función debe:

- Filtrar empleados de IT con salario mayor a 70000
- Filtrar empleados de Ventas o Marketing
- Filtrar empleados activos con más de 5 años de experiencia
- Mostrar estadísticas básicas de cada grupo filtrado

**Archivo:** `src/ejercicio_03.py`

#### **Ejercicio 4: Selección de Columnas Específicas**
Implementa una función que seleccione columnas específicas con `.loc`. La función debe:

- Seleccionar solo nombre y salario de todos los empleados
- Seleccionar un rango de columnas desde nombre hasta departamento
- Combinar filtro de filas y columnas para empleados mayores de 50 años
- Mostrar las primeras 10 filas de cada selección

**Archivo:** `src/ejercicio_04.py`

#### **Ejercicio 5: Modificación de Datos con .loc**
Crea una función que modifique datos usando `.loc`. La función debe:

- Aumentar el salario en 10% a empleados de IT
- Cambiar el estado a inactivo para empleados mayores de 60 años
- Actualizar la ciudad a 'Bogotá' para empleados de RRHH
- Mostrar los cambios realizados antes y después

**Archivo:** `src/ejercicio_05.py`

#### **Ejercicio 6: Filtrado con Funciones de String**
Desarrolla una función que use métodos de string con `.loc`. La función debe:

- Filtrar empleados cuyo nombre contenga el dígito '1'
- Filtrar empleados cuyo apellido termine en '5'
- Filtrar empleados de ciudades que empiecen con 'B'
- Mostrar estadísticas de cada grupo encontrado

**Archivo:** `src/ejercicio_06.py`

#### **Ejercicio 7: Filtrado por Fechas**
Implementa una función que filtre por fechas usando `.loc`. La función debe:

- Filtrar empleados que ingresaron en 2022
- Filtrar empleados que ingresaron en los últimos 2 años
- Filtrar empleados que ingresaron en el primer trimestre de cualquier año
- Calcular la antigüedad promedio de cada grupo

**Archivo:** `src/ejercicio_07.py`

#### **Ejercicio 8: Filtrado Avanzado con Funciones**
Crea una función que use funciones personalizadas con `.loc`. La función debe:

- Crear una función que clasifique salarios (bajo, medio, alto)
- Filtrar empleados con salario superior al promedio
- Filtrar empleados con salario en el percentil 75
- Mostrar distribución de cada categoría

**Archivo:** `src/ejercicio_08.py`

#### **Ejercicio 9: Combinación de Filtros Complejos**
Desarrolla una función que combine múltiples tipos de filtros. La función debe:

- Filtrar empleados activos, de IT o Finanzas, con salario > 60000 y edad < 45
- Usar operadores lógicos complejos con paréntesis
- Filtrar empleados de ciudades específicas con experiencia > 10 años
- Crear un resumen estadístico de los grupos filtrados

**Archivo:** `src/ejercicio_09.py`

#### **Ejercicio 10: Análisis Completo con .loc**
Implementa una función que realice un análisis completo usando `.loc`. La función debe:

- Crear múltiples vistas del DataFrame usando diferentes filtros
- Calcular métricas por departamento y ciudad
- Identificar empleados con características específicas (top performers, nuevos, etc.)
- Generar un reporte completo con todas las métricas

**Archivo:** `src/ejercicio_10.py`

---

### 🔢 EJERCICIOS ILOC - Filtrado por Posición (Ejercicios 11-20)

#### **Ejercicio 11: Selección Básica con .iloc**
Implementa una función que use `.iloc` para seleccionar datos por posición. La función debe:

- Seleccionar la primera fila
- Seleccionar las primeras 5 filas
- Seleccionar la última fila
- Seleccionar filas específicas por posición

**Archivo:** `src/ejercicio_11.py`

#### **Ejercicio 12: Selección con Rangos**
Crea una función que use rangos con `.iloc`. La función debe:

- Seleccionar filas del 10 al 20
- Seleccionar las últimas 10 filas
- Seleccionar filas pares
- Seleccionar cada tercera fila

**Archivo:** `src/ejercicio_12.py`

#### **Ejercicio 13: Selección de Múltiples Filas**
Desarrolla una función que seleccione múltiples filas no consecutivas. La función debe:

- Seleccionar filas usando una lista de posiciones específicas
- Seleccionar filas aleatorias
- Combinar diferentes métodos de selección
- Mostrar estadísticas de las filas seleccionadas

**Archivo:** `src/ejercicio_13.py`

#### **Ejercicio 14: Selección de Columnas por Posición**
Implementa una función que seleccione columnas usando `.iloc`. La función debe:

- Seleccionar las primeras 3 columnas
- Seleccionar columnas específicas por posición
- Seleccionar la última columna
- Combinar selección de filas y columnas

**Archivo:** `src/ejercicio_14.py`

#### **Ejercicio 15: Modificación de Datos con .iloc**
Crea una función que modifique datos usando `.iloc`. La función debe:

- Modificar valores en posiciones específicas
- Modificar un rango de celdas
- Modificar múltiples columnas a la vez
- Mostrar los cambios realizados

**Archivo:** `src/ejercicio_15.py`

#### **Ejercicio 16: Selección con Pasos**
Desarrolla una función que use pasos en la selección con `.iloc`. La función debe:

- Seleccionar cada segunda fila
- Seleccionar filas en orden inverso
- Seleccionar cada quinta fila empezando desde la tercera posición
- Combinar pasos en filas y columnas

**Archivo:** `src/ejercicio_16.py`

#### **Ejercicio 17: Selección Avanzada con .iloc**
Implementa una función que realice selecciones complejas. La función debe:

- Seleccionar subconjuntos específicos del DataFrame
- Usar arrays booleanos con `.iloc`
- Combinar `.iloc` con funciones de agregación
- Crear vistas personalizadas del DataFrame

**Archivo:** `src/ejercicio_17.py`

#### **Ejercicio 18: Trabajo con Listas de Índices**
Crea una función que trabaje con listas de índices dinámicas. La función debe:

- Generar listas de índices basadas en condiciones
- Encontrar posiciones que cumplan criterios específicos
- Seleccionar filas basadas en percentiles
- Mostrar diferentes muestras del DataFrame

**Archivo:** `src/ejercicio_18.py`

#### **Ejercicio 19: Combinaciones de .iloc**
Desarrolla una función que combine diferentes usos de `.iloc`. La función debe:

- Crear múltiples vistas usando diferentes patrones de selección
- Combinar selección aleatoria con selección sistemática
- Usar `.iloc` para crear muestras estratificadas
- Comparar diferentes métodos de muestreo

**Archivo:** `src/ejercicio_19.py`

#### **Ejercicio 20: Análisis Completo con .iloc**
Implementa una función que realice un análisis completo usando `.iloc`. La función debe:

- Crear diferentes vistas del DataFrame usando posiciones
- Realizar análisis de muestras aleatorias vs sistemáticas
- Comparar rendimiento de diferentes métodos de selección
- Generar un reporte completo con métricas de las diferentes selecciones

**Archivo:** `src/ejercicio_20.py`

---

