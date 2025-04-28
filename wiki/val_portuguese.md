<!--
Meta Description: # Entendendo o "val" em Kotlin: Declaração de Variáveis Imutáveis ## Sinopse O `val` em Kotlin é uma palavra-chave utilizada para declarar variáveis i...
Meta Keywords: val, kotlin, uma, pode, variável
-->

# Entendendo o "val" em Kotlin: Declaração de Variáveis Imutáveis

## Sinopse
O `val` em Kotlin é uma palavra-chave utilizada para declarar variáveis imutáveis, ou seja, uma vez atribuído um valor, ele não pode ser alterado. Essa característica promove a segurança e a previsibilidade no código, sendo uma das principais funcionalidades da linguagem.

## Documentação
No Kotlin, a palavra-chave `val` é utilizada para declarar uma variável que não pode ser reatribuída após sua inicialização. Isso significa que, uma vez que você atribui um valor a uma variável declarada com `val`, você não pode mudar esse valor. Isso é especialmente útil em cenários onde a imutabilidade é desejável, como em programação funcional.

### Propósito
O uso de `val` ajuda a evitar efeitos colaterais indesejados e melhora a legibilidade do código, uma vez que o programador pode ter certeza de que o valor da variável não mudará ao longo do seu escopo.

### Uso
Para declarar uma variável com `val`, você deve seguir a seguinte sintaxe:

```kotlin
val nomeDaVariavel: Tipo = valor
```

O `Tipo` é opcional, já que o Kotlin pode inferir o tipo com base no valor atribuído.

## Exemplos

### Exemplo 1: Declaração Simples

```kotlin
val nome: String = "Kotlin"
```

Neste exemplo, a variável `nome` é declarada como uma string e não pode ser alterada para um novo valor.

### Exemplo 2: Inferência de Tipo

```kotlin
val idade = 25
```

Aqui, a variável `idade` é inferida como um `Int`, e seu valor não pode ser modificado depois da atribuição.

### Exemplo 3: Uso com Coleções

```kotlin
val listaDeNomes = listOf("Alice", "Bob", "Charlie")
// listaDeNomes.add("David") // Isso causaria um erro de compilação
```

Embora `listaDeNomes` seja imutável (não pode ser reatribuída), você ainda pode manipular a coleção se ela for mutável.

## Explicação
Um erro comum ao utilizar `val` é confundir a imutabilidade da variável com a imutabilidade dos objetos. Por exemplo, uma lista declarada com `val` não pode ser reatribuída, mas seus elementos podem ser modificados se a lista for mutável. 

Outra armadilha é tentar modificar a variável declarada com `val`. Qualquer tentativa de reatribuição resultará em um erro de compilação:

```kotlin
val numero = 10
// numero = 20 // Isso gerará um erro: "Val cannot be reassigned"
```

Portanto, é essencial entender que `val` impede apenas a reatribuição da variável, não a mutação do objeto que a variável referencia.

## Resumo em Uma Linha
O `val` em Kotlin é utilizado para declarar variáveis imutáveis, promovendo segurança e previsibilidade no código.