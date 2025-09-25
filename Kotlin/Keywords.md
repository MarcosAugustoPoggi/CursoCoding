# Keywords e Comentários

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

## Principais Keywords do Kotlin

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

#### **`class`** - Classe

```kotlin
class Pessoa {
    val nome: String = "João"
    
    fun apresentar() {
        println("Eu sou $nome")
    }
}
```

#### **`object`** - Objeto Singleton

```kotlin
object Configuracao {
    val versao = "1.0"
    fun info() = "App versão $versao"
}
```

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

// Com valores específicos
when (nota) {
    100 -> println("Perfeito!")
    in 90..99 -> println("Quase perfeito!")
    else -> println("Continue estudando!")
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

// Operador safe call
nome?.let { println("Nome: $it") }
```

#### **`is`** - Verificação de Tipo

```kotlin
val valor: Any = "Texto"

if (valor is String) {
    println("É uma string: $valor")
}

when (valor) {
    is String -> println("Texto: $valor")
    is Int -> println("Número: $valor")
    else -> println("Tipo desconhecido")
}
```

#### **`as`** - Conversão de Tipo

```kotlin
val numero: Any = 42
val numeroInt = numero as Int  // Conversão forçada

// Conversão segura
val numeroSeguro = numero as? Int  // Retorna null se não conseguir
```

---

### 🔧 Grupo 4: Modificadores

#### **`private`** - Privado

```kotlin
class MinhaClasse {
    private val segredo = "Só eu posso ver"
    
    private fun metodoSecreto() {
        println("Método privado")
    }
}
```

#### **`public`** - Público (padrão)

```kotlin
class MinhaClasse {
    public val visivel = "Todos podem ver"  // public é padrão
    val tambemVisivel = "Também público"    // mesmo sem escrever
}
```

#### **`internal`** - Interno ao Módulo

```kotlin
internal class ClasseInterna {
    internal fun funcaoInterna() {
        println("Visível apenas neste módulo")
    }
}
```

#### **`protected`** - Protegido (herança)

```kotlin
open class Pai {
    protected val heranca = "Filhos podem ver"
}

class Filho : Pai() {
    fun usar() {
        println(heranca)  // ✅ Pode acessar
    }
}
```

---

### 🎪 Grupo 5: Orientação a Objetos

#### **`open`** - Permite Herança

```kotlin
open class Animal {  // Pode ser herdada
    open fun som() = "Som genérico"
}

class Cachorro : Animal() {
    override fun som() = "Au au!"
}
```

#### **`override`** - Sobrescrever

```kotlin
class Gato : Animal() {
    override fun som() = "Miau!"  // Sobrescreve método do pai
}
```

#### **`abstract`** - Abstrato

```kotlin
abstract class Forma {
    abstract fun calcularArea(): Double  // Deve ser implementado
    
    fun info() {  // Método concreto
        println("Sou uma forma geométrica")
    }
}

class Retangulo(val largura: Double, val altura: Double) : Forma() {
    override fun calcularArea() = largura * altura
}
```

#### **`interface`** - Interface

```kotlin
interface Voador {
    fun voar()
    fun pousar() = println("Pousando...")  // Implementação padrão
}

class Passaro : Voador {
    override fun voar() {
        println("Voando com asas!")
    }
}
```

---

### 🎁 Grupo 6: Funcionalidades Especiais

#### **`data`** - Classe de Dados

```kotlin
data class Pessoa(val nome: String, val idade: Int)

val pessoa1 = Pessoa("Ana", 25)
val pessoa2 = Pessoa("Ana", 25)

println(pessoa1 == pessoa2)  // true (compara valores)
println(pessoa1)             // Pessoa(nome=Ana, idade=25)
```

#### **`sealed`** - Classe Selada

```kotlin
sealed class Resultado {
    data class Sucesso(val valor: String) : Resultado()
    data class Erro(val mensagem: String) : Resultado()
    object Carregando : Resultado()
}

fun processar(resultado: Resultado) = when (resultado) {
    is Resultado.Sucesso -> println("Sucesso: ${resultado.valor}")
    is Resultado.Erro -> println("Erro: ${resultado.mensagem}")
    Resultado.Carregando -> println("Carregando...")
}
```

#### **`companion`** - Objeto Companheiro

```kotlin
class MinhaClasse {
    companion object {
        const val CONSTANTE = "Valor fixo"
        
        fun criarInstancia() = MinhaClasse()
    }
}

// Uso sem criar instância
val instancia = MinhaClasse.criarInstancia()
println(MinhaClasse.CONSTANTE)
```


---

## Resumo da Aula

### Keywords Aprendidas Hoje

- **Declarações:** `fun`, `val`, `var`, `class`, `object`
- **Controle:** `if`, `else`, `when`, `for`, `while`
- **Tipos:** `null`, `is`, `as`
- **Modificadores:** `private`, `public`, `internal`, `protected`
- **OOP:** `open`, `override`, `abstract`, `interface`
- **Especiais:** `data`, `sealed`, `companion`

---

## 📖 Glossário de Termos da Aula

### Keywords/Palavras-chave

**Keywords** - Palavras reservadas da linguagem com significado específico **Case-sensitive** - Diferencia maiúsculas de minúsculas **Reserved words** - Palavras que não podem ser usadas como nomes

### Tipos de Declaração

**Function (fun)** - Bloco de código reutilizável que executa uma tarefa **Value (val)** - Declara uma constante (valor imutável) **Variable (var)** - Declara uma variável (valor mutável) **Class** - Modelo para criar objetos **Object** - Instância única de uma classe (singleton)

### Controle de Fluxo

**Conditional (if/else)** - Executa código baseado em condições **When expression** - Versão Kotlin do switch/case, mais poderosa **Loop/Laço** - Repetição de código (for, while) **Iteration** - Uma execução do loop

### Orientação a Objetos

**Inheritance (herança)** - Uma classe herda características de outra **Override** - Sobrescrever um método da classe pai **Abstract** - Classe ou método que deve ser implementado por subclasses **Interface** - Contrato que define métodos que uma classe deve implementar **Encapsulation** - Ocultar detalhes internos (private, public, etc.)

### Tipos e Nullabilidade

**Null** - Ausência de valor **Nullable** - Tipo que pode conter null (String?) **Non-null** - Tipo que nunca pode ser null (String) **Type checking** - Verificar o tipo de uma variável (is) **Type casting** - Converter entre tipos (as) **Safe call (?.)** - Operador que evita null pointer exceptions