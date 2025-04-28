<!--
Meta Description: # Comando "break" em Kotlin: Controle de Fluxo em Laços ## Sinopse O comando `break` em Kotlin é utilizado para interromper a execução de laços, como ...
Meta Keywords: break, laço, kotlin, que, laços
-->

# Comando "break" em Kotlin: Controle de Fluxo em Laços

## Sinopse
O comando `break` em Kotlin é utilizado para interromper a execução de laços, como `for`, `while` e `do...while`, permitindo um controle mais preciso do fluxo de execução do programa.

## Documentação
O `break` é uma palavra-chave em Kotlin que serve para sair imediatamente de um laço, interrompendo sua execução. Ele é útil em situações onde uma condição específica é atendida, e você deseja sair do laço sem esperar que todas as iterações sejam completadas.

### Propósito
O principal propósito do `break` é permitir que o programador finalize um laço prematuramente, economizando tempo de execução e evitando operações desnecessárias.

### Uso
O comando `break` pode ser utilizado em qualquer tipo de laço em Kotlin. Sua sintaxe é simples e consiste apenas em escrever a palavra-chave `break` dentro do bloco do laço. 

### Detalhes
- O `break` pode ser usado em laços aninhados para sair do laço mais interno.
- Não deve ser usado fora de um contexto de laço, pois isso resultará em um erro de compilação.

## Exemplos

### Exemplo 1: Uso básico do `break` em um laço `for`
```kotlin
for (i in 1..10) {
    if (i == 5) {
        break
    }
    println(i)
}
// Saída: 1, 2, 3, 4
```

### Exemplo 2: Uso do `break` em um laço `while`
```kotlin
var j = 1
while (j <= 10) {
    if (j == 7) {
        break
    }
    println(j)
    j++
}
// Saída: 1, 2, 3, 4, 5, 6
```

### Exemplo 3: `break` em laços aninhados
```kotlin
for (x in 1..3) {
    for (y in 1..3) {
        if (y == 2) {
            break // Sai do laço interno
        }
        println("x: $x, y: $y")
    }
}
// Saída: x: 1, y: 1
//         x: 2, y: 1
//         x: 3, y: 1
```

## Explicação
Alguns erros comuns ao utilizar o `break` incluem:
- Tentar usar `break` fora de um laço, o que resultará em um erro de compilação.
- Não perceber que o `break` afeta apenas o laço em que se encontra, o que pode levar a resultados inesperados em laços aninhados.

Além disso, o `break` não deve ser confundido com o `continue`, que apenas pula para a próxima iteração do laço, sem sair dele.

## Resumo em uma linha
O comando `break` em Kotlin permite interromper a execução de laços, proporcionando controle total sobre o fluxo do programa.