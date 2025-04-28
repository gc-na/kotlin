<!--
Meta Description: # `fun`: Funções em Kotlin – Entenda Tudo Sobre a Declaração de Funções ## Sinopse O comando `fun` em Kotlin é utilizado para declarar funções, permit...
Meta Keywords: função, fun, kotlin, funções, uma
-->

# `fun`: Funções em Kotlin – Entenda Tudo Sobre a Declaração de Funções

## Sinopse
O comando `fun` em Kotlin é utilizado para declarar funções, permitindo que os desenvolvedores criem blocos de código reutilizáveis que podem ser chamados em diferentes partes de um programa.

## Documentação
Em Kotlin, a palavra-chave `fun` é fundamental para a definição de funções. Uma função é um conjunto de instruções que podem ser executadas quando chamada. A sintaxe básica para declarar uma função em Kotlin é a seguinte:

```kotlin
fun nomeDaFuncao(parametros: Tipo): TipoDeRetorno {
    // corpo da função
}
```

### Propósito
O propósito principal da declaração de funções com `fun` é promover a reutilização de código e a modularização, facilitando a manutenção e a legibilidade do código.

### Uso
Para utilizar uma função, basta declará-la e, em seguida, chamá-la pelo nome, passando os parâmetros necessários. A função pode retornar um valor, ou não, dependendo da sua definição.

### Detalhes
- **Parâmetros**: Você pode passar zero ou mais parâmetros para uma função, especificando seus tipos.
- **Tipo de Retorno**: O tipo de retorno da função é opcional. Se a função não retornar nada, pode ser especificado como `Unit`, que é o equivalente a `void` em outras linguagens.
- **Funções de Nível Superior**: Em Kotlin, as funções podem ser definidas fora de qualquer classe, permitindo que sejam funções de nível superior.

## Exemplos

### Exemplo 1: Função Simples
```kotlin
fun saudacao(nome: String): String {
    return "Olá, $nome!"
}
```

### Exemplo 2: Função Sem Parâmetros
```kotlin
fun dizerOla() {
    println("Olá, mundo!")
}
```

### Exemplo 3: Função com Parâmetros Opcionais
```kotlin
fun soma(a: Int, b: Int = 0): Int {
    return a + b
}
```

### Exemplo 4: Função de Nível Superior
```kotlin
fun main() {
    println(saudacao("João"))
    dizerOla()
    println(soma(5, 3))
    println(soma(5)) // Usando o valor padrão
}
```

## Explicação
Embora o uso de `fun` seja bastante intuitivo, alguns desenvolvedores iniciantes podem encontrar dificuldades como:

- **Parâmetros Opcionais**: É importante lembrar que, ao definir parâmetros opcionais, o valor padrão deve ser atribuído corretamente.
- **Tipo de Retorno**: Se uma função não retornar um valor, você não precisa declarar o tipo de retorno, mas, se o fizer, use `Unit`.
- **Escopo da Função**: Funções definidas fora de uma classe são acessíveis de qualquer lugar no mesmo arquivo, mas podem exigir importação em diferentes arquivos.

## Resumo em Uma Linha
A palavra-chave `fun` em Kotlin é usada para declarar funções, permitindo reutilização de código e modularização eficiente.