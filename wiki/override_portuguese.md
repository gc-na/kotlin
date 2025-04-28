<!--
Meta Description: # Override em Kotlin: Compreendendo o Polimorfismo na Programação Orientada a Objetos ## Sinopse O `override` em Kotlin é uma palavra-chave utilizada ...
Meta Keywords: classe, que, override, kotlin, métodos
-->

# Override em Kotlin: Compreendendo o Polimorfismo na Programação Orientada a Objetos

## Sinopse
O `override` em Kotlin é uma palavra-chave utilizada para modificar o comportamento de métodos e propriedades herdados de uma classe pai, permitindo que uma classe filha forneça sua própria implementação.

## Documentação
Em Kotlin, a palavra-chave `override` é essencial para a implementação do polimorfismo na Programação Orientada a Objetos. Quando uma classe herda de outra classe, pode haver métodos e propriedades que precisam ser personalizados. Para fazer isso, a classe filha deve utilizar a palavra-chave `override` para indicar que está substituindo um método ou propriedade da classe pai.

### Propósito
O propósito do `override` é permitir que subtipos alterem o comportamento de métodos e propriedades definidos em supertipos, garantindo que a hierarquia de classes funcione de maneira flexível e reutilizável.

### Uso
Para usar `override`, o método ou a propriedade na classe pai deve ser marcada com a palavra-chave `open`, indicando que pode ser sobrescrito. A classe filha então define seu próprio comportamento usando `override`.

### Detalhes
- A palavra-chave `override` deve sempre ser usada em métodos ou propriedades que estão sendo substituídos.
- É possível sobrescrever métodos com diferentes implementações na classe filha, desde que a assinatura do método permaneça a mesma.
- O Kotlin proporciona uma verificação em tempo de compilação para garantir que o método que está sendo sobrescrito realmente exista na classe pai.

## Exemplos

### Exemplo 1: Sobrescrevendo um Método

```kotlin
open class Animal {
    open fun fazerSom() {
        println("O animal faz um som")
    }
}

class Cachorro : Animal() {
    override fun fazerSom() {
        println("O cachorro late")
    }
}

fun main() {
    val meuCachorro = Cachorro()
    meuCachorro.fazerSom() // Saída: O cachorro late
}
```

### Exemplo 2: Sobrescrevendo uma Propriedade

```kotlin
open class Carro {
    open val tipo: String = "Veículo"
}

class CarroEsportivo : Carro() {
    override val tipo: String = "Carro Esportivo"
}

fun main() {
    val meuCarro = CarroEsportivo()
    println(meuCarro.tipo) // Saída: Carro Esportivo
}
```

## Explicação
Um erro comum ao usar `override` é não marcar o método ou a propriedade na classe pai como `open`. Isso resultará em um erro de compilação, pois o Kotlin não permite que métodos ou propriedades que não são abertos sejam sobrescritos. Além disso, é importante garantir que a assinatura do método na classe filha corresponda exatamente à da classe pai, incluindo parâmetros e tipos de retorno.

Outro ponto a ser considerado é a visibilidade dos métodos. Um método que é `private` na classe pai não poderá ser sobrescrito na classe filha, pois não é acessível.

## Resumo em Uma Linha
A palavra-chave `override` em Kotlin permite que classes filhas modifiquem métodos e propriedades herdados, promovendo a personalização e o polimorfismo na Programação Orientada a Objetos.