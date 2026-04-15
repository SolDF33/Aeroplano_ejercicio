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


### 5. Diferencia en Tiempo de Ejecución: Composición vs. Agregación

Desde una perspectiva de rendimiento técnico (velocidad de procesamiento), la diferencia es prácticamente inexistente. Sin embargo, la distinción fundamental ocurre en la **gestión de la memoria** y el **ciclo de vida**:

* **Gestión del Ciclo de Vida:**
    * En la **Composición**, el objeto "Todo" es responsable de la instanciación de sus "Partes". En tiempo de ejecución, cuando el objeto principal es eliminado, el recolector de basura elimina automáticamente sus componentes, optimizando la liberación de memoria de forma inmediata.
    * En la **Agregación**, las partes tienen un ciclo de vida independiente. Al ser inyectadas desde el exterior, si el objeto principal desaparece, los componentes (los "repuestos") permanecen en memoria para ser reutilizados por otros objetos.

* **Flexibilidad vs. Acoplamiento:**
    * La **Agregación** permite una mayor flexibilidad en tiempo de ejecución, ya que permite intercambiar componentes dinámicamente sin necesidad de recrear el objeto principal.
    * La **Composición** ofrece un acoplamiento fuerte que garantiza que el objeto siempre tenga sus partes necesarias desde el momento cero, pero a costa de una estructura más rígida.

**Conclusión:** La elección no se basa en la velocidad de ejecución, sino en la necesidad de **reutilización de objetos** (Agregación) frente a la **seguridad de integridad** del objeto (Composición). 

**Desarrollado por:** Sol De Francesco  
**Materia:** Programación  
**Año:** 2026