<!--
Meta Description: # O Que é "init" em Kotlin: Compreenda o Construtor Primário ## Sinopse O "init" em Kotlin é um bloco de inicialização que permite executar código dur...
Meta Keywords: init, que, uma, bloco, kotlin
-->

# O Que é "init" em Kotlin: Compreenda o Construtor Primário

## Sinopse
O "init" em Kotlin é um bloco de inicialização que permite executar código durante a criação de um objeto, sendo parte fundamental do construtor primário. Este recurso facilita a configuração inicial de propriedades de uma classe, garantindo que o objeto esteja em um estado consistente após sua criação.

## Documentação
Em Kotlin, o bloco "init" é utilizado dentro da declaração de uma classe para definir ações que devem ser realizadas sempre que uma instância da classe é criada. Ao contrário dos construtores tradicionais em outras linguagens, o "init" não precisa ser explicitamente declarado com uma palavra-chave diferente; ele faz parte do construtor primário.

### Propósito
O principal objetivo do bloco "init" é permitir a execução de código de inicialização, como atribuições de valores a propriedades ou chamadas a métodos, logo após a criação do objeto.

### Uso
Aqui está a sintaxe básica do uso do bloco "init":

```kotlin
class NomeDaClasse(val propriedade: Tipo) {
    init {
        // Código de inicialização
    }
}
```

Dentro do bloco "init", você pode acessar as propriedades da classe e realizar várias operações de inicialização.

## Exemplos

### Exemplo 1: Inicialização Simples

```kotlin
class Pessoa(val nome: String, val idade: Int) {
    init {
        println("Nome: $nome, Idade: $idade")
    }
}

fun main() {
    val pessoa = Pessoa("João", 30)
    // Saída: Nome: João, Idade: 30
}
```

### Exemplo 2: Validação de Propriedades

```kotlin
class Produto(val nome: String, val preco: Double) {
    init {
        require(preco >= 0) { "O preço não pode ser negativo." }
    }
}

fun main() {
    val produto = Produto("Camiseta", 29.99)
    // Produto criado com sucesso.
}
```

## Explicação
Uma armadilha comum ao usar o bloco "init" é esquecer que ele é executado antes de qualquer outro método da classe. Portanto, se você tentar acessar uma propriedade que ainda não foi inicializada, isso pode levar a erros. Além disso, é importante lembrar que múltiplos blocos "init" podem ser usados em uma única classe, e eles serão executados na ordem em que aparecem.

Outra consideração é que o bloco "init" não pode ser utilizado diretamente como um construtor separado; ele só pode ser usado como parte do construtor primário.

## Resumo em Uma Linha
O bloco "init" em Kotlin permite executar código de inicialização e configurar propriedades durante a criação de uma instância de classe.