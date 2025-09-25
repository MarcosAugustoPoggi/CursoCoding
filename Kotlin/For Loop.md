# Loops em Kotlin - Repetindo Código de Forma Eficiente

_Material de Aula - Curso de Programação_

## O que são Loops?

**Loops são estruturas que repetem um bloco de código várias vezes.** Imagine ter que escrever 100 vezes "println(número)" - seria muito trabalhoso! Com loops, fazemos isso em poucas linhas.

---

## 1. **Iteração Básica sobre uma Coleção**

- **Sintaxe**: `for (elemento in colecao) {...}`

```kotlin
val numeros = listOf(1, 2, 3, 4, 5)  
for (numero in numeros) {  
    println(numero)  
}
```

```console
1
2
3
4
5
```

O `for` percorre qualquer coleção que tenha um iterador. Isso significa que a coleção precisa ter funções especiais como `iterator()`, `next()` e `hasNext()` - mas não se preocupe, as coleções básicas do Kotlin já têm isso.

---

## 2. **Iteração com Índices**

- **Sintaxe**: `for (indice in colecao.indices) {...}`

```kotlin
val palavras = arrayOf("Kotlin", "é", "incrível")  
for (indice in palavras.indices) {  
    println("Palavra no índice $indice é ${palavras[indice]}")  
}
```

```console
Palavra no índice 0 é Kotlin
Palavra no índice 1 é é
Palavra no índice 2 é incrível
```

Útil quando você precisa saber a posição de cada elemento na coleção.

---

## 3. **Iteração com `withIndex()`**

- **Sintaxe**: `for ((indice, valor) in colecao.withIndex()) {...}`

```kotlin
val palavrasAlt = listOf("Kotlin", "é", "fantástico")  
for ((indice, palavra) in palavrasAlt.withIndex()) {  
    println("Palavra no índice $indice é $palavra")  
}
```

```console
Palavra no índice 0 é Kotlin
Palavra no índice 1 é é
Palavra no índice 2 é fantástico
```

Mais elegante que usar `.indices` quando você precisa tanto do índice quanto do valor.

---

## 4. **Iteração sobre um Intervalo**

- **Sintaxe**: `for (i in inicio..fim) {...}`

```kotlin
for (i in 1..5) {  
    println(i)  
}
```

```console
1
2
3
4
5
```

Perfeito para repetir algo um número específico de vezes.

---

## 5. **Iteração com Passo**

- **Sintaxe**: `for (i in inicio..fim step tamanhoDoSalto) {...}`

```kotlin
for (i in 1..10 step 2) {  
    println(i)  
}
```

```console
1
3
5
7
9
```

O `step` define quantos números pular a cada iteração.

---

## 6. **Iteração Reversa**

- **Sintaxe**: `for (i in fim downTo inicio) {...}`

```kotlin
for (i in 5 downTo 1) {  
    println(i)  
}
```

```console
5
4
3
2
1
```

Útil para contagem regressiva ou percorrer algo de trás para frente.

---

## 7. **Iteração sobre um Mapa**

- **Sintaxe**: `for ((chave, valor) in mapa) {...}`

```kotlin
val mapa = mapOf(1 to "um", 2 to "dois")  
for ((chave, valor) in mapa) {  
    println("$chave = $valor")  
}
```

```console
1 = um
2 = dois
```

Mapas são como dicionários - cada chave tem um valor correspondente.

---

## 8. **Iteração sobre Caracteres de uma String**

- **Sintaxe**: `for (caractere in string) {...}`

```kotlin
val texto = "Olá"  
for (caractere in texto) {  
    println(caractere)  
}
```

```console
O
l
á
```

Strings podem ser percorridas letra por letra.

---

## 9. **Filtrando Elementos Durante a Iteração**

- **Sintaxe**: `for (elemento in colecao.filter { ... }) {...}`

```kotlin
val numerosAlt = listOf(1, 2, 3, 4, 5)  
for (numero in numerosAlt.filter { it % 2 == 0 }) {  
    println(numero)  
}
```

```console
2
4
```

`filter` seleciona apenas os elementos que atendem uma condição (neste caso, números pares).

---

## 10. **Interrompendo ou Continuando o Loop**

- **`break`**: Sai do loop completamente.
- **`continue`**: Pula o resto da iteração atual e vai para a próxima.

```kotlin
for (i in 1..10) {  
    if (i == 5) break         // Para quando chegar no 5
    if (i % 2 == 0) continue  // Pula números pares
    println(i)  
}
```

```console
1
3
```

Primeiro imprime 1 e 3 (ímpares), pula 2 e 4 (pares), e para antes do 5.

---

## 11. **Loops Aninhados**

- **Sintaxe**: `for (elemento1 in colecao1) { for (elemento2 in colecao2) {...} }`

```kotlin
val matriz = listOf(listOf(1, 2), listOf(3, 4))  
for (linha in matriz) {  
    for (item in linha) {  
        println(item)  
    }  
}
```

```console
1
2
3
4
```

Um loop dentro de outro - útil para estruturas bidimensionais como tabelas.

---

## 12. **Loops com Rótulos**

- **Sintaxe**: `rotuloDoLoop@ for (...) {...}`

```kotlin
externo@ for (i in 1..5) {  
    for (j in 1..5) {  
        if (j == 3) break@externo  // Sai do loop externo, não só do interno
        println("i = $i, j = $j")  
    }  
}
```

```console
i = 1, j = 1
i = 1, j = 2
```

Rótulos permitem controlar qual loop específico você quer interromper em loops aninhados.

---

## Resumo dos Conceitos

### Tipos de For Loop

- **`for (item in lista)`** - Percorre cada elemento
- **`for (i in 1..10)`** - Percorre um intervalo numérico
- **`for (i in lista.indices)`** - Percorre pelos índices
- **`for ((indice, valor) in lista.withIndex())`** - Percorre com índice e valor

### Controle de Fluxo

- **`break`** - Sai do loop
- **`continue`** - Pula para próxima iteração
- **`break@rotulo`** - Sai de loop específico em loops aninhados

### Modificadores Úteis

- **`step 2`** - Define o incremento
- **`downTo`** - Vai em ordem decrescente
- **`.filter`** - Filtra elementos antes de iterar

---

## 📖 Glossário de Termos

### Conceitos de Loop

**Loop/Laço** - Estrutura que repete código **Iteration/Iteração** - Uma execução do loop **Iterator** - Objeto que permite percorrer uma coleção **Collection/Coleção** - Grupo de elementos (lista, array, etc.) **Element/Elemento** - Item individual dentro de uma coleção

### Controle de Fluxo

**Break** - Comando para sair do loop **Continue** - Comando para pular para próxima iteração **Label/Rótulo** - Nome dado a um loop para referenciá-lo **Nested loops** - Loops dentro de outros loops

### Estruturas de Dados

**List/Lista** - Coleção ordenada de elementos **Array** - Estrutura de dados com tamanho fixo **Map/Mapa** - Estrutura chave-valor (como dicionário) **Range/Intervalo** - Sequência de números (1..5) **Index/Índice** - Posição de um elemento (começa em 0)

### Operações

**Filter/Filtrar** - Selecionar elementos que atendem condição **Step/Passo** - Tamanho do incremento em cada iteração **downTo** - Operador para iterar em ordem decrescente **withIndex()** - Função que retorna índice e valor juntos

### Dica de Estudos

💡 **Pratique com exemplos simples!** Comece com listas pequenas e vá aumentando a complexidade. Loops são fundamentais na programação!