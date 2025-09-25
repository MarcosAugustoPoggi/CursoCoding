## Introdução: O que são Variáveis?
### Variáveis em Kotlin - val, var e Tipos de Dados

**Variáveis são como "caixas" onde guardamos informações para usar no nosso programa.**

### Analogia da Vida Real

```
🗃️ Gaveta "Nome" → Contém: "Maria Silva"
🗃️ Gaveta "Idade" → Contém: 25
🗃️ Gaveta "Salário" → Contém: 5000.50

No Kotlin:
val nome = "Maria Silva"    // Caixa que não pode ser trocada
var idade = 25              // Caixa que pode ser trocada
val salario = 5000.50       // Caixa com número decimal
```

**Diferença fundamental:**

- **`val`** = Caixa **lacrada** (valor não muda)
- **`var`** = Caixa **normal** (valor pode mudar)

---

## val vs var - A Diferença Crucial

### 🔒 `val` - Valor Imutável (Value)

```kotlin
val nome = "João"
val idade = 25
val pi = 3.14159

// Tentativa de mudança - ERRO!
// nome = "Pedro"     // ❌ Erro de compilação
// idade = 26         // ❌ Erro de compilação
```

**Quando usar `val`:**

- Quando o valor não vai mudar
- Para números fixos (como PI)
- Para configurações
- **Use `val` sempre que possível!**

### 🔄 `var` - Variável Mutável (Variable)

```kotlin
var contador = 0
var nome = "Ana"
var temperatura = 25.5

// Mudanças permitidas
contador = 1           // ✅ OK
contador = contador + 1 // ✅ OK
nome = "Beatriz"       // ✅ OK
temperatura = 30.2     // ✅ OK
```

**Quando usar `var`:**

- Quando o valor precisa mudar
- Para contadores
- Para dados que o usuário digita
- Para valores que são calculados e atualizados

---

## Declaração de Variáveis - Sintaxe

### Sintaxe Básica

```kotlin
// Padrão: palavra-chave nome = valor
val nomeCompleto = "Maria Silva"
var idade = 28

// Com tipo explícito (opcional na maioria das vezes)
val altura: Double = 1.75
var peso: Double = 65.5
```

### 🎯 Regras para Nomes de Variáveis

```kotlin
// ✅ Nomes válidos
val nome = "João"
val idade = 25
val numero1 = 10
val valorMaximo = 100

// ❌ Nomes inválidos
// val 1numero = 10      // Não pode começar com número
// val nome completo = "Ana" // Não pode ter espaço
// val if = "teste"      // 'if' é palavra reservada
```

**Dica:** Use nomes descritivos! `idade` é melhor que `i`.

---

## Tipos de Dados Fundamentais

### 🔢 Números Inteiros

```kotlin
// Int - números inteiros normais
val idade = 25
val pontos = 1500
var contador = 0

println("Idade: $idade")        // Idade: 25
println("Pontos: $pontos")      // Pontos: 1500
```

### 🎯 Números Decimais

```kotlin
// Double - números com casas decimais
val altura = 1.75
val preco = 29.90
val temperatura = 36.5

println("Altura: $altura metros")    // Altura: 1.75 metros
println("Preço: R$ $preco")         // Preço: R$ 29.9
```

### 📝 Texto (String)

```kotlin
// String - texto
val nome = "João Silva"
val cidade = "São Paulo"
var mensagem = "Olá, mundo!"

println("Nome: $nome")              // Nome: João Silva
println("Cidade: $cidade")          // Cidade: São Paulo
```

### ✅ Verdadeiro/Falso (Boolean)

```kotlin
// Boolean - true ou false
val estaLogado = true
val temPermissao = false
var jogoIniciado = false

println("Logado: $estaLogado")      // Logado: true
println("Permissão: $temPermissao") // Permissão: false
```

---

## String Templates - Colocando Variáveis no Texto

### Interpolação Básica com $

```kotlin
val nome = "Ana"
val idade = 28

println("Nome: $nome")              // Nome: Ana
println("Idade: $idade anos")       // Idade: 28 anos
println("Olá, $nome!")             // Olá, Ana!
```

### Cálculos Dentro do Texto com ${}

