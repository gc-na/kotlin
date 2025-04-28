<!--
Meta Description: # Comando "if" em Kotlin: Estruturas de Controle de Fluxo ## Sinopse O comando "if" em Kotlin é uma estrutura de controle de fluxo que permite executa...
Meta Keywords: kotlin, else, código, uma, para
-->

# Comando "if" em Kotlin: Estruturas de Controle de Fluxo

## Sinopse
O comando "if" em Kotlin é uma estrutura de controle de fluxo que permite executar diferentes blocos de código com base em condições booleanas. É essencial para a tomada de decisões em programas.

## Documentação
O comando "if" em Kotlin é utilizado para avaliar uma expressão condicional. Se a condição for verdadeira, um bloco de código específico é executado; caso contrário, pode-se especificar um bloco alternativo utilizando "else".

### Estrutura Básica
```kotlin
if (condição) {
    // Código executado se a condição for verdadeira
} else {
    // Código executado se a condição for falsa
}
```

### Uso em Expressões
Kotlin permite usar "if" como uma expressão, ou seja, pode retornar um valor. Isso é útil para atribuições ou retornos em funções.

```kotlin
val resultado = if (condição) {
    valorSeVerdadeiro
} else {
    valorSeFalso
}
```

### Encadeamento de Condições
É possível encadear várias condições utilizando "else if".

```kotlin
if (condição1) {
    // Código para condição1
} else if (condição2) {
    // Código para condição2
} else {
    // Código para outras condições
}
```

## Exemplos

### Exemplo 1: Uso Básico
```kotlin
val numero = 10

if (numero > 0) {
    println("O número é positivo.")
} else {
    println("O número é negativo ou zero.")
}
```

### Exemplo 2: If como Expressão
```kotlin
val idade = 18
val status = if (idade >= 18) {
    "Adulto"
} else {
    "Menor de idade"
}
println(status)  // Saída: Adulto
```

### Exemplo 3: Encadeamento de Condições
```kotlin
val nota = 75

if (nota >= 90) {
    println("Aprovado com Distinção.")
} else if (nota >= 60) {
    println("Aprovado.")
} else {
    println("Reprovado.")
}
```

## Explicação
Um erro comum com o comando "if" é esquecer de usar chaves para delimitar o bloco de código, principalmente quando se trabalha com múltiplas linhas. Em Kotlin, as chaves são recomendadas para melhorar a legibilidade, mesmo que o bloco tenha apenas uma linha. Além disso, ao usar "if" como uma expressão, é importante garantir que todas as possíveis condições retornem um valor, caso contrário, o compilador apresentará um erro.

## Resumo em Uma Linha
O comando "if" em Kotlin é uma estrutura que permite a execução condicional de blocos de código, podendo ser utilizada como uma expressão que retorna valores.