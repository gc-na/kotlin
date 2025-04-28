<!--
Meta Description: # Sellos en Kotlin: Entendiendo la Clase Sellada ## Sinopsis Las clases selladas en Kotlin permiten representar un conjunto restringido de tipos, ofre...
Meta Keywords: estado, resultado, las, que, clases
-->

# Sellos en Kotlin: Entendiendo la Clase Sellada

## Sinopsis
Las clases selladas en Kotlin permiten representar un conjunto restringido de tipos, ofreciendo un control más preciso sobre el comportamiento de las jerarquías de clases. Esto es especialmente útil en situaciones donde se necesita limitar las subclases a un número fijo.

## Documentación
Las clases selladas se declaran usando la palabra clave `sealed`. Su propósito principal es proporcionar una forma de definir un tipo que puede tener un número limitado de subtipos. Esto es beneficioso para patrones de diseño como el **patrón de estado** o el **patrón de comando**, donde se requiere un conjunto específico de variaciones de un objeto.

Una clase sellada solo puede tener subclases definidas dentro del mismo archivo. Esto asegura que todas las posibles subclases sean conocidas y se puedan manejar de manera segura, lo que a su vez mejora la legibilidad y mantenibilidad del código.

### Sintaxis
```kotlin
sealed class NombreDeLaClaseSellada {
    // Subclases
}
```

### Uso
Para utilizar una clase sellada, se define la clase usando la palabra clave `sealed`, seguida de la declaración de las subclases que heredan de ella. Estas subclases pueden ser clases normales, clases de datos o incluso objetos.

## Ejemplos

### Ejemplo Básico
```kotlin
sealed class Resultado {
    data class Exito(val mensaje: String) : Resultado()
    data class Error(val codigo: Int, val mensaje: String) : Resultado()
}

fun manejarResultado(resultado: Resultado) {
    when (resultado) {
        is Resultado.Exito -> println("Éxito: ${resultado.mensaje}")
        is Resultado.Error -> println("Error ${resultado.codigo}: ${resultado.mensaje}")
    }
}
```

### Ejemplo con Objetos
```kotlin
sealed class Estado {
    object Cargando : Estado()
    object Listo : Estado()
    data class Error(val mensaje: String) : Estado()
}

fun mostrarEstado(estado: Estado) {
    when (estado) {
        is Estado.Cargando -> println("Cargando...")
        is Estado.Listo -> println("Listo para usar.")
        is Estado.Error -> println("Error: ${estado.mensaje}")
    }
}
```

## Explicación
Al utilizar clases selladas, es importante recordar que:

1. **Restricción de Subclases**: Todas las subclases deben estar definidas en el mismo archivo que la clase sellada, lo que puede ser un inconveniente si se necesita extender el comportamiento en otros archivos.
   
2. **Exhaustividad en When**: Al utilizar una expresión `when` para manejar un tipo sellado, el compilador puede verificar que todos los casos posibles se han manejado, lo que reduce errores en tiempo de ejecución.

3. **Uso en Librerías**: Dado su comportamiento predecible, las clases selladas son ideales para ser utilizadas en librerías y API donde se desee garantizar un comportamiento específico.

## Resumen en Una Línea
Las clases selladas en Kotlin permiten definir un conjunto limitado de subtipos, mejorando la seguridad y la claridad en la gestión de jerarquías de tipos.