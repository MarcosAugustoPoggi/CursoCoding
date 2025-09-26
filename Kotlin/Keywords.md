# Kotlin - Keywords (Palavras-chave)
**ou palavras reservadas**

## Introdução: Aprendendo a "Linguagem" Kotlin

Assim como você aprendeu português com palavras, verbos e regras gramaticais, programar em Kotlin também tem seu vocabulário especial.

**A boa notícia:** O vocabulário do Kotlin é muito menor que qualquer idioma humano!

- **Português:** ~300.000 palavras
- **Kotlin:** ~80 palavras especiais (keywords)

Vamos aprender essas palavras em pequenos grupos, tornando tudo mais fácil de absorver.

---

## O que são Keywords (Palavras-chave)?

**Keywords** são palavras especiais que têm significado específico no Kotlin. São como "verbos" ou "conectivos" da linguagem - cada uma tem uma função específica.

### Analogia com Português

```
Português: "Se você estudar, então você aprenderá."
           ↓      ↓        ↓     ↓       ↓
Keywords:  if   (condição) then (ação) else (alternativa)

Kotlin:    if (idade >= 18) println("Maior de idade") else println("Menor")
           ↓                                            ↓
        Keywords que o Kotlin entende
```

### Regras das Keywords

1. **Reservadas**: Não podemos usar como nomes de variáveis
2. **Case-sensitive**: `if` ≠ `IF` ≠ `If`
3. **Fixas**: Sempre têm o mesmo significado

---

## Keywords Fundamentais (Aprendemos Agora)

### 📚 Grupo 1: Declarações Básicas

#### **`fun`** - Função

```kotlin
fun saudar() {
    println("Olá!")
}

fun calcular(a: Int, b: Int): Int {
    return a + b
}
```

_"fun" = function (função)_

#### **`val`** - Valor Imutável

```kotlin
val nome = "Maria"        // Não pode ser alterado
val idade = 25           // Constante
// nome = "João"         // ❌ ERRO!
```

_"val" = value (valor que não muda)_

#### **`var`** - Variável Mutável

```kotlin
var contador = 0         // Pode ser alterado
contador = 1            // ✅ OK
contador = contador + 1 // ✅ OK
```

_"var" = variable (variável que pode mudar)_

---

### 🔄 Grupo 2: Controle de Fluxo

#### **`if`** / **`else`** - Condições

```kotlin
val idade = 20

if (idade >= 18) {
    println("Maior de idade")
} else {
    println("Menor de idade")
}

// Kotlin permite if como expressão
val status = if (idade >= 18) "adulto" else "jovem"
```

#### **`when`** - Múltiplas Condições

```kotlin
val nota = 85

when {
    nota >= 90 -> println("Excelente!")
    nota >= 80 -> println("Muito bom!")
    nota >= 70 -> println("Bom")
    else -> println("Pode melhorar")
}
```

#### **`for`** - Laço/Loop

```kotlin
// Repetir ação
for (i in 1..5) {
    println("Número: $i")
}

// Iterar sobre lista
val nomes = listOf("Ana", "Bruno", "Carlos")
for (nome in nomes) {
    println("Olá, $nome!")
}
```

#### **`while`** - Laço com Condição

```kotlin
var contador = 1
while (contador <= 3) {
    println("Contador: $contador")
    contador++
}
```

---

### 🎯 Grupo 3: Tipos e Nullabilidade

#### **`null`** - Valor Nulo

```kotlin
var nome: String? = null  // Pode ser nulo
var idade: Int = 25       // Nunca pode ser nulo

// Verificação segura
if (nome != null) {
    println("Nome: $nome")
}
```

#### **`is`** - Verificação de Tipo

```kotlin
val valor: Any = "Texto"

if (valor is String) {
    println("É uma string: $valor")
}
```

#### **`return`** - Retornar Valor

```kotlin
fun somar(a: Int, b: Int): Int {
    return a + b  // Retorna o resultado
}

fun verificarIdade(idade: Int): String {
    if (idade >= 18) {
        return "Maior de idade"
    }
    return "Menor de idade"
}
```

---

### 🔧 Grupo 4: Controle de Loop

#### **`break`** - Sair do Loop

```kotlin
for (i in 1..10) {
    if (i == 5) {
        break  // Para o loop quando i for 5
    }
    println(i)
}
// Imprime: 1, 2, 3, 4
```

#### **`continue`** - Pular Iteração

```kotlin
for (i in 1..5) {
    if (i == 3) {
        continue  // Pula quando i for 3
    }
    println(i)
}
// Imprime: 1, 2, 4, 5
```

---

## Outras Keywords (Veremos Mais Tarde)

**Existem muitas outras keywords no Kotlin que aprenderemos nas próximas aulas:**

### 🏗️ Orientação a Objetos

- **`class`** - Para criar classes
- **`object`** - Para objetos únicos
- **`interface`** - Para contratos
- **`abstract`** - Para classes abstratas
- **`open`** - Para permitir herança
- **`override`** - Para sobrescrever métodos

### 🔐 Modificadores de Visibilidade

- **`private`** - Acesso privado
- **`public`** - Acesso público (padrão)
- **`internal`** - Acesso interno ao módulo
- **`protected`** - Acesso protegido (herança)

### ⚡ Funcionalidades Avançadas

- **`data`** - Para classes de dados
- **`sealed`** - Para classes seladas
- **`companion`** - Para objetos companheiros
- **`inline`** - Para funções inline
- **`suspend`** - Para programação assíncrona

### 🔧 Outras Úteis

- **`as`** - Para conversão de tipos
- **`in`** - Para verificar se está em coleção/range
- **`out`** - Para variância
- **`try`** - Para tratamento de erros
- **`catch`** - Para capturar erros
- **`finally`** - Para código que sempre executa

**Não se preocupe!** Vamos aprender essas keywords conforme precisarmos. Por agora, foque nas fundamentais.

---

## Exemplo Prático: Sistema de Notas

```kotlin
fun main() {
    val nomePrograma = "Sistema de Notas"
    var totalAlunos = 0
    
    println("=== $nomePrograma ===")
    
    val notas = listOf(85, 92, 78, 96, 88)
    
    for (nota in notas) {
        totalAlunos = totalAlunos + 1
        
        val conceito = when {
            nota >= 90 -> "A"
            nota >= 80 -> "B" 
            nota >= 70 -> "C"
            else -> "D"
        }
        
        println("Aluno $totalAlunos: Nota $nota - Conceito $conceito")
        
        if (nota < 70) {
            println("  ⚠️ Aluno precisa de recuperação!")
        }
    }
    
    val media = calcularMedia(notas)
    
    println("\nResumo:")
    println("Total de alunos: $totalAlunos")
    println("Média da turma: ${"%.1f".format(media)}")
    
    val statusTurma = if (media >= 80) "Excelente" else "Boa"
    println("Status da turma: $statusTurma")
}

fun calcularMedia(notas: List<Int>): Double {
    val soma = notas.sum()
    return soma.toDouble() / notas.size
}
```

---

## Resumo da Aula

### Keywords Aprendidas Hoje

- **Declarações:** `fun`, `val`, `var`
- **Controle:** `if`, `else`, `when`, `for`, `while`
- **Tipos:** `null`, `is`
- **Funções:** `return`
- **Loops:** `break`, `continue`

### Regras Importantes

1. **Keywords são reservadas** - não podem ser nomes de variáveis
2. **Case-sensitive** - `if` é diferente de `IF`
3. **Significado fixo** - sempre fazem a mesma coisa
4. **Fundamentais para programar** - são a base da linguagem

### Próxima Aula

- **Variáveis e tipos de dados em detalhes**
- **String templates e interpolação**
- **Operadores e expressões**

---

## 📖 Glossário de Termos da Aula

### Keywords/Palavras-chave

**Keywords** - Palavras reservadas da linguagem com significado específico **Case-sensitive** - Diferencia maiúsculas de minúsculas **Reserved words** - Palavras que não podem ser usadas como nomes **Function (fun)** - Bloco de código reutilizável que executa uma tarefa **Value (val)** - Declara uma constante (valor imutável) **Variable (var)** - Declara uma variável (valor mutável)

### Controle de Fluxo

**Conditional (if/else)** - Executa código baseado em condições **When expression** - Versão Kotlin do switch/case, mais poderosa **Loop/Laço** - Repetição de código (for, while) **Iteration** - Uma execução do loop **Break** - Comando para sair do loop **Continue** - Comando para pular para próxima iteração

### Tipos e Nullabilidade

**Null** - Ausência de valor **Nullable** - Tipo que pode conter null (String?) **Non-null** - Tipo que nunca pode ser null (String) **Type checking** - Verificar o tipo de uma variável (is) **Return** - Comando para retornar valor de uma função

### Conceitos Gerais

**Syntax** - Regras de escrita da linguagem **Expression** - Código que produz um valor **Statement** - Instrução que executa uma ação **Scope** - Alcance/visibilidade de uma variável ou função

### Dica de Estudos

💡 **Pratique escrevendo código!** As keywords se tornam naturais com o uso. Comece com exemplos simples e vá aumentando a complexidade gradualmente.