```kotlin
val preco = 25.90
val quantidade = 3

println("Preço: R$ $preco")                    // Preço: R$ 25.9
println("Total: R$ ${preco * quantidade}")     // Total: R$ 77.7
println("Nome maiúsculo: ${nome.uppercase()}") // Nome maiúsculo: ANA
```

---

## Conversão de Tipos (Casting)

### Conversões Básicas

```kotlin
// Número para texto
val numero = 42
val numeroTexto = numero.toString()
println("Número como texto: '$numeroTexto'")  // "42"

// Texto para número
val textoNumero = "123"
val numeroConvertido = textoNumero.toInt()
println("Texto como número: $numeroConvertido") // 123

// Int para Double
val inteiro = 10
val decimal = inteiro.toDouble()
println("Inteiro como decimal: $decimal")      // 10.0

// Double para Int (perde as casas decimais)
val valorDecimal = 10.75
val valorInteiro = valorDecimal.toInt()
println("Decimal como inteiro: $valorInteiro") // 10
```

### Exemplo Prático de Conversões

```kotlin
fun main() {
    // Simulando entrada do usuário (como texto)
    val idadeTexto = "25"
    val alturaTexto = "1.75"
    
    // Convertendo para números
    val idade = idadeTexto.toInt()
    val altura = alturaTexto.toDouble()
    
    println("Idade: $idade anos")
    println("Altura: $altura metros")
    
    // Fazendo cálculos
    val anosRestantes = 100 - idade
    val alturaEmCm = altura * 100
    
    println("Anos até os 100: $anosRestantes")
    println("Altura em cm: ${alturaEmCm.toInt()}")
    
    // Conversões para texto
    val relatorio = "Pessoa de $idade anos e ${alturaEmCm.toInt()}cm"
    println(relatorio)
}
```

### Conversões Comuns

```kotlin
// Principais conversões
val texto = "42"
val numero = 123
val decimal = 45.67
val verdadeiro = true

// Para String
val numeroTexto = numero.toString()       // "123"
val decimalTexto = decimal.toString()     // "45.67"
val booleanoTexto = verdadeiro.toString() // "true"

// Para Int
val textoParaInt = texto.toInt()          // 42
val decimalParaInt = decimal.toInt()      // 45 (corta decimais)

// Para Double  
val textoParaDouble = texto.toDouble()    // 42.0
val inteiroParaDouble = numero.toDouble() // 123.0

// Para Boolean
val textoParaBoolean = "true".toBoolean() // true
```

---

## Null Safety - Lidando com Valores Vazios

### Tipos que Podem ser Null

```kotlin
// Normal: nunca pode ser null
var nome: String = "João"
// nome = null  // ❌ ERRO!

// Nullable: pode ser null (com ?)
var nomeOpcional: String? = "João"
nomeOpcional = null  // ✅ OK

var idade: Int? = 25
idade = null  // ✅ OK
```

### Trabalhando com Valores Null

```kotlin
val nome: String? = null

// Verificação simples
if (nome != null) {
    println("Nome: $nome")
} else {
    println("Nome não informado")
}

// Operador seguro (?.)
println("Tamanho do nome: ${nome?.length}")  // null se nome for null

// Valor padrão com ?:
val nomeSeguro = nome ?: "Sem nome"
println("Nome: $nomeSeguro")  // "Sem nome" se nome for null
```

---

## Exemplos Práticos Simples

### Exemplo 1: Calculadora Básica

```kotlin
fun main() {
    val numero1 = 10
    val numero2 = 3
    
    val soma = numero1 + numero2
    val subtracao = numero1 - numero2
    val multiplicacao = numero1 * numero2
    val divisao = numero1.toDouble() / numero2  // Conversão para ter decimais
    
    println("$numero1 + $numero2 = $soma")
    println("$numero1 - $numero2 = $subtracao") 
    println("$numero1 × $numero2 = $multiplicacao")
    println("$numero1 ÷ $numero2 = $divisao")
}
```

### Exemplo 2: Informações Pessoais

```kotlin
fun main() {
    val nome = "Maria"
    val sobrenome = "Silva"
    var idade = 28
    val altura = 1.65
    val estaEmpregada = true
    
    // String template com múltiplas variáveis
    val nomeCompleto = "$nome $sobrenome"
    
    println("=== INFORMAÇÕES PESSOAIS ===")
    println("Nome completo: $nomeCompleto")
    println("Idade: $idade anos")
    println("Altura: $altura metros")
    println("Empregada: $estaEmpregada")
    
    // Fazendo aniversário
    idade = idade + 1
    println("Após aniversário: $idade anos")
    
    // Conversões
    val alturaTexto = altura.toString()
    val idadeTexto = idade.toString()
    println("Idade como texto: '$idadeTexto'")
    println("Altura como texto: '$alturaTexto'")
}
```

### Exemplo 3: Trabalhando com Conversões

```kotlin
fun main() {
    // Simulando dados de entrada como texto
    val precoTexto = "49.90"
    val quantidadeTexto = "2"
    val descontoTexto = "10"
    
    // Convertendo para números
    val preco = precoTexto.toDouble()
    val quantidade = quantidadeTexto.toInt()
    val desconto = descontoTexto.toInt()
    
    // Calculando
    val subtotal = preco * quantidade
    val valorDesconto = subtotal * desconto / 100
    val total = subtotal - valorDesconto
    
    // Mostrando resultados
    println("=== CUPOM FISCAL ===")
    println("Preço unitário: R$ $preco")
    println("Quantidade: $quantidade")
    println("Subtotal: R$ $subtotal")
    println("Desconto ($desconto%): R$ $valorDesconto")
    println("TOTAL: R$ $total")
    
    // Convertendo resultado final para texto
    val totalTexto = total.toString()
    println("Total como texto: '$totalTexto'")
}
```

---

## Melhores Práticas Simples

### ✅ Prefira `val` sobre `var`

```kotlin
// ✅ Bom: usa val quando não vai mudar
val nome = "João"
val pi = 3.14159

// ✅ Use var apenas quando precisa mudar
var contador = 0
contador = contador + 1
```

### ✅ Nomes Descritivos

```kotlin
// ✅ Bom: nomes claros
val nomeCompleto = "Maria Silva"
val idadeUsuario = 25  

// ❌ Evite: nomes genéricos
val n = "Maria Silva"
val x = 25
```

### ✅ Use String Templates

```kotlin
val nome = "Ana"
val idade = 30

// ✅ Bom: string template
println("$nome tem $idade anos")

// ❌ Evite: concatenação com +
println(nome + " tem " + idade + " anos")
```

---

## Resumo da Aula

### Conceitos Principais

**`val` vs `var`:**

- **`val`** = não pode mudar (prefira este)
- **`var`** = pode mudar (use quando necessário)

**Tipos Básicos:**

- **Int** para números inteiros (25, 100, -5)
- **Double** para números decimais (1.75, 29.90)
- **String** para texto ("João", "Olá mundo")
- **Boolean** para verdadeiro/falso (true, false)

**String Templates:**

- **$variavel** para colocar variável no texto
- **${expressao}** para cálculos no texto

**Conversões:**

- **.toString()** para converter qualquer coisa em texto
- **.toInt()** para converter texto em número inteiro
- **.toDouble()** para converter texto em número decimal

**Null Safety:**

- **Tipo?** pode ser null
- **Tipo** nunca pode ser null
- Use **?.** para acessar com segurança

---

## 📖 Glossário de Termos da Aula

### Variáveis Básicas

**Variable (var)** - Caixa que pode ter seu conteúdo alterado **Value (val)** - Caixa lacrada, conteúdo não pode ser alterado **Declaration** - Criar uma variável (val nome = "João") **Assignment** - Dar um valor para uma variável (nome = "Pedro") **Initialization** - Dar o primeiro valor para uma variável

### Tipos de Dados

**Int** - Números inteiros (1, 2, 100, -50) **Double** - Números com casas decimais (1.5, 29.90, -10.75) **String** - Texto ("Olá", "João Silva") **Boolean** - Verdadeiro ou falso (true, false) **Type** - O "tipo" de dado que uma variável guarda

### String Templates

**String interpolation** - Colocar valor de variável dentro de texto **Template** - Usar $ para inserir variáveis em strings **Expression** - Cálculo dentro de ${} em strings

### Conversões (Casting)

**Type conversion** - Mudar um tipo para outro **toString()** - Converter qualquer valor para texto **toInt()** - Converter texto para número inteiro **toDouble()** - Converter texto para número decimal **toBoolean()** - Converter texto