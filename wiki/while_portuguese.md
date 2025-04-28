<!--
Meta Description: # Laço "while" em Kotlin: Como Funciona e Exemplos Práticos ## Sinopse O laço `while` em Kotlin é uma estrutura de controle que permite a execução rep...
Meta Keywords: condição, while, uma, laço, para
-->

# Laço "while" em Kotlin: Como Funciona e Exemplos Práticos

## Sinopse
O laço `while` em Kotlin é uma estrutura de controle que permite a execução repetida de um bloco de código enquanto uma condição especificada for verdadeira. Esse recurso é fundamental para a criação de loops em aplicações que requerem iterações dinâmicas.

## Documentação
O `while` em Kotlin é utilizado para criar laços que executam um bloco de código até que uma condição se torne falsa. A sintaxe básica do `while` é:

```kotlin
while (condição) {
    // bloco de código a ser executado
}
```

### Propósito
O objetivo do `while` é permitir a repetição de uma sequência de instruções com base em uma condição booleana. Ele é ideal para situações em que o número de iterações não é conhecido a priori.

### Uso
- **Condição**: A condição deve ser uma expressão booleana. O laço continua a ser executado enquanto essa condição retornar `true`.
- **Interrupção**: A execução do laço pode ser interrompida usando a palavra-chave `break` ou pode ser pulada uma iteração com `continue`.

### Detalhes
- Se a condição inicial for falsa, o bloco de código dentro do `while` não será executado.
- É importante garantir que a condição eventualmente se torne falsa, caso contrário, o laço se tornará um loop infinito.

## Exemplos

### Exemplo Básico 1: Contagem de 1 a 5
```kotlin
var contador = 1
while (contador <= 5) {
    println(contador)
    contador++
}
```
**Saída:**
```
1
2
3
4
5
```

### Exemplo Básico 2: Loop Infinito com Interrupção
```kotlin
var tentativas = 0
while (true) {
    tentativas++
    println("Tentativa número: $tentativas")
    if (tentativas >= 5) {
        break
    }
}
```
**Saída:**
```
Tentativa número: 1
Tentativa número: 2
Tentativa número: 3
Tentativa número: 4
Tentativa número: 5
```

## Explicação
### Armadilhas Comuns
- **Loops Infinitos**: Um erro comum é não alterar a condição dentro do laço, resultando em um loop infinito. Sempre verifique se a condição será eventualmente falsa.
- **Alteração da Condição**: Cuidado ao alterar variáveis que influenciam a condição do laço dentro do bloco. Isso pode levar a resultados inesperados.
- **Uso de `break` e `continue`**: Utilize `break` para sair do loop e `continue` para pular para a próxima iteração. O uso inadequado pode afetar a lógica do seu programa.

### Notas Adicionais
O `while` é frequentemente usado em situações como leitura de dados até uma condição ser satisfeita, processamento de entradas do usuário, ou para executar um bloco de código enquanto uma operação assíncrona está em andamento.

## Resumo em Uma Linha
O laço `while` em Kotlin permite executar repetidamente um bloco de código enquanto uma condição booleana for verdadeira, sendo essencial para iterações dinâmicas.