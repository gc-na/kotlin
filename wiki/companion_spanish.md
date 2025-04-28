<!--
Meta Description: # Companion en Kotlin: Todo lo que Necesitas Saber ## Sinopsis El uso de `companion` en Kotlin permite definir miembros estáticos dentro de una clase,...
Meta Keywords: companion, object, miembros, clase, kotlin
-->

# Companion en Kotlin: Todo lo que Necesitas Saber

## Sinopsis
El uso de `companion` en Kotlin permite definir miembros estáticos dentro de una clase, lo que facilita la creación de métodos y propiedades que pueden ser accedidos sin necesidad de instanciar la clase.

## Documentación
En Kotlin, el concepto de `companion object` se utiliza para crear una clase interna que actúa como un contenedor para miembros estáticos. Esto es útil cuando se necesita agrupar funciones o propiedades que son relevantes para la clase, pero que no dependen de una instancia específica de la misma.

### Propósito
El `companion object` permite que los elementos dentro de él sean accesibles de manera estática, similar a los miembros estáticos en otros lenguajes de programación como Java. Esto es especialmente útil para crear métodos de fábrica y constantes.

### Uso
Para declarar un `companion object`, se utiliza la palabra clave `companion` seguida de un bloque de código. A continuación se muestra la sintaxis básica:

```kotlin
class MiClase {
    companion object {
        const val CONSTANTE = "Soy una constante"
        
        fun metodoEstático() {
            println("Método estático llamado")
        }
    }
}
```

Los miembros del `companion object` se pueden acceder directamente utilizando el nombre de la clase:

```kotlin
fun main() {
    println(MiClase.CONSTANTE) // Salida: Soy una constante
    MiClase.metodoEstático()    // Salida: Método estático llamado
}
```

## Ejemplos
### Ejemplo Básico
```kotlin
class Persona {
    companion object {
        var contador = 0
        
        fun crearPersona(): Persona {
            contador++
            return Persona()
        }
    }
}

fun main() {
    val persona1 = Persona.crearPersona()
    val persona2 = Persona.crearPersona()
    
    println("Número de personas creadas: ${Persona.contador}") // Salida: Número de personas creadas: 2
}
```

### Ejemplo con Propiedades
```kotlin
class Configuracion {
    companion object {
        const val VERSION = "1.0.0"
        
        fun mostrarVersion() {
            println("Versión de la aplicación: $VERSION")
        }
    }
}

fun main() {
    Configuracion.mostrarVersion() // Salida: Versión de la aplicación: 1.0.0
}
```

## Explicación
Al utilizar `companion object`, es importante tener en cuenta algunos aspectos:

- **Acceso a miembros de instancia**: Los miembros del `companion object` no pueden acceder a los miembros de instancia de la clase sin una referencia a una instancia de la clase.
- **Nombre del companion**: Si no se asigna un nombre al `companion object`, se puede acceder a sus miembros de forma directa utilizando el nombre de la clase. Sin embargo, si se asigna un nombre, los miembros deben ser accedidos utilizando ese nombre.
  
Ejemplo de un `companion object` con nombre:
```kotlin
class Ejemplo {
    companion object MiCompanion {
        fun imprimir() {
            println("Desde MiCompanion")
        }
    }
}

fun main() {
    Ejemplo.MiCompanion.imprimir() // Salida: Desde MiCompanion
}
```

## Resumen en una línea
El `companion object` en Kotlin permite definir miembros estáticos dentro de una clase, facilitando el acceso a funciones y propiedades sin necesidad de instanciar la clase.