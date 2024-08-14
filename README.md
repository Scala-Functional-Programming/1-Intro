# 1-Scala-Basics
0. [Crear primera aplicación en Scala](#schema0)
1. [Values, Variables and Types](#schema1)
2. [Expressions](#schema2)

[REF](#schemaref)


<hr>

<a name="schema0"></a>

## 0. Crear primera aplicación en Scala
### **Paso 1:Configurar un Proyecto Scala*
1. Crea un nuevo directorio para tu proyecto.
2. Abre Visual Studio Code y navega hasta el directorio de tu proyecto.
3. Abre una nueva terminal en Visual Studio Code: ve a `"Terminal" > "Nueva Terminal"`.
4. En la terminal, ejecuta el siguiente comando para crear un nuevo proyecto Scala usando sbt (Scala Build Tool):
```bash
sbt new scala/scala-seed.g8
```
5. Sigue las instrucciones en la terminal para proporcionar un nombre para tu proyecto.
6. Espera a que sbt descargue las dependencias y cree la estructura del proyecto.
### **Paso 2: Explorar el Proyecto Creado**
Después de crear el proyecto, verás una estructura de directorios similar a esta:

```css

mi-proyecto/
  ├── build.sbt
  ├── project/
  │   └── build.properties
  └── src/
      └── main/
          └── scala/
              └── miapp/
                  └── Hello.scala
```
- `project/`: Este directorio contiene los archivos de configuración de SBT.
- `src/main/scala/miapp`: Aquí es donde colocarás tu código fuente Scala. Verás un archivo `Main.scala` como punto de entrada para tu aplicación.
- `target/`: Este directorio contendrá los archivos compilados y otros artefactos generados por SBT.
### **Paso 3: Escribir y Ejecutar tu Código**
1. Abre el archivo Main.scala ubicado en `src/main/scala/miapp`.
2. Escriba tu código Scala dentro de este archivo. Puedes modificar el contenido existente o escribir tu propio código.
3. Guarda el archivo (Ctrl+S).
4. Para compilar y ejecutar tu aplicación, abre una terminal en Visual Studio Code y ejecuta el siguiente comando:
```bash
sbt run
```
Esto compilará y ejecutará tu aplicación Scala. Verás la salida de tu aplicación en la terminal.



<hr>

<a name="schema1"></a>

## 1. Values, Variables and Types

[Código](./var-types/src/main/scala/miapp/basics/ValuesVariablesTypes.scala)

En Scala, las variables se definen usando val o var:

- `val`: Define una variable inmutable (similar a una constante). Una vez asignado un valor, no puede cambiar.

    ```scala
    val x = 10  // x no puede ser reasignado
    ```
- `var`: Define una variable mutable. Puedes reasignar un valor a la variable.

    ```scala
    var y = 20  // y puede ser reasignado
    y = 30
    ```
### Tipos de Variables
Scala es un lenguaje tipado estáticamente, lo que significa que el tipo de cada variable se determina en tiempo de compilación. Los tipos más comunes son:

- Númericos:
    - Int: Enteros (ej. 42)
    - Double: Números de punto flotante (ej. 3.14)
    - Float: Números de punto flotante de menor precisión.
    - Long: Enteros grandes.
    - Short, Byte: Enteros pequeños.
- Boolean:
    - Boolean: Valores true o false.
- Carácter y Cadena:
    - Char: Un solo carácter (ej. 'A')
    - String: Secuencia de caracteres (ej. "Hola, Scala!")
- Otros tipos:
    - Unit: Similar a void en otros lenguajes; indica ausencia de un valor significativo.
    - Option[T]: Representa un valor que puede estar presente (Some) o ausente (None).
    - Tuple: Agrupa varios valores (de diferentes tipos) en una sola variable.
- Inferencia de tipos

Scala tiene inferencia de tipos, lo que significa que no siempre es necesario especificar el tipo de una variable; el compilador puede deducirlo:

```scala
val name = "Scala"  // El tipo se infiere como String
```
Sin embargo, puedes especificar el tipo explícitamente si es necesario:

```scala
val age: Int = 30
```
<hr>

<a name="schema2"></a>

## 2.Expressions

En Scala, **todo es una expresión**, lo que significa que casi todas las construcciones del lenguaje devuelven un valor. Esto contrasta con otros lenguajes donde hay una distinción entre expresiones (que devuelven un valor) y sentencias (que no lo hacen).

### Características clave de las expresiones en Scala:
- Expresiones de Bloque: Un bloque de código { ... } es una expresión, y su valor es el resultado de la última expresión dentro del bloque.

    ```scala
    val result = {
    val x = 10
    val y = 20
    x + y  // El valor del bloque es 30
    }
    ```
- Condicionales: El if es una expresión que devuelve un valor, lo que permite asignar su resultado directamente a una variable.

```scala
val max = if (a > b) a else b
```
- Match Expression: Similar a un `switch`, pero más poderoso. Es una expresión que devuelve un valor basado en patrones.

    ```scala
    val day = "Monday"
    val activity = day match {
    case "Monday" => "Work"
    case "Saturday" => "Relax"
    case _ => "Unknown"
    }
    ```
- Expresiones funcionales: Las funciones anónimas `lambdas` y las funciones nombradas también son expresiones.

    ```scala
    val square = (x: Int) => x * x
    ```
### Ventaja principal
Como todo es una expresión, Scala permite escribir código más conciso y funcional. Por ejemplo, puedes asignar directamente el resultado de una operación a una variable, hacer uso de condicionales dentro de asignaciones, o procesar flujos de datos de manera más natural.

En resumen, las expresiones en Scala facilitan la escritura de código limpio, conciso y expresivo, con un fuerte enfoque en la inmutabilidad y el estilo funcional.
















<hr>

<a name="schemaref"></a>

[REF](https://www.udemy.com/course/rock-the-jvm-scala-for-beginners/)