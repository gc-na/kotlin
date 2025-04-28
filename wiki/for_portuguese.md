<!--
Meta Description: # O Comando "for" no Kotlin: Iterando com Facilidade ## Sinopse O comando "for" em Kotlin é uma estrutura de controle utilizada para iterar sobre cole...
Meta Keywords: kotlin, uma, sobre, iterando, println
-->

# O Comando "for" no Kotlin: Iterando com Facilidade

## Sinopse
O comando "for" em Kotlin é uma estrutura de controle utilizada para iterar sobre coleções, arrays ou intervalos. Ele proporciona uma maneira simples e concisa de acessar elementos sequencialmente.

## Documentação
O loop "for" em Kotlin permite que os desenvolvedores percorram uma coleção ou intervalo de valores sem a necessidade de um índice explícito. Sua sintaxe é simples e pode ser usada com diversos tipos de iteráveis, como listas, conjuntos ou ranges.

### Propósito
O principal objetivo do comando "for" é facilitar a iteração sobre elementos, tornando o código mais legível e reduzindo a possibilidade de erros ao lidar com índices.

### Uso
A estrutura básica do `for` é a seguinte:

```kotlin
for (item in collection) {
    // Código a ser executado para cada item
}
```

Você pode iterar sobre intervalos (ranges) e arrays da seguinte forma:

```kotlin
for (i in 1..5) {
    println(i) // Imprime números de 1 a 5
}
```

## Exemplos

### Exemplo 1: Iterando sobre uma lista
```kotlin
val frutas = listOf("Maçã", "Banana", "Laranja")
for (fruta in frutas) {
    println(fruta)
}
```

### Exemplo 2: Iterando sobre um intervalo
```kotlin
for (i in 1 until 10) {
    println(i) // Imprime números de 1 a 9
}
```

### Exemplo 3: Iterando com passos
```kotlin
for (i in 1..10 step 2) {
    println(i) // Imprime 1, 3, 5, 7, 9
}
```

### Exemplo 4: Iterando em ordem decrescente
```kotlin
for (i in 10 downTo 1) {
    println(i) // Imprime números de 10 a 1
}
```

## Explicação
Embora o loop "for" seja bastante intuitivo, existem algumas armadilhas comuns a serem observadas:

- **Mudança de coleção durante a iteração**: Alterar a coleção que está sendo iterada pode resultar em comportamento inesperado ou em uma `ConcurrentModificationException`.
  
- **Uso de índices**: Ao iterar sobre uma lista, é fácil cair na tentação de usar índices ao invés de elementos diretos. Prefira sempre usar o formato `for (item in collection)` para melhor legibilidade.

- **Intervalos vazios**: Quando utilizamos `until`, o valor final não é incluído. É importante ter isso em mente para evitar confusões.

## Resumo em Uma Linha
O comando "for" em Kotlin permite iterar facilmente sobre coleções, arrays e intervalos, proporcionando uma sintaxe limpa e intuitiva.