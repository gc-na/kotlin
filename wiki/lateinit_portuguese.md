<!--
Meta Description: # lateinit em Kotlin: O Que É e Como Usá-lo ## Sinopse O `lateinit` é um modificador de visibilidade em Kotlin que permite declarar variáveis não inic...
Meta Keywords: que, lateinit, não, nome, uma
-->

# lateinit em Kotlin: O Que É e Como Usá-lo

## Sinopse
O `lateinit` é um modificador de visibilidade em Kotlin que permite declarar variáveis não inicializadas, mas que serão inicializadas antes do uso. É especialmente útil para variáveis de tipo não nulo que não podem ser inicializadas no momento da declaração.

## Documentação
O `lateinit` é utilizado em propriedades que são declaradas como `var` (variáveis mutáveis) e permite que você adie a inicialização de uma variável até que ela seja realmente necessária. Isso é particularmente útil em cenários como injeção de dependência, onde o valor pode ser atribuído após a construção do objeto.

### Uso
Para usar o `lateinit`, basta preceder a declaração da variável com a palavra-chave `lateinit`. A variável deve ser de um tipo não nulo e deve ser uma propriedade da classe.

```kotlin
class Exemplo {
    lateinit var nome: String

    fun inicializarNome(novoNome: String) {
        nome = novoNome
    }
    
    fun imprimirNome() {
        println(nome)
    }
}
```

### Detalhes
- O `lateinit` não pode ser usado com propriedades de tipo primitivo (como `Int`, `Double`, etc.).
- Se você tentar acessar uma variável `lateinit` que não foi inicializada, uma exceção `UninitializedPropertyAccessException` será lançada.
- É possível verificar se uma propriedade `lateinit` foi inicializada usando o método `::nome.isInitialized`.

## Exemplos

### Exemplo Básico
```kotlin
class Usuario {
    lateinit var nome: String
    
    fun configurarNome(novoNome: String) {
        nome = novoNome
    }
    
    fun mostrarNome() {
        if (::nome.isInitialized) {
            println("Nome: $nome")
        } else {
            println("Nome não inicializado.")
        }
    }
}

fun main() {
    val usuario = Usuario()
    usuario.mostrarNome() // Saída: Nome não inicializado.
    usuario.configurarNome("Carlos")
    usuario.mostrarNome() // Saída: Nome: Carlos
}
```

## Explicação
Um dos principais erros ao usar `lateinit` é tentar acessar uma propriedade que não foi inicializada, o que resulta em uma exceção em tempo de execução. É crucial garantir que a variável seja inicializada antes do uso. Além disso, `lateinit` não pode ser usado em propriedades que precisam ser inicializadas no momento da declaração, como constantes ou propriedades imutáveis (`val`).

Outra consideração importante é que o `lateinit` não é aplicável a tipos primitivos. Para tipos primitivos, considere usar uma variável nullable (`Int?`, `Double?`, etc.) e inicializá-la com `null` até que um valor válido seja atribuído.

## Resumo em Uma Frase
O `lateinit` é um modificador em Kotlin que permite adiar a inicialização de variáveis não nulas, proporcionando flexibilidade no gerenciamento de dependências e inicializações tardias.