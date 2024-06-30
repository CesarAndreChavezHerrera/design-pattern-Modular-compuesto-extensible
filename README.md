
# Patrón de Diseño Modular Compuesto Extensible para Videojuegos

## ¿Qué es?
El **Patrón de Diseño Modular Compuesto Extensible** es un enfoque arquitectónico para el desarrollo de videojuegos que facilita la construcción y modificación de objetos complejos mediante la combinación de módulos independientes. Este patrón permite una gran flexibilidad y reutilización de componentes, haciendo que la adición de nuevas funcionalidades y la modificación de las existentes sea un proceso sencillo y eficiente.

## ¿Cómo nace?
Al trabajar con Godot Engine y al crear prototipos tanto para mí como al ser invitado a revisiones de sprint de videojuegos, he notado los desafíos comunes de reutilización y flexibilidad que otros desarrolladores enfrentan, y que yo también he experimentado. Con el objetivo de optimizar tiempos y maximizar la reutilización de recursos, surgió la necesidad de desarrollar un nuevo patrón de diseño. Este patrón está diseñado específicamente para aplicarse en Godot, aunque también puede adaptarse eficazmente a otros motores de juego.

## ¿En qué consiste?
Este patrón se compone de tres partes principales:

### Unidad Funcional
La **Unidad Funcional** define la funcionalidad básica que varios módulos pueden compartir. Al añadir una Unidad Funcional a un módulo, este adquiere la funcionalidad específica proporcionada por dicha unidad.

**Ejemplo:** Imaginemos que tenemos diferentes enemigos, jugadores y otros objetos en el juego. Todos estos objetos necesitan manejar su vida (HP) y reducirla cuando reciben daño. Para esto, creamos una "Unidad Funcional de vida" que contiene toda la lógica necesaria. Cada vez que necesitemos que un módulo (por ejemplo, una pared destructible) tenga la lógica de vida, simplemente añadimos la Unidad Funcional de vida a dicho módulo.

### Modificador
El **Modificador** es una Unidad Funcional diseñada para alterar o modificar otras Unidades Funcionales. Proporciona variaciones de comportamiento que pueden ser temporales o permanentes y está pensado para modificar Unidades Funcionales, no módulos directamente.

**Ejemplo:** Supongamos que tenemos un módulo "jugador" con la _Unidad Funcional de vida_ y la _Unidad Funcional de movimiento_. Si el jugador entra en contacto con un fuego (que tiene la _Unidad Funcional de ataque_), se le puede añadir un Modificador llamado "quemadura". Este Modificador restará 1 punto de vida al jugador cada segundo durante 10 segundos, utilizando la función "quitar_vida" de la _Unidad Funcional de vida_.

### Módulo
Los **Módulos** son objetos independientes que pueden ser combinados con otros módulos para generar nuevos comportamientos. Pueden contener Unidades Funcionales y Modificadores, y también pueden ser combinados para crear módulos más complejos.

**Ejemplo:** Para construir una ciudad en el juego, comenzamos creando módulos individuales como mesas, puertas, ventanas y camas. Estos elementos pueden tener comportamientos específicos si se les añaden Unidades Funcionales, como la capacidad de ser destruidos. Luego, creamos un módulo "cuarto" que organiza los diferentes módulos (mesa, puerta, etc.). Posteriormente, creamos un módulo "casa" que organiza los módulos de cuartos, y así sucesivamente, hasta construir una ciudad completa.

## Ventajas frente a otros patrones de diseño aplicados a videojuegos
1. **Flexibilidad y Reutilización**: Al dividir las funcionalidades en Unidades Funcionales y Modificadores, este patrón permite una gran reutilización de componentes y facilita la extensión de funcionalidades sin necesidad de modificar el código existente.
2. **Mantenimiento Sencillo**: El modularidad de este patrón hace que el mantenimiento del código sea más sencillo. Las Unidades Funcionales y Modificadores pueden ser actualizados o reemplazados independientemente, reduciendo el riesgo de introducir errores en el sistema.
3. **Composición Dinámica**: Los módulos pueden ser combinados y recompuestos de diversas maneras para crear nuevos comportamientos y funcionalidades. Esto permite una gran flexibilidad a la hora de diseñar y modificar el juego.
4. **Escalabilidad**: Este patrón es altamente escalable, permitiendo añadir nuevas Unidades Funcionales y Modificadores sin afectar negativamente el rendimiento o la estructura del juego.

## ¿Qué lo hace único?
El **Patrón de Diseño Modular Compuesto Extensible** se distingue por su combinación innovadora de varios conceptos de otros patrones de diseño, como el Decorator, Composite y Strategy. Lo que lo hace único es su enfoque en:

1. **Unidades Funcionales**: Estos componentes básicos definen funcionalidades esenciales y pueden ser reutilizados en diferentes módulos.
2. **Modificadores**: Permiten la modificación dinámica y específica de Unidades Funcionales, añadiendo una capa adicional de flexibilidad.
3. **Módulos Compuestos**: La capacidad de crear jerarquías complejas de módulos que pueden ser fácilmente combinados y recompuestos para crear comportamientos sofisticados.

Este enfoque modular y extensible es particularmente adecuado para videojuegos, donde la capacidad de añadir y modificar componentes de manera rápida y eficiente es crucial para el desarrollo y evolución continua del juego.

AUN SE ESTA TRABAJANDO 
