# Trabajo Práctico: Modelado de Aeroplano (POO)

Este proyecto consiste en el modelado de un aeroplano utilizando **TypeScript**, aplicando conceptos avanzados de Programación Orientada a Objetos para representar la estructura y relación entre sus componentes.

## 🚀 Ejecución del Proyecto

Para verificar el funcionamiento del código en una terminal con Node.js y TypeScript instalado, ejecute:

bash
npx ts-node aeroplano.ts


---

## 🛠️ Análisis de POO y Diseño

### 1. Relación de Jerarquía (Todo-Partes)
El sistema utiliza una estructura jerárquica donde la clase **Aeroplano** actúa como el objeto raíz (el "Todo") que coordina a sus componentes (las "Partes"):
- **Componentes:** `Helice`, `Alas`, `TrendeAterrizaje` y `Cubierta`.

### 2. Implementación de Agregación 
Aunque los componentes forman parte del aeroplano, se ha optado por una relación de **Agregación** en lugar de Composición estricta. 

**Justificación técnica:** Siguiendo la lógica de mantenimiento aeronáutico, las partes pueden existir como **repuestos** independientes. En el código, esto se refleja mediante la **Inyección de Dependencias**: los objetos de las partes se crean externamente y se pasan al constructor del Aeroplano. Esto permite que el ciclo de vida de las partes no dependa exclusivamente de la existencia del objeto Aeroplano.

### 3. Métodos y Comportamiento
Cada clase implementa un método `ToString()` que permite encapsular la información técnica de cada componente, logrando un código modular, legible y fácil de mantener.


### 5. Diferencias de Ejecución
En tiempo de ejecución, no hay una diferencia significativa en la velocidad de procesamiento. La diferencia clave es el ciclo de vida: en la Composición, las partes mueren con el todo, optimizando la liberación de memoria; en la Agregación, las partes sobreviven al todo, permitiendo la reutilización de objetos pero requiriendo una gestión de memoria más consciente.
---
**Desarrollado por:** Sol De Francesco  
**Materia:** Programación  
**Año:** 2026