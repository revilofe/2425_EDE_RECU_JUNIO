# 2425 - Recuperación de entornos de desarrollo - DAW


Edita este archivo y responde a las siguientes preguntas. Luego, sube los cambios

## RA1 (1 Punto)

### 1. (0,4 - 5 min) ¿Cómo interactúan los distintos elementos de un ordenador durante la ejecución de un programa software? Describe el proceso desde que se ejecuta un programa hasta que pasa a ejecutarse y termina.

*Respuesta a la pregunta 1. (mínimo 300 palabras)*


---

### 2. (0,6 - 10 min) Características de los siguientes Lenguajes de Programación: Python, Java, C, JavaScript. Habla sobre aspectos relaciondos con (Nivel de abstracción, Modo de ejecución, Paradigmas, Caracteristicas, 
Un ejemplo: Kotlin
#### Kotlin — Ficha de características

| Aspecto                         | Descripción detallada                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| ------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Nivel de abstracción**        | Lenguaje **de alto nivel**: se programa pensando en objetos y funciones, no en registros ni punteros. No obstante, conserva “puertas de servicio” (JNI, Kotlin/Native, `ByteBuffer`) para descender a bajo nivel cuando toca trabajar con C o controlar memoria manualmente.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| **Modo de ejecución**           | 1. **JVM-bytecode**: el compilador genera bytecode y el *HotSpot JIT* optimiza en tiempo de ejecución.<br>2. **Kotlin/Native**: *AOT* a binarios nativos para iOS, Linux, Windows, etc., sin máquina virtual.<br>3. **Kotlin/JS**: transpilación a JavaScript para front-ends web.<br>4. **Kotlin Multiplatform (KMP)**: un único código común + “expect/actual” para cada plataforma.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| **Paradigmas soportados**       | - **Orientado a objetos** (clases, herencia, interfaces).<br>- **Funcional** (funciones de orden superior, inmutabilidad, `map/reduce`, lambdas, *currying* light).<br>- **Reactivo/asincrónico**: *coroutines* y *flows* como ciudadanos de primera.<br>- **Basado en componentes/DSL**: gracias a funciones de extensión y receptores implícitos, escribir *mini-lenguajes* (DSL) es natural.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| **Características distintivas** | • **Null Safety**: el compilador no deja que un `null` se cuele sin tu permiso (`?`, `!!`).<br>• **Type Inference**: escribe `val saludo = "Hola"` y te olvidas de `String`.<br>• **Data Classes & Records**: `data class Usuario(val id:Int, val nombre:String)` genera `equals`, `hashCode`, `copy`, `toString` y *componentN*.<br>• **Coroutines**: concurrencia ligera.<br>• **Extension Functions/Properties**: añade métodos a clases ajenas sin herencia ni patrón Decorator.<br>• **Interoperabilidad total con Java**: usa cualquier librería Java como si fuera nativa, y viceversa.<br>• **Compilación incremental** y *gradle-friendly*: ciclos de feedback rápidos.<br>• **Kotlin 2.x** (2024-25): *K2* compiler, velocidad de compilación mejorada, inferencia de tipos más potente y nuevo *frontend* unificado. |



*Respuesta a la pregunta 2. (mínimo 300 palabras)*

---

---


## RA2 (1 Punto)

### 3. (0,3 - 5 min) ¿Qué significa IDE? ¿Qué es?

*Respuesta a la pregunta 3. (mínimo 300 palabras)*

---

### 4. (0,7 - 10 min) Lista y explica en qué consisten 5 características clave de los IDEs (Por ejemplo: Tienen opciones para depurar, Pueden automatizar tareas…. Estos ejemplos no puedes usarlos)

*Respuesta a la pregunta 4. (mínimo 300 palabras)*

---

---

## RA3 (1 Punto)

### 5. (0,5 - 20 min) Se presenta un código en Kotlin con funciones para calcular la sumatoria y el factorial de un número. Sin embargo, el código contiene errores. El objetivo es utilizar el depurador para:

* Identificar los errores en la lógica de las funciones.
* Comprender cómo afectan estos errores a los resultados finales.
* Corregir los errores y comprobar que el programa funciona correctamente.

Definiciones:

- Factorial: El factorial de un número entero positivo `n` (representado como `n!`) es el producto de todos los números enteros positivos desde `1` hasta `n`. Ejemplo: `4! = 4 × 3 × 2 × 1 = 24`.

- Sumatoria: La sumatoria de un número entero positivo `n` es la suma de todos los números enteros positivos desde `1` hasta `n`. Ejemplo: La sumatoria de `4` es `1 + 2 + 3 + 4 = 10`.

```kotlin 
//Código con errores intencionales  
fun main() {  
println("Introduce un número para calcular sumatoria y factorial:")  
val numero = readLine()?.toIntOrNull()

    if (numero == null || numero < 0) {  
    println("Introduce un número válido positivo.")  
    } else {  
val sumatoria = calcularSumatoria(numero)  
val factorial = calcularFactorial(numero)  
println("La sumatoria de 1 hasta $numero es: $sumatoria")  
println("El factorial de $numero es: $factorial")  
    
}

// Función sumatoria con errores intencionales  
fun calcularSumatoria(n: Int): Int {  
    var suma = 1           
    for (i in 1..n - 1) { 
    suma -= i}  
    return suma  
}

// Función calcular el factorial con errores intencionales  
fun calcularFactorial(n: Int): Int {  
    var resultado = 0      
    for (i in 0..n) {      
        resultado *= 1     
    }  
    return resultado  
}

// Función factorial con errores intencionales  
fun factorial(n: Int): Int {  
    var resultado = 0  
    for (i in 0..n) {  
        resultado *= 1  
    }  
    return resultado  
}
``` 

**Entrega:**


1. El código corregido

    *Respuesta a la pregunta 5.1*


2. Cada error identificado.

    *Respuesta a la pregunta 5.2*


3. Captura pantalla usando el debug.

    *Respuesta a la pregunta 5.3*


---



### 6. (0,5 - 20 min) Partiendo del código resultado del ejercicio anterior, se te pide que escribas tests unitarios utilizando el framework Kotest para validar el correcto funcionamiento de las funciones `calcularSumatoria` y `calcularFactorial`.

¿Qué se quiere probar?

Para la función calcularSumatoria:

* Que devuelva la suma correcta de los números desde 1 hasta n.
* Que devuelva 0 cuando el número de entrada es 0\.

Para la función calcularFactorial:

* Que devuelva el producto correcto de los números desde 1 hasta n.
* Que devuelva 1 cuando el número de entrada es 0, ya que el factorial de 0 es 1\.

**Entrega:**

1. El código de los test desarrollados

   *Respuesta a la pregunta 6.1*


2. Captura de pantalla del resultado de ejecutar los test.

   *Respuesta a la pregunta 6.2*


---

---

## RA4 (1 Puntos)

### 7. (0,35 - 20 min) Partiendo del código corregido, se ha detectado un Code Smell (mal olor del código) que debéis identificado y corregir.

Pista:

* Code Smell identificado: Código Duplicado (Duplicate Code).
* Patrón de refactorización a aplicar: Extraer Método (Extract Method).

**Entrega:**

1. Explicación en qué consiste el code smell *`Duplicate Code`* y el patrón de refactorización *`Extract Method`* y qué soluciona.

   *Respuesta a la pregunta 7.1*



2. El código que se ha corregido después de aplicar la refactorización.

    *Respuesta a la pregunta 7.2*

---

### 8. (0,2 - 10 min) ¿Qué espacios de trabajo tiene git y para qué sirven cada uno?

*Respuesta a la pregunta 8. (mínimo 200 palabras)*

---


### 9. (0.3 - 10 min) Estás en un repositorio local, y usas git para realizar el control de versiones de tu código. ¿Qué comando ejecutarías para estas situaciones?

Ejemplo de respuesta:
0. Inicializa un proyecto.
    + comando: `git init`

*Responde a las siguientes situaciones:*

1. Ver el historial de commits en una sola linea.
   + comando: 
   
2. Deshacer el último commit y deshacer cambios. Eliminar los cambios.
    + comando:

4. Crear la rama “featureA” y cambiar a ella.
    + comando:

5. Ver el estado del repositorio.
    + comando:

6. Clonar el repositorio `https://github.com/revilofe/HundirFlota.git`.
    + comando:

7. Descargar al repositorio local los cambios del remote `origin` rama `main`.
    + comando:

---


### 10. (0,15 - 10 min) Tienes un código que tienes que documentar. Documenta correctamente la función `factorial` utilizando KDoc (usando el formato y etiquetas de kdoc), el sistema estándar de documentación en Kotlin.

La documentación de código es una parte fundamental del desarrollo, ya que ayuda a otros desarrolladores (y a ti mismo en el futuro) a entender mejor cómo funciona una función, qué espera como entrada y qué devuelve.

**Entregar:** El código, en el que se ha documentado siguiendo el formato KDOC. Asegúrate de incluir las secciones.  
* La descripción general de la función.
* Excepción que lanza.
* Los parámetros que recibe.
* El valor de retorno que proporciona.
* Ejemplos de uso si se considera necesario.

Código base sin documentación:
```kotlin
fun factorial(n: Int): Int {
    require(n >= 0) { "El número debe ser mayor o igual a 0" } // Validación de entrada
    var resultado = 1
    for (i in 1..n) {
        resultado *= i
    }
    return resultado
}
```

