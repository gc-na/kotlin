<!--
Meta Description: # var em Kotlin: Atributos e Aplicações ## Sinopse O `var` é uma palavra-chave em Kotlin utilizada para declarar variáveis mutáveis. Isso significa qu...
Meta Keywords: var, variáveis, que, kotlin, para
-->

# var em Kotlin: Atributos e Aplicações

## Sinopse
O `var` é uma palavra-chave em Kotlin utilizada para declarar variáveis mutáveis. Isso significa que uma variável declarada com `var` pode ter seu valor alterado ao longo da execução do programa, permitindo maior flexibilidade no desenvolvimento de aplicações.

## Documentação
Em Kotlin, a palavra-chave `var` é utilizada para declarar variáveis que podem ser modificadas. Ao contrário do `val`, que declara variáveis imutáveis, o `var` permite que o valor da variável seja reatribuído após a sua inicialização.

### Propósito
O principal propósito do `var` é proporcionar uma maneira simples e eficaz de lidar com dados que precisam ser alterados, como contadores, estados de um objeto ou qualquer outra informação dinâmica durante a execução de um aplicativo.

### Uso
A sintaxe básica para declarar uma variável usando `var` é a seguinte:

```kotlin
var nomeDaVariavel: Tipo = valorInicial
```

- **nomeDaVariavel**: o nome que você dá à sua variável.
- **Tipo**: o tipo de dado que a variável irá armazenar (pode ser omitido se o compilador puder inferir o tipo).
- **valorInicial**: o valor inicial da variável.

### Detalhes
- Variáveis declaradas com `var` podem ser reassigned a qualquer momento.
- O tipo pode ser inferido pelo compilador, assim não é necessário especificá-lo explicitamente.

## Exemplos

### Exemplo 1: Declaração e Reatribuição Simples
```kotlin
fun main() {
    var idade = 25
    println(idade) // Saída: 25
    idade = 26
    println(idade) // Saída: 26
}
```

### Exemplo 2: Declaração com Tipo Específico
```kotlin
fun main() {
    var nome: String = "João"
    println(nome) // Saída: João
    nome = "Maria"
    println(nome) // Saída: Maria
}
```

### Exemplo 3: Uso em Estruturas de Controle
```kotlin
fun main() {
    var contagem = 0
    for (i in 1..5) {
        contagem += i
    }
    println(contagem) // Saída: 15
}
```

## Explicação
Embora o `var` seja útil para a mutabilidade, é importante usar essa flexibilidade com cautela. Variáveis mutáveis podem levar a estados inesperados e dificultar a manutenção do código. Aqui estão alguns pontos a considerar:

- **Evitar Mutabilidade Desnecessária**: Sempre que possível, prefira usar `val` para declarar variáveis imutáveis. Isso torna o código mais seguro e previsível.
- **Escopo**: Tenha cuidado com o escopo das variáveis `var`. Variáveis declaradas dentro de funções ou blocos são acessíveis apenas dentro daquele contexto.
- **Inicialização**: Certifique-se de inicializar suas variáveis antes de usá-las; caso contrário, o compilador emitirá um erro.

## Resumo em Uma Linha
A palavra-chave `var` em Kotlin é utilizada para declarar variáveis mutáveis, que podem ter seus valores alterados durante a execução do programa.