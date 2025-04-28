<!--
Meta Description: # Classe em Kotlin: Entendendo a Estrutura Fundamental da Programação Orientada a Objetos ## Sinopse A classe em Kotlin é um dos pilares da programaçã...
Meta Keywords: kotlin, classe, que, uma, classes
-->

# Classe em Kotlin: Entendendo a Estrutura Fundamental da Programação Orientada a Objetos

## Sinopse
A classe em Kotlin é um dos pilares da programação orientada a objetos, permitindo a definição de tipos de dados complexos e encapsulando comportamentos e propriedades.

## Documentação
Em Kotlin, uma classe é uma estrutura que representa um modelo ou uma entidade que agrupa dados e comportamentos relacionados. As classes permitem que os desenvolvedores criem objetos, que são instâncias de classes, e encapsulem atributos e métodos que operam sobre esses atributos.

### Propósito
As classes em Kotlin têm como propósito facilitar a organização do código, promover a reutilização e a abstração, além de permitir o encapsulamento de dados.

### Uso
Para definir uma classe em Kotlin, utiliza-se a palavra-chave `class`, seguida pelo nome da classe. O corpo da classe pode conter propriedades, métodos e inicializadores.

### Estrutura Básica
```kotlin
class NomeDaClasse {
    // Propriedades
    var propriedade: Tipo = valorInicial

    // Métodos
    fun metodo() {
        // Implementação
    }
}
```

## Exemplos
### Exemplo Simples de Classe
```kotlin
class Carro(val modelo: String, var ano: Int) {
    fun exibirDetalhes() {
        println("Modelo: $modelo, Ano: $ano")
    }
}

fun main() {
    val meuCarro = Carro("Fusca", 1976)
    meuCarro.exibirDetalhes()
}
```

### Classe com Inicialização
```kotlin
class Pessoa(val nome: String, var idade: Int) {
    init {
        println("Pessoa criada: $nome, $idade anos")
    }
}

fun main() {
    val pessoa = Pessoa("Maria", 30)
}
```

## Explicação
Ao trabalhar com classes em Kotlin, é importante estar ciente de alguns pontos:

1. **Visibilidade**: As classes e suas propriedades podem ter modificadores de visibilidade (`public`, `private`, `protected`, `internal`), que controlam o acesso a elas.

2. **Construtores**: Kotlin oferece construtores primários e secundários, permitindo uma flexibilidade maior na criação de instâncias.

3. **Herança**: Classes em Kotlin podem herdar de outras classes, utilizando a palavra-chave `open` para permitir que uma classe seja estendida.

4. **Dados Mutáveis e Imutáveis**: Propriedades podem ser declaradas como `var` (mutáveis) ou `val` (imutáveis), o que influencia o comportamento do objeto.

5. **Objetos Singleton**: Kotlin também permite a definição de classes singleton usando a palavra-chave `object`, que garante que apenas uma instância da classe existirá.

## Resumo em Uma Linha
A classe em Kotlin é uma estrutura essencial que encapsula dados e comportamentos, fundamentando a programação orientada a objetos.