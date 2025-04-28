<!--
Meta Description: # A Palavra-Chave "private" em Kotlin: Encapsulamento e Acesso a Membros ## Sinopse A palavra-chave `private` em Kotlin é utilizada para controlar o a...
Meta Keywords: private, classe, acesso, uma, que
-->

# A Palavra-Chave "private" em Kotlin: Encapsulamento e Acesso a Membros

## Sinopse
A palavra-chave `private` em Kotlin é utilizada para controlar o acesso a propriedades e métodos dentro de uma classe ou arquivo, promovendo o encapsulamento e protegendo a integridade dos dados.

## Documentação
Em Kotlin, a visibilidade de membros de classes e interfaces é definida usando modificadores de visibilidade. A palavra-chave `private` é um dos modificadores mais utilizados. Quando um membro é declarado como `private`, ele só pode ser acessado dentro da classe ou arquivo onde foi definido. Isso ajuda a proteger os dados e a manter a lógica interna da classe oculta de outras partes do código.

### Propósito
O principal objetivo do modificador `private` é garantir que os detalhes internos de uma classe não sejam acessíveis diretamente fora dela, o que é uma prática fundamental em programação orientada a objetos.

### Uso
Usar `private` é simples. Você pode declará-lo antes de propriedades ou métodos dentro de uma classe. O uso de `private` pode ser aplicado a:

- Propriedades de classe
- Métodos de classe
- Construtores

### Detalhes
- **Visibilidade em Classes**: Membros privados não são acessíveis em subclasses, mesmo que estas estejam dentro do mesmo pacote.
- **Visibilidade em Arquivos**: Quando utilizado em uma função ou propriedade fora de uma classe, `private` limita o acesso apenas ao arquivo onde está definido.
  
## Exemplos

### Exemplo 1: Propriedade Privada
```kotlin
class ContaBancaria {
    private var saldo: Double = 0.0

    fun depositar(valor: Double) {
        if (valor > 0) {
            saldo += valor
        }
    }

    fun obterSaldo(): Double {
        return saldo
    }
}

fun main() {
    val conta = ContaBancaria()
    conta.depositar(100.0)
    println("Saldo atual: ${conta.obterSaldo()}") // Saída: Saldo atual: 100.0
    // println(conta.saldo) // Erro: 'saldo' tem acesso privado em 'ContaBancaria'
}
```

### Exemplo 2: Método Privado
```kotlin
class Calculadora {
    private fun somar(a: Int, b: Int): Int {
        return a + b
    }

    fun calcularSoma(a: Int, b: Int): Int {
        return somar(a, b)
    }
}

fun main() {
    val calc = Calculadora()
    println("Soma: ${calc.calcularSoma(5, 10)}") // Saída: Soma: 15
    // println(calc.somar(5, 10)) // Erro: 'somar' tem acesso privado em 'Calculadora'
}
```

## Explicação
Um dos erros comuns ao usar `private` é tentar acessar membros privados de fora da classe ou arquivo, resultando em erros de compilação. Outro ponto importante é que `private` não impede o acesso a membros de instâncias da mesma classe, então é possível manipular dados privados dentro de métodos dessa classe.

Além disso, ao utilizar `private` em funções ou propriedades em um arquivo, é necessário entender que o escopo é limitado ao arquivo em questão, o que pode ser útil para funções utilitárias que não devem ser expostas globalmente.

## Resumo em Uma Linha
A palavra-chave `private` em Kotlin é utilizada para restringir o acesso a membros de classes e arquivos, promovendo o encapsulamento e a proteção dos dados.