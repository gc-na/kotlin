<!--
Meta Description: # Modificador "protected" em Kotlin: Entenda seu Uso e Aplicações ## Sinopse O modificador de acesso "protected" em Kotlin é utilizado para restringir...
Meta Keywords: protected, classe, acesso, kotlin, membros
-->

# Modificador "protected" em Kotlin: Entenda seu Uso e Aplicações

## Sinopse
O modificador de acesso "protected" em Kotlin é utilizado para restringir a visibilidade de classes e membros a subclasses e à própria classe, promovendo encapsulamento e organização no código.

## Documentação
No Kotlin, o modificador "protected" permite que os membros de uma classe (como propriedades e métodos) sejam acessados apenas dentro da própria classe e em suas subclasses. Isso é especialmente útil para implementar a herança, onde a intenção é que subclasses possam acessar e modificar comportamentos definidos em uma classe pai, enquanto mantém esses membros inacessíveis a outras partes do código.

### Propósito
O uso do "protected" é essencial quando se deseja proteger membros de uma classe de acessos indesejados, mas ainda permitir que subclasses tenham acesso a esses membros. Isso proporciona uma forma de encapsulamento e controle de acesso, facilitando a manutenção do código.

### Uso
Para declarar um membro como "protected", basta utilizar a palavra-chave antes da definição do membro:

```kotlin
open class Animal {
    protected val tipo: String = "Desconhecido"

    protected fun emitirSom() {
        println("Som genérico")
    }
}

class Cachorro : Animal() {
    fun apresentar() {
        println("Eu sou um $tipo")
        emitirSom()
    }
}
```

No exemplo acima, a classe `Cachorro` pode acessar tanto a propriedade `tipo` quanto o método `emitirSom()` da classe `Animal`, pois está dentro do escopo da subclasse.

## Exemplos
### Exemplo 1: Acesso a Membros Protegidos
```kotlin
open class Veiculo {
    protected val modelo: String = "Modelo Padrão"

    protected fun mostrarModelo() {
        println("Modelo do veículo: $modelo")
    }
}

class Carro : Veiculo() {
    fun detalhes() {
        mostrarModelo() // Acesso permitido
    }
}
```

### Exemplo 2: Tentativa de Acesso Externo
```kotlin
class Bicicleta : Veiculo() {
    fun info() {
        // println(modelo) // Erro: 'modelo' é protegido e não acessível aqui
    }
}
```

## Explicação
### Armadilhas Comuns
1. **Acesso Não Permitido**: Uma tentativa de acessar um membro protegido de fora da classe ou subclasses resultará em um erro de compilação. É importante lembrar que o "protected" não é equivalente ao "private", já que "private" limita o acesso apenas à própria classe.
  
2. **Herdabilidade Limitada**: O modificador "protected" não é aplicável a nível de instância se não houver herança. Ou seja, se você não pretende usar herança, considere usar o "private".

3. **Visibilidade em Módulos**: O "protected" não afeta a visibilidade em diferentes módulos; ele é restrito apenas ao escopo de classe e subclasses.

## Resumo em Uma Frase
O modificador "protected" em Kotlin permite que membros de uma classe sejam acessíveis apenas dentro da própria classe e suas subclasses, facilitando o encapsulamento e a herança.