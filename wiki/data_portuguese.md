<!--
Meta Description: # Dados em Kotlin: Entendendo a Classe Data ## Sinopse Neste artigo, exploraremos a classe `data` em Kotlin, que é uma forma conveniente de criar clas...
Meta Keywords: dados, classe, kotlin, val, data
-->

# Dados em Kotlin: Entendendo a Classe Data

## Sinopse
Neste artigo, exploraremos a classe `data` em Kotlin, que é uma forma conveniente de criar classes que são usadas principalmente para armazenar dados.

## Documentação
A palavra-chave `data` em Kotlin é usada para declarar classes de dados. Essas classes são projetadas para armazenar dados e fornecer funcionalidades básicas de comparação, clonagem e exibição de dados de maneira simplificada. Ao declarar uma classe como `data`, o compilador gera automaticamente métodos como `equals()`, `hashCode()`, `toString()`, e também um método `copy()` que permite criar cópias de objetos de forma eficaz.

### Propósito
Classes de dados são úteis quando você precisa transferir dados entre diferentes partes da aplicação, sem se preocupar com a lógica de implementação.

### Uso
Para declarar uma classe de dados, você deve usar a palavra-chave `data` antes da definição da classe. A classe deve ter pelo menos uma propriedade que pode ser inicializada no construtor primário.

```kotlin
data class Usuario(val nome: String, val idade: Int)
```

## Exemplos
Aqui estão alguns exemplos básicos de uso da classe `data`:

### Exemplo 1: Definição de Classe de Dados
```kotlin
data class Produto(val id: Int, val nome: String, val preco: Double)
```

### Exemplo 2: Criando um Objeto
```kotlin
val produto = Produto(1, "Camiseta", 49.90)
println(produto) // Saída: Produto(id=1, nome=Camiseta, preco=49.9)
```

### Exemplo 3: Comparação de Objetos
```kotlin
val produto1 = Produto(1, "Camiseta", 49.90)
val produto2 = Produto(1, "Camiseta", 49.90)

println(produto1 == produto2) // Saída: true
```

### Exemplo 4: Usando o Método Copy
```kotlin
val produto3 = produto1.copy(preco = 39.90)
println(produto3) // Saída: Produto(id=1, nome=Camiseta, preco=39.9)
```

## Explicação
Embora as classes de dados em Kotlin sejam poderosas, existem alguns pontos importantes a serem considerados:

1. **Imutabilidade**: As propriedades de uma classe de dados são, por padrão, imutáveis. Para torná-las mutáveis, você deve usar a palavra-chave `var` em vez de `val`.

2. **Desconhecer o `copy()`**: O método `copy()` é uma das características mais úteis das classes de dados, permitindo que você crie cópias de objetos com alterações específicas, mas é importante lembrar que ele não altera o objeto original.

3. **Propriedades**: Todas as propriedades do construtor primário são incluídas automaticamente nos métodos gerados. Se você não quiser que uma propriedade seja incluída, pode declará-la fora do construtor primário.

4. **Extensibilidade**: Você não pode herdar de uma classe de dados, pois isso poderia complicar a implementação dos métodos gerados.

## Resumo em Uma Linha
A classe `data` em Kotlin facilita a criação de classes que armazenam dados, gerando automaticamente métodos essenciais como `equals()`, `hashCode()`, e `toString()`.