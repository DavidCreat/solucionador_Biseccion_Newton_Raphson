# 🧮 Solucionador de Ecuaciones No Lineales

<div align="center">

[![Python](https://img.shields.io/badge/Python-3.6%2B-blue.svg)](https://www.python.org/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](https://opensource.org/licenses/MIT)
[![Status](https://img.shields.io/badge/Status-Estable-success.svg)]()
[![Métodos](https://img.shields.io/badge/M%C3%A9todos-Bisecci%C3%B3n%20%7C%20Newton--Raphson-orange.svg)]()

</div>

<p align="center">
Una implementación elegante y eficiente de métodos numéricos para encontrar raíces de ecuaciones no lineales.
</p>

---

## 📋 Contenido

- [Descripción](#-descripción)
- [Características](#-características)
- [Métodos Implementados](#-métodos-implementados)
- [Requisitos](#-requisitos)
- [Instalación](#-instalación)
- [Uso](#-uso)
  - [Modo Interactivo](#modo-interactivo)
  - [Modo Línea de Comandos](#modo-línea-de-comandos)
  - [Modo Archivo de Parámetros](#modo-archivo-de-parámetros)
- [Ejemplos](#-ejemplos)
- [Estructura del Proyecto](#-estructura-del-proyecto)
- [Contribución](#-contribución)
- [Licencia](#-licencia)

---

## 📝 Descripción

Este programa implementa dos métodos numéricos fundamentales para encontrar raíces de ecuaciones no lineales:

1. **Método de Bisección**: Un método robusto que garantiza convergencia para funciones continuas.
2. **Método de Newton-Raphson**: Un método de convergencia cuadrática que utiliza la derivada de la función.

El programa está diseñado con una interfaz intuitiva y proporciona análisis detallados de rendimiento y precisión para ambos métodos.

---

## ✨ Características

- 🖥️ **Interfaz de consola intuitiva** con instrucciones paso a paso
- 📊 **Visualización detallada** de resultados con tablas de iteraciones
- 📈 **Comparación automática** entre métodos (velocidad, precisión, iteraciones)
- 🧠 **Cálculo automático** de derivadas numéricas
- 🛡️ **Validación robusta** de entradas y manejo de errores
- 🔄 **Múltiples modos** de ejecución (interactivo, línea de comandos, archivo)
- 📋 **Soporte para ecuaciones complejas** con funciones matemáticas estándar

---

## 🔍 Métodos Implementados

| Método | Características | Ventajas | Desventajas |
|--------|----------------|----------|-------------|
| **Bisección** | Requiere intervalo [a,b] donde f(a)·f(b) < 0 | <ul><li>Convergencia garantizada</li><li>Robusto</li><li>Simple de implementar</li></ul> | <ul><li>Convergencia lenta (lineal)</li><li>Requiere un intervalo inicial</li></ul> |
| **Newton-Raphson** | Requiere un valor inicial x₀ | <ul><li>Convergencia rápida (cuadrática)</li><li>Precisión alta</li></ul> | <ul><li>Puede diverger</li><li>Requiere que la función sea diferenciable</li><li>Problemas si f'(x) ≈ 0</li></ul> |

---

## 📋 Requisitos

- Python 3.6 o superior
- Módulos estándar de Python:
  - `math`: Funciones matemáticas
  - `re`: Expresiones regulares
  - `sys`: Interacción con el sistema
  - `argparse`: Manejo de argumentos de línea de comandos
  - `time`: Medición de tiempos de ejecución

---

## 🚀 Instalación

No se requiere instalación especial. Simplemente clona o descarga este repositorio:

```bash
git clone https://github.com/tu-usuario/solucionador-ecuaciones.git
cd solucionador-ecuaciones
```

---

## 💻 Uso

### Modo Interactivo

Simplemente ejecuta el programa sin argumentos:

```bash
python solucionador_ecuaciones.py
```

El programa te guiará paso a paso:
1. Ingreso de la ecuación
2. Selección del método
3. Configuración de parámetros
4. Visualización de resultados

### Modo Línea de Comandos

```bash
python solucionador_ecuaciones.py -e "x^2-4" -m biseccion -a -5 -b 5
```

#### Argumentos disponibles:

| Argumento | Descripción | Ejemplo |
|-----------|-------------|---------|
| `-e, --equation` | Ecuación a resolver | `-e "x^2-4"` |
| `-m, --method` | Método a utilizar | `-m biseccion` |
| `-a` | Extremo izquierdo del intervalo | `-a -5` |
| `-b` | Extremo derecho del intervalo | `-b 5` |
| `-x0` | Aproximación inicial para Newton-Raphson | `-x0 3` |
| `-t, --tolerance` | Tolerancia | `-t 1e-8` |
| `-i, --max-iterations` | Número máximo de iteraciones | `-i 50` |
| `-f, --file` | Archivo con parámetros | `-f parametros.txt` |

### Modo Archivo de Parámetros

Crea un archivo de texto con los parámetros:

```
# Archivo de parámetros
equation=x^2 - 4
method=both
a=-5
b=0
x0=-1
tolerance=1e-8
max_iterations=50
```

Y ejecútalo:

```bash
python solucionador_ecuaciones.py -f parametros.txt
```

---

## 📊 Ejemplos

### Ejemplo 1: Ecuación polinómica

```
Ecuación: x^2 - 4
Raíces exactas: x = 2 y x = -2
```

<details>
<summary>Ver resultados</summary>

```
Método de Bisección:
• Raíz encontrada: 2.0000000019
• Iteraciones: 29
• Error absoluto final: 9.3132257462e-09

Método de Newton-Raphson:
• Raíz encontrada: 2.0000000000
• Iteraciones: 5
• Error absoluto final: 2.1094237468e-14
```

</details>

### Ejemplo 2: Función trigonométrica

```
Ecuación: sin(x)
Raíces exactas: x = 0, π, 2π, ...
```

<details>
<summary>Ver resultados</summary>

```
Método de Bisección:
• Raíz encontrada: 3.1415920258
• Iteraciones: 19
• Error absoluto final: 1.9073486328e-06

Método de Newton-Raphson:
• Raíz encontrada: 3.1415926536
• Iteraciones: 3
• Error absoluto final: 1.3322676296e-15
```

</details>

### Ejemplo 3: Función exponencial

```
Ecuación: exp(x) - 2
Raíz exacta: x = ln(2) ≈ 0.693147
```

<details>
<summary>Ver resultados</summary>

```
Método de Bisección:
• Raíz encontrada: 0.6931476593
• Iteraciones: 19
• Error absoluto final: 1.9073486328e-06

Método de Newton-Raphson:
• Raíz encontrada: 0.6931471806
• Iteraciones: 4
• Error absoluto final: 1.9498675230e-08
```

</details>

---

## 📁 Estructura del Proyecto

```
solucionador-ecuaciones/
├── solucionador_ecuaciones.py   # Programa principal
├── parametros.txt               # Ejemplo de archivo de parámetros
└── README.md                    # Este archivo
```

### Funciones Principales

| Función | Descripción |
|---------|-------------|
| `analizar_ecuacion()` | Convierte una cadena de texto en una función evaluable |
| `derivada()` | Calcula la derivada numérica de una función |
| `metodo_biseccion()` | Implementa el método de bisección |
| `metodo_newton_raphson()` | Implementa el método de Newton-Raphson |
| `comparar_metodos()` | Compara los resultados de ambos métodos |

---

## 👥 Contribución

Las contribuciones son bienvenidas. Si deseas mejorar este proyecto:

1. Haz un fork del repositorio
2. Crea una rama para tu característica (`git checkout -b feature/nueva-caracteristica`)
3. Realiza tus cambios y haz commit (`git commit -m 'Añadir nueva característica'`)
4. Sube tus cambios (`git push origin feature/nueva-caracteristica`)
5. Abre un Pull Request

---

## 📜 Licencia

Este proyecto está licenciado bajo la Licencia MIT - consulta el archivo [LICENSE](LICENSE) para más detalles.

---

<div align="center">
<p>Desarrollado con ❤️ para el curso de Cálculo Numérico</p>
<p>© 2025</p>
</div>