*Respuesta a la pregunta 10: Código con KDoc*

---

---

## RA5 (1 Punto)

### 11. (1 - 30 min) En este ejercicio, deberás modelar la relación que puede haber en una empresa: los **departamentos** están compuestos por diferentes tipos de **empleados**, entre los cuales se distingue entre **jefes** y **subordinados**. Cada departamento puede contener múltiples empleados, y cada jefe supervisa a uno o varios subordinados. Esto tendrás que realizarlo utilizando un **diagrama de clases UML**


**Requisitos del Ejercicio**

1. **Clases Principales**:

   * Define una clase `Departamento` con sus propiedades y métodos esenciales.
   * Crea una clase base `Empleado` que contenga los atributos y métodos comunes a todos los empleados.
   * Define dos clases especializadas que son `Empleado’`s:
     * `Jefe`: Representa a los empleados con responsabilidad de supervisión.
     * `Subordinado`: Representa a los empleados bajo la supervisión de un jefe.

2. **Relaciones entre Clases**:

   * Implementa una relación entre `Departamento` y `Empleado`, indicando que un departamento puede contener múltiples empleados.
   * Define una relación entre `Empleado` y las clases `Jefe` y `Subordinado`.
   * Establece una relación donde un `Jefe` supervisa a uno o más `Subordinado`.

3. **Propiedades y Métodos**:  
   * **`Departamento`**
     * `- id: int` → Identificador único del departamento.
     * `- nombre: string` → Nombre del departamento.
     * `+ agregarEmpleado(e: Empleado): void` → Método para añadir un empleado.
     * `+ eliminarEmpleado(e: Empleado): void` → Método para eliminar un empleado.  
   * **`Empleado`**
     * `- id: int` → Identificador del empleado.
     * `- nombre: string` → Nombre del empleado.  
   * **`Jefe`**
     * `- nivel: string` → Nivel jerárquico del jefe.
     * `+ asignarTarea(): void` → Método para asignar tareas a subordinados.  
   * **`Subordinado`**
     * `+ recibirTarea(): void` → Método para recibir tareas del jefe.


**Entrega:** 
1. Imagen generada por la herramienta UML con el diagrama de clases. https://www.plantuml.com/   

    *Respuesta a la pregunta 11.1*




2. Código fuente del diagrama de clases.

    *Respuesta a la pregunta 11.2*



3. Explicación de las relaciones entre clases.

    *Respuesta a la pregunta 11.3*


---

---

## RA6 (1 Punto)

### 12. (1 - 30 min) En este ejercicio, deberás modelar el ciclo de vida de un usuario dentro de un sistema utilizando un **diagrama de estados UML**.

El sistema gestiona a los usuarios en tres estados fundamentales:

* **Activo**: El usuario tiene acceso completo al sistema.
* **Bloqueado**: El usuario ha sido restringido debido a intentos fallidos de inicio de sesión o actividad sospechosa.
* **Desactivado**: El usuario ha decidido desactivar su cuenta o esta ha sido desactivada automáticamente por inactividad prolongada.

**Requisitos del Ejercicio**

1. **Identificar los estados** en los que puede encontrarse un usuario dentro del sistema.
2. **Definir las transiciones** entre los estados, considerando las condiciones (**guardas**) y las **acciones** que se deben realizar en cada caso.
3. **Incluir las acciones de entrada y actividades internas** en los estados cuando sea necesario.

**Reglas del Negocio**

* Un usuario inicia en el estado **Activo** tras completar su registro.
* El usuario pasa a estado **Bloqueado** si supera **3 intentos fallidos** de inicio de sesión o si se detecta actividad sospechosa.
* El usuario pasa a estado **Desactivado** si solicita desactivar su cuenta o si permanece inactivo por más de **6 meses**.
* Un usuario en estado **Bloqueado** puede ser desbloqueado manualmente por un administrador o automáticamente por el sistema.
* Un usuario en estado **Desactivado** puede solicitar la reactivación de su cuenta.


**Entrega:**
1. Imagen generada por la herramienta UML con el diagrama de estados. https://www.plantuml.com/
   
   *Respuesta a la pregunta 12.1*



2. Código fuente del diagrama de estados.
   
   *Respuesta a la pregunta 12.2*



3. Explicación de estados y sus acciones/actividades, transiciones y sus guardas.
   
   *Respuesta a la pregunta 12.3*


---

---

> Recuerda que debes subir los cambios al repositorio remoto.

[Acceso a la descripción y soluciones](https://docs.google.com/document/d/1vnTLuDog6NbLF6gQCbvKI3RiIr9Yd8GTjR7aYQ8xwzY/edit?usp=sharing)
