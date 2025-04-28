<!--
Meta Description: # Delegación en Kotlin: Todo lo que Necesitas Saber ## Sinopsis La delegación en Kotlin es una poderosa característica que permite a una clase delegar...
Meta Keywords: delegación, kotlin, accion, fun, empleado
-->

# Delegación en Kotlin: Todo lo que Necesitas Saber

## Sinopsis
La delegación en Kotlin es una poderosa característica que permite a una clase delegar la implementación de ciertos comportamientos a otra clase. Esto promueve la reutilización de código y facilita la implementación de patrones de diseño como el patrón Delegado.

## Documentación
La delegación en Kotlin se puede implementar de varias maneras, siendo las más comunes la delegación de propiedades y la delegación de interfaces.

### Delegación de Propiedades
Kotlin permite delegar la implementación de propiedades a un objeto. Esto se logra mediante el uso de la palabra clave `by`. La delegación de propiedades es especialmente útil para delegar la lógica de acceso y almacenamiento a una propiedad.

**Uso Básico:**
```kotlin
class Usuario {
    var nombre: String by Delegates.observable("Sin Nombre") { prop, viejo, nuevo ->
        println("$viejo -> $nuevo")
    }
}
```
En este ejemplo, la propiedad `nombre` es delegada a `Delegates.observable`, que permite ejecutar un bloque de código cada vez que el valor cambia.

### Delegación de Interfaces
También es posible delegar la implementación de interfaces. Esto se hace implementando una interfaz y pasando su implementación a través de un objeto delegado.

**Uso Básico:**
```kotlin
interface Accion {
    fun ejecutar()
}

class AccionReal : Accion {
    override fun ejecutar() {
        println("Acción ejecutada")
    }
}

class Delegador(accion: Accion) : Accion {
    private val accionDelegada = accion

    override fun ejecutar() {
        accionDelegada.ejecutar()
    }
}
```
Aquí, `Delegador` implementa la interfaz `Accion` y delega la llamada al método `ejecutar` a un objeto de tipo `Accion`.

## Ejemplos
### Ejemplo de Delegación de Propiedades
```kotlin
import kotlin.properties.Delegates

class Empleado {
    var salario: Double by Delegates.vetoable(30000.0) { _, _, nuevo ->
        nuevo >= 0
    }
}

fun main() {
    val empleado = Empleado()
    empleado.salario = 35000.0 // Aceptado
    println(empleado.salario) // Imprime 35000.0
    empleado.salario = -5000.0 // Rechazado
    println(empleado.salario) // Sigue siendo 35000.0
}
```

### Ejemplo de Delegación de Interfaces
```kotlin
interface Logger {
    fun log(mensaje: String)
}

class ConsoleLogger : Logger {
    override fun log(mensaje: String) {
        println("Log: $mensaje")
    }
}

class App(private val logger: Logger) {
    fun iniciar() {
        logger.log("La aplicación ha comenzado")
    }
}

fun main() {
    val logger = ConsoleLogger()
    val app = App(logger)
    app.iniciar() // Imprime: Log: La aplicación ha comenzado
}
```

## Explicación
Al utilizar la delegación en Kotlin, es importante tener en cuenta algunos puntos:

1. **Cuidado con la Mutabilidad**: Si la propiedad delegada es mutable, asegúrate de manejar correctamente su estado para evitar inconsistencias.
2. **Delegación Cíclica**: Evita crear una situación donde dos objetos se deleguen mutuamente, lo que puede llevar a ciclos infinitos o a un comportamiento inesperado.
3. **Uso de Delegados Estándar**: Kotlin proporciona varios delegados estándar (como `lazy`, `observable`, `vetoable`) que pueden simplificar tu código y mejorar su legibilidad.

## Resumen en Una Línea
La delegación en Kotlin permite reutilizar código y simplificar la implementación de propiedades y comportamientos al delegar su lógica a otros objetos.