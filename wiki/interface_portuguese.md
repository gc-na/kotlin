<!--
Meta Description: # Interfaces em Kotlin: Definição, Uso e Exemplos Práticos ## Sinopse As interfaces em Kotlin são contratos que definem um conjunto de métodos que uma...
Meta Keywords: interface, que, kotlin, métodos, interfaces
-->

# Interfaces em Kotlin: Definição, Uso e Exemplos Práticos

## Sinopse
As interfaces em Kotlin são contratos que definem um conjunto de métodos que uma classe deve implementar, permitindo a implementação de múltiplos comportamentos e a criação de código mais flexível e reutilizável.

## Documentação
Em Kotlin, uma interface é um tipo que pode conter declarações de métodos e propriedades. As interfaces podem ser implementadas por classes, permitindo que essas classes forneçam a implementação dos métodos definidos na interface. Isso promove a abstração e o polimorfismo.

### Propósito
As interfaces em Kotlin são utilizadas para:
- Definir um comportamento comum que várias classes podem implementar.
- Permitir a implementação de múltiplas interfaces por uma única classe.
- Facilitar a criação de código desacoplado e testável.

### Uso
Para declarar uma interface em Kotlin, utiliza-se a palavra-chave `interface`, seguida pelo nome da interface e, opcionalmente, um bloco de código que contém as declarações dos métodos e propriedades. Os métodos em uma interface não possuem corpo, exceto se forem métodos padrão (com implementação).

```kotlin
interface ExemploInterface {
    fun metodoExemplo()
    val propriedadeExemplo: String
}
```

Para implementar uma interface em uma classe, utiliza-se a palavra-chave `:`, seguida pelo nome da interface. A classe deve fornecer a implementação dos métodos e propriedades definidos na interface.

```kotlin
class ExemploClasse : ExemploInterface {
    override fun metodoExemplo() {
        println("Implementação do método exemplo.")
    }

    override val propriedadeExemplo: String
        get() = "Valor da propriedade exemplo"
}
```

## Exemplos

### Exemplo Básico de Interface
```kotlin
interface Animal {
    fun fazerSom()
}

class Cachorro : Animal {
    override fun fazerSom() {
        println("Au Au!")
    }
}

fun main() {
    val meuCachorro = Cachorro()
    meuCachorro.fazerSom() // Saída: Au Au!
}
```

### Interface com Propriedades
```kotlin
interface Veiculo {
    val tipo: String
    fun acelerar()
}

class Carro : Veiculo {
    override val tipo: String
        get() = "Carro"

    override fun acelerar() {
        println("Acelerando o carro!")
    }
}

fun main() {
    val meuCarro = Carro()
    println(meuCarro.tipo) // Saída: Carro
    meuCarro.acelerar() // Saída: Acelerando o carro!
}
```

## Explicação
Ao utilizar interfaces, é importante notar que:
- Uma classe pode implementar várias interfaces, o que permite um design mais flexível.
- É necessário usar a palavra-chave `override` ao implementar métodos e propriedades da interface.
- Interfaces não podem conter estado (variáveis de instância) a não ser que sejam propriedades com getters e setters.
- Métodos na interface são implicitamente `abstract` e `public`, enquanto as propriedades são `abstract` por padrão.

Um erro comum é esquecer de usar `override` ao implementar métodos, o que resultará em um erro de compilação.

## Resumo em Uma Frase
As interfaces em Kotlin permitem definir contratos de comportamento que podem ser implementados por diversas classes, promovendo a reutilização e flexibilidade do código.