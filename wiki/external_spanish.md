<!--
Meta Description: # Kotlin: Uso de la palabra clave "external" ## Sinopsis La palabra clave `external` en Kotlin se utiliza para declarar funciones y propiedades que es...
Meta Keywords: kotlin, external, que, externa, palabra
-->

# Kotlin: Uso de la palabra clave "external"

## Sinopsis
La palabra clave `external` en Kotlin se utiliza para declarar funciones y propiedades que están implementadas en otro lenguaje, generalmente C o C++. Esto permite la interoperabilidad entre Kotlin y código nativo, facilitando el uso de bibliotecas y APIs que no están escritas en Kotlin.

## Documentación
La palabra clave `external` se aplica a funciones y propiedades que no tienen una implementación en Kotlin. En su lugar, se espera que la implementación se proporcione en otro lugar, como en una biblioteca nativa. Esto es especialmente útil en el desarrollo de aplicaciones que necesitan interactuar con código de bajo nivel o con sistemas operativos.

### Propósito
El propósito de `external` es permitir que los desarrolladores de Kotlin utilicen código nativo sin necesidad de reescribirlo en Kotlin. Esto es fundamental para aplicaciones que requieren alta eficiencia o acceso a APIs específicas del sistema.

### Uso
Para declarar una función o propiedad como `external`, simplemente se precede su declaración con la palabra clave `external`. Es importante tener en cuenta que las funciones externas deben ser utilizadas con precaución, ya que carecen de implementación directa en Kotlin.

#### Ejemplo de declaración de función externa:
```kotlin
external fun nativeFunction(param: Int): String
```

#### Ejemplo de declaración de propiedad externa:
```kotlin
external val nativeProperty: Int
```

## Ejemplos
A continuación, se muestran ejemplos básicos de cómo utilizar la palabra clave `external` en Kotlin.

### Ejemplo 1: Función externa
```kotlin
// Declaración de una función externa
external fun getCurrentTime(): Long

fun main() {
    // Llamada a la función externa
    val currentTime = getCurrentTime()
    println("Current Time: $currentTime")
}
```

### Ejemplo 2: Propiedad externa
```kotlin
// Declaración de una propiedad externa
external val version: String

fun main() {
    // Uso de la propiedad externa
    println("Kotlin Version: $version")
}
```

## Explicación
Al utilizar `external`, es fundamental recordar que:

- **Compilación**: La función o propiedad externa debe estar disponible en el entorno de ejecución. Si no se encuentra la implementación, se producirán errores en tiempo de ejecución.
- **Interoperabilidad**: Aunque `external` permite la interoperabilidad, se deben manejar cuidadosamente los tipos de datos. Kotlin y C/C++ tienen diferenciales en la representación de tipos, lo que puede causar problemas si no se gestionan adecuadamente.
- **Plataformas**: Asegúrate de que tu entorno de desarrollo soporte la llamada a código nativo. Esto es especialmente relevante al trabajar con plataformas como Android o aplicaciones de escritorio.

## Resumen en una línea
La palabra clave `external` en Kotlin permite declarar funciones y propiedades que son implementadas en código nativo, facilitando la interoperabilidad con bibliotecas y APIs no escritas en Kotlin.