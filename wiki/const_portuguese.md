<!--
Meta Description: # Constantes em Kotlin: Entendendo o Uso da Palavra-chave "const" ## Sinopse A palavra-chave `const` em Kotlin é utilizada para declarar constantes em...
Meta Keywords: const, kotlin, que, uma, constante
-->

# Constantes em Kotlin: Entendendo o Uso da Palavra-chave "const"

## Sinopse
A palavra-chave `const` em Kotlin é utilizada para declarar constantes em tempo de compilação, permitindo que valores sejam definidos como imutáveis e acessíveis em todo o código.

## Documentação
O `const` em Kotlin é uma modificação que pode ser aplicada a variáveis do tipo primitivo e a String, declaradas como `val`. Ao utilizar `const`, você está definindo uma constante que deve ser inicializada em tempo de compilação. Isso significa que o valor atribuído à constante não pode ser alterado após sua definição.

### Propósito
O principal propósito do `const` é melhorar a eficiência do código, permitindo que constantes sejam resolvidas em tempo de compilação, em vez de em tempo de execução. Isso é especialmente útil para valores que não mudam e que são utilizados em múltiplos lugares no código.

### Uso
Para declarar uma constante com `const`, você deve seguir a seguinte sintaxe:

```kotlin
const val NOME_DA_CONSTANTE: TIPO = VALOR
```

Onde:
- `NOME_DA_CONSTANTE` é o nome da constante, que deve estar em letras maiúsculas por convenção.
- `TIPO` é o tipo da constante, que pode ser um tipo primitivo ou `String`.
- `VALOR` é o valor que você pretende atribuir à constante.

### Detalhes
- As constantes `const` devem ser declaradas no nível superior de um arquivo Kotlin ou dentro de um objeto.
- Elas não podem ser usadas com tipos que não sejam primitivos ou `String`.
- Não é possível usar `const` com propriedades de classes (membros), apenas com propriedades de nível superior ou de objetos.

## Exemplos
Aqui estão alguns exemplos de como usar `const` em Kotlin:

### Exemplo 1: Declarando uma constante de texto
```kotlin
const val NOME_DO_PROGRAMA = "Meu Programa Kotlin"
```

### Exemplo 2: Declarando uma constante numérica
```kotlin
const val TEMPO_MAXIMO = 60 // em segundos
```

### Exemplo 3: Usando constantes em uma função
```kotlin
fun exibirInformacoes() {
    println("Bem-vindo ao $NOME_DO_PROGRAMA")
    println("O tempo máximo é de $TEMPO_MAXIMO segundos.")
}
```

## Explicação
Alguns cuidados devem ser tomados ao usar `const` em Kotlin:

- **Imutabilidade**: Uma vez definida, o valor de uma constante `const` não pode ser alterado. Tentar modificar uma constante resultará em um erro de compilação.
- **Limitações de Tipo**: Apenas tipos primitivos e `String` podem ser usados. Tentar usar uma constante com um tipo não permitido resultará em erro.
- **Escopo**: Certifique-se de que as constantes estão no escopo correto. Elas devem ser declaradas fora de classes ou em um objeto para serem acessíveis globalmente.

## Resumo em Uma Linha
A palavra-chave `const` em Kotlin define constantes imutáveis em tempo de compilação, melhorando a eficiência e a organização do código.