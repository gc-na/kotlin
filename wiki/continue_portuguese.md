<!--
Meta Description: # Continue: Comando de Controle de Fluxo em Kotlin ## Sinopse O comando `continue` em Kotlin é utilizado dentro de estruturas de repetição, como `for`...
Meta Keywords: continue, loop, kotlin, comando, iteração
-->

# Continue: Comando de Controle de Fluxo em Kotlin

## Sinopse
O comando `continue` em Kotlin é utilizado dentro de estruturas de repetição, como `for`, `while` e `do while`, para pular a iteração atual e continuar a próxima. Essa funcionalidade é útil quando se deseja ignorar certas condições sem interromper completamente o loop.

## Documentação
O `continue` é um comando de controle de fluxo que permite que você controle como um loop se comporta em determinadas situações. Ao ser chamado, o `continue` faz com que o loop ignore o restante do código que está na iteração atual e avance diretamente para a próxima iteração.

### Uso
- **Sintaxe**: O uso básico do `continue` é simples. Você o coloca dentro de um loop, onde, se uma condição específica for atendida, o comando `continue` é executado.
  
```kotlin
for (i in 1..10) {
    if (i % 2 == 0) {
        continue // Ignora números pares
    }
    println(i) // Apenas números ímpares serão impressos
}
```

### Detalhes
- O `continue` pode ser utilizado em loops aninhados. Quando chamado, ele apenas afetará o loop mais interno onde foi chamado.
- O comando não pode ser usado fora de um contexto de loop, pois resultará em um erro de compilação.

## Exemplos
Aqui estão alguns exemplos práticos do uso do `continue` em Kotlin:

### Exemplo 1: Ignorando números pares
```kotlin
for (i in 1..10) {
    if (i % 2 == 0) {
        continue
    }
    println(i) // Saída: 1, 3, 5, 7, 9
}
```

### Exemplo 2: Usando `continue` em um loop while
```kotlin
var i = 0
while (i < 10) {
    i++
    if (i % 2 == 0) {
        continue
    }
    println(i) // Saída: 1, 3, 5, 7, 9
}
```

### Exemplo 3: Em um loop aninhado
```kotlin
for (i in 1..3) {
    for (j in 1..3) {
        if (j == 2) {
            continue // Ignora a iteração quando j é 2
        }
        println("i: $i, j: $j")
    }
}
// Saída: i: 1, j: 1
//        i: 1, j: 3
//        i: 2, j: 1
//        i: 2, j: 3
//        i: 3, j: 1
//        i: 3, j: 3
```

## Explicação
Embora o `continue` seja uma ferramenta poderosa, é importante usá-lo com cuidado. Um dos erros comuns é utilizar `continue` sem uma condição apropriada, o que pode levar ao comportamento inesperado do loop. Além disso, ao usar `continue` em loops aninhados, é fundamental entender qual loop está sendo afetado. O `continue` apenas interrompe a iteração do loop mais interno, o que pode causar confusão se não estiver claro qual loop está sendo manipulado.

## Resumo em Uma Linha
O comando `continue` em Kotlin permite pular a iteração atual de um loop e continuar com a próxima, facilitando o controle do fluxo de execução.