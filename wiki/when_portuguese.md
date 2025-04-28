<!--
Meta Description: # Quando Usar "when" em Kotlin: Guia Completo ## Sinopse O `when` é uma expressão de controle em Kotlin que permite realizar múltiplas verificações de...
Meta Keywords: when, uma, que, kotlin, else
-->

# Quando Usar "when" em Kotlin: Guia Completo

## Sinopse
O `when` é uma expressão de controle em Kotlin que permite realizar múltiplas verificações de condição de forma mais concisa e legível em comparação ao tradicional `switch` de outras linguagens.

## Documentação
O `when` é uma poderosa estrutura de controle que pode ser utilizada para executar diferentes blocos de código com base no valor de uma variável. Ele oferece uma sintaxe mais limpa e flexível, permitindo verificar valores, tipos e até expressões complexas. O `when` pode ser usado como uma expressão que retorna um valor ou como uma instrução que executa ações.

### Propósito
O propósito do `when` é simplificar decisões complexas e substituir múltiplas instruções `if-else`, melhorando a legibilidade do código.

### Uso
A sintaxe básica do `when` é a seguinte:

```kotlin
when (variavel) {
    valor1 -> bloco1
    valor2 -> bloco2
    else -> blocoPadrão
}
```

Você pode usar `when` sem uma variável para verificar condições mais complexas:

```kotlin
when {
    condicao1 -> bloco1
    condicao2 -> bloco2
    else -> blocoPadrão
}
```

## Exemplos
### Exemplo 1: Uso Básico do `when`
```kotlin
val diaDaSemana = 3

val nomeDoDia = when (diaDaSemana) {
    1 -> "Domingo"
    2 -> "Segunda-feira"
    3 -> "Terça-feira"
    4 -> "Quarta-feira"
    5 -> "Quinta-feira"
    6 -> "Sexta-feira"
    7 -> "Sábado"
    else -> "Dia inválido"
}

println(nomeDoDia) // Saída: Terça-feira
```

### Exemplo 2: Uso do `when` Sem Variável
```kotlin
val numero = 15

when {
    numero % 2 == 0 -> println("Número Par")
    numero % 2 != 0 -> println("Número Ímpar")
    else -> println("Número Inválido")
}
```

## Explicação
Embora o `when` seja uma ferramenta poderosa, alguns cuidados devem ser tomados:

- **Tipo de Dados**: O `when` deve ser usado com valores compatíveis. Usar tipos diferentes pode resultar em erros de compilação.
- **Expressões Complexas**: Quando se utiliza expressões no `when`, é importante garantir que as condições sejam mutuamente exclusivas para evitar comportamentos inesperados.
- **Valor Padrão**: Sempre que possível, inclua um bloco `else` para cobrir casos não tratados, evitando que seu código falhe silenciosamente.

## Resumo em Uma Linha
O `when` em Kotlin é uma expressão versátil que simplifica a execução de múltiplas verificações de condição, tornando o código mais limpo e fácil de entender.