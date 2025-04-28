<!--
Meta Description: # Entendendo o "super" em Kotlin: A Palavra-Chave para Acesso a Superclasses ## Sinopse O "super" é uma palavra-chave fundamental em Kotlin que permit...
Meta Keywords: superclasse, super, uma, kotlin, val
-->

# Entendendo o "super" em Kotlin: A Palavra-Chave para Acesso a Superclasses

## Sinopse
O "super" é uma palavra-chave fundamental em Kotlin que permite acessar membros (métodos e propriedades) de uma superclasse a partir de uma subclasse. Essa funcionalidade é essencial para implementar herança e reutilização de código em programação orientada a objetos.

## Documentação
O "super" é utilizado quando uma classe herda de outra classe e você precisa chamar métodos ou acessar propriedades da classe pai. Essa palavra-chave é especialmente útil quando há uma sobreposição de métodos entre a superclasse e a subclasse, permitindo que você especifique qual versão do método deseja invocar.

### Propósito
- Facilitar o acesso a membros da superclasse.
- Permitir a chamada de construtores da superclasse.
  
### Uso
A palavra-chave "super" é utilizada da seguinte forma:

- Para chamar um método da superclasse:
  ```kotlin
  super.nomeDoMetodo()
  ```
- Para acessar uma propriedade da superclasse:
  ```kotlin
  val valor = super.propriedade
  ```
- Para chamar o construtor da superclasse dentro do construtor da subclasse:
  ```kotlin
  class SubClasse : SuperClasse() {
      init {
          super.construtorDaSuperClasse(parametros)
      }
  }
  ```

### Detalhes
- O uso do "super" é obrigatório quando os métodos ou propriedades da superclasse foram sobrescritos na subclasse e você deseja acessar a versão original.
- O "super" deve ser usado em um contexto onde a subclasse esteja sendo definida.

## Exemplos

### Exemplo 1: Chamando um Método da Superclasse
```kotlin
open class Animal {
    open fun fazerSom() {
        println("Animal faz som")
    }
}

class Cachorro : Animal() {
    override fun fazerSom() {
        super.fazerSom() // Chama o método da superclasse
        println("Cachorro late")
    }
}

fun main() {
    val cachorro = Cachorro()
    cachorro.fazerSom()
}
```

### Exemplo 2: Acessando uma Propriedade da Superclasse
```kotlin
open class Veiculo(val tipo: String) {
    open fun info() {
        println("Tipo de veiculo: $tipo")
    }
}

class Carro(tipo: String, val marca: String) : Veiculo(tipo) {
    override fun info() {
        super.info() // Chama a propriedade da superclasse
        println("Marca do carro: $marca")
    }
}

fun main() {
    val carro = Carro("Automóvel", "Toyota")
    carro.info()
}
```

### Exemplo 3: Chamando o Construtor da Superclasse
```kotlin
open class Pessoa(val nome: String) {
    init {
        println("Pessoa criada: $nome")
    }
}

class Estudante(nome: String, val matricula: String) : Pessoa(nome) {
    init {
        println("Estudante matriculado: $matricula")
    }
}

fun main() {
    val estudante = Estudante("Alice", "12345")
}
```

## Explicação
Um erro comum ao utilizar "super" é tentar acessá-lo fora do contexto de uma classe que realmente estende outra. Além disso, é importante lembrar que caso um método ou propriedade não seja sobrescrito, o uso do "super" não é necessário. Outro ponto a considerar é que "super" só pode ser usado se a superclasse realmente contiver o método ou a propriedade referida.

## Resumo em Uma Linha
A palavra-chave "super" em Kotlin é utilizada para acessar membros e construtores de uma superclasse a partir de uma subclasse, facilitando a implementação da herança.