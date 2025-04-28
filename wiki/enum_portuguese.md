<!--
Meta Description: # Enum em Kotlin: Compreendendo Tipos Enumerados ## Sinopse Enums (tipos enumerados) em Kotlin são uma poderosa característica que permite definir um ...
Meta Keywords: enums, enum, para, kotlin, que
-->

# Enum em Kotlin: Compreendendo Tipos Enumerados

## Sinopse
Enums (tipos enumerados) em Kotlin são uma poderosa característica que permite definir um conjunto de constantes relacionadas. Eles são ideais para representar um grupo fixo de valores, como dias da semana, estados de um processo, etc.

## Documentação
Os enums em Kotlin são utilizados para declarar um tipo que pode ter um conjunto limitado de valores. Cada valor é uma instância do tipo enum, o que proporciona segurança de tipo e legibilidade ao código.

### Propósito
Enums são usados para representar um conjunto fixo de valores, tornando o código mais legível e seguro. Eles ajudam a evitar erros, como passar valores inválidos para funções.

### Uso
Para declarar um enum em Kotlin, utilizamos a palavra-chave `enum class`. Abaixo está a sintaxe básica:

```kotlin
enum class NomeDoEnum {
    VALOR1,
    VALOR2,
    VALOR3
}
```

Os enums também podem ter propriedades e métodos, permitindo que cada valor possua comportamentos específicos.

### Detalhes
- **Herança**: Enums não podem ser herdados de outras classes, mas podem implementar interfaces.
- **Métodos**: É possível adicionar métodos e propriedades a um enum para funcionalidade adicional.
- **Uso em `when`**: Os enums se integram perfeitamente com a expressão `when`, permitindo uma abordagem mais limpa para controle de fluxo.

## Exemplos

### Exemplo Básico
```kotlin
enum class DiaDaSemana {
    DOMINGO,
    SEGUNDA,
    TERÇA,
    QUARTA,
    QUINTA,
    SEXTA,
    SÁBADO
}

fun verificaDia(dia: DiaDaSemana) {
    when (dia) {
        DiaDaSemana.DOMINGO -> println("Dia de descanso!")
        DiaDaSemana.SEGUNDA -> println("Início da semana!")
        else -> println("Dia de trabalho!")
    }
}
```

### Exemplo com Propriedades e Métodos
```kotlin
enum class Estado(val descricao: String) {
    ATIVO("O estado está ativo"),
    INATIVO("O estado está inativo"),
    PENDENTE("O estado está pendente");

    fun imprimeDescricao() {
        println(descricao)
    }
}

fun main() {
    Estado.ATIVO.imprimeDescricao()  // Saída: O estado está ativo
}
```

## Explicação
### Armadilhas Comuns
- **Comparação de Enum**: É importante lembrar que enums devem ser comparados usando `==` ou `===` para evitar erros de referência.
- **Extensibilidade**: Enums não podem ser estendidos. Se precisar de um comportamento mais complexo, considere usar classes seladas (`sealed classes`).

### Observações
- Os enums são uma excelente forma de garantir que apenas valores válidos sejam utilizados em seu código, melhorando a manutenibilidade.
- Ao trabalhar com enums, é bom documentar cada valor para que o propósito de cada um fique claro.

## Resumo em uma Frase
Enums em Kotlin permitem a definição de um tipo seguro e legível que representa um conjunto fixo de constantes, facilitando a manutenção e a legibilidade do código.