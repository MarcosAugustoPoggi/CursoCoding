
## Comentários - Documentando seu Código

### Por que Comentar?

**Comentários são como "post-its" no seu código:**

- Explicam o que você estava pensando
- Ajudam outros programadores (e você mesmo no futuro)
- Não afetam a execução do programa

### 📝 Comentário de Linha Única

```kotlin
// Este é um comentário de uma linha
val nome = "João"  // Comentário no final da linha

// Comentários podem explicar código complexo
val resultado = (a * b) + (c / d)  // Fórmula matemática especial
```

**Quando usar:**

- Explicações rápidas
- Notas sobre código específico
- Lembretes temporários

### 📄 Comentário de Múltiplas Linhas

```kotlin
/*
   Este é um comentário de múltiplas linhas.
   Pode ocupar várias linhas e é útil para
   explicações mais longas ou documentação.
*/

fun algoritmoComplexo() {
    /*
       Este algoritmo resolve um problema específico:
       1. Primeiro faz isso
       2. Depois faz aquilo
       3. Por fim, retorna o resultado
    */
    
    // Código do algoritmo aqui...
}
```

**Quando usar:**

- Documentação de funções
- Explicações longas
- Cabeçalhos de arquivo
- Desabilitar código temporariamente

### 📚 Comentários de Documentação (KDoc)

```kotlin
/**
 * Calcula a área de um retângulo.
 * 
 * @param largura A largura do retângulo em metros
 * @param altura A altura do retângulo em metros
 * @return A área em metros quadrados
 * 
 * @throws IllegalArgumentException se largura ou altura forem negativas
 * 
 * @sample
 * val area = calcularArea(5.0, 3.0)  // Retorna 15.0
 */
fun calcularArea(largura: Double, altura: Double): Double {
    require(largura >= 0) { "Largura não pode ser negativa" }
    require(altura >= 0) { "Altura não pode ser negativa" }
    
    return largura * altura
}
```

**KDoc é usado para:**

- Documentação oficial da API
- Geração automática de documentação
- Ajuda em IDEs

### ❌ Como NÃO Comentar

```kotlin
// ❌ Ruim: óbvio demais
var contador = 0  // Declara uma variável contador com valor 0

// ❌ Ruim: comentário desatualizado
var idade = 30  // Idade da pessoa (na verdade agora é 25)

// ❌ Ruim: comentário longo demais para algo simples
/*
   Esta variável extremamente importante armazena
   o nome do usuário que será usado em toda a aplicação
   para identificar a pessoa logada no sistema...
*/
val usuario = "João"

// ✅ Bom: explica o "porquê"
val taxa = 0.12  // Taxa de juros do Banco Central para 2024

// ✅ Bom: explica código complexo
val resultado = list.filter { it > 0 }  // Remove números negativos
                   .map { it * 2 }      // Dobra os valores
                   .sum()               // Soma tudo
```

---

## Boas Práticas para Keywords e Comentários

### 🎯 Keywords

1. **Use nomes descritivos:** `val nomeCompleto` melhor que `val n`
2. **Seja consistente:** Sempre use o mesmo estilo
3. **Prefira `val` sobre `var`:** Imutabilidade é mais segura
4. **Use `when` em vez de múltiplos `if-else`**

### 💬 Comentários

1. **Explique o "porquê", não o "o quê"**
2. **Mantenha comentários atualizados**
3. **Use comentários para código complexo**
4. **Evite comentários óbvios**
5. **Comente decisões importantes**

---

## Exemplo Prático: Juntando Tudo

```kotlin
/**
 * Sistema simples de cadastro de pessoas.
 * Demonstra uso de keywords e boas práticas de comentários.
 */

// Classe de dados para representar uma pessoa
data class Pessoa(
    val nome: String,
    val idade: Int,
    val email: String?  // Email é opcional (pode ser null)
)

// Objeto para gerenciar o cadastro
object CadastroPessoas {
    // Lista mutável para armazenar pessoas
    private val pessoas = mutableListOf<Pessoa>()
    
    /**
     * Adiciona uma nova pessoa ao cadastro.
     * 
     * @param pessoa A pessoa a ser adicionada
     * @return true se adicionada com sucesso
     */
    fun adicionar(pessoa: Pessoa): Boolean {
        // Valida se a pessoa é maior de idade
        if (pessoa.idade < 18) {
            println("Erro: Apenas maiores de idade podem se cadastrar")
            return false
        }
        
        // Verifica se já existe pessoa com mesmo nome
        val jaExiste = pessoas.any { it.nome == pessoa.nome }
        if (jaExiste) {
            println("Erro: Pessoa com nome ${pessoa.nome} já existe")
            return false
        }
        
        pessoas.add(pessoa)
        return true
    }
    
    /**
     * Lista todas as pessoas por faixa etária.
     */
    fun listarPorIdade() {
        for (pessoa in pessoas) {
            val categoria = when {
                pessoa.idade < 25 -> "jovem"
                pessoa.idade < 60 -> "adulto" 
                else -> "sênior"
            }
            
            /*
               Mostra informações formatadas.
               Email é opcional, por isso usamos safe call (?.)
            */
            val emailInfo = pessoa.email?.let { "Email: $it" } ?: "Sem email"
            println("${pessoa.nome} ($categoria) - $emailInfo")
        }
    }
}

// Função principal para demonstrar o sistema
fun main() {
    // Criando algumas pessoas para teste
    val pessoa1 = Pessoa("Ana Silva", 28, "ana@email.com")
    val pessoa2 = Pessoa("João Santos", 17, null)  // Menor de idade
    val pessoa3 = Pessoa("Maria Oliveira", 45, "maria@email.com")
    
    // Tentando adicionar as pessoas
    CadastroPessoas.adicionar(pessoa1)  // Sucesso
    CadastroPessoas.adicionar(pessoa2)  // Erro: menor de idade
    CadastroPessoas.adicionar(pessoa3)  // Sucesso
    
    println("\n=== Lista de Pessoas ===")
    CadastroPessoas.listarPorIdade()
}
```

---

## Resumo da Aula

### Tipos de Comentários

- **Linha única:** `// comentário`
- **Múltiplas linhas:** `/* comentário */`
- **Documentação:** `/** KDoc */`

---

## 📖 Glossário de Termos da Aula

### Comentários

**Single-line comment** - Comentário de uma linha (//) **Multi-line comment** - Comentário de múltiplas linhas (/* _/) **Documentation comment** - Comentário para documentação (/_* */) **KDoc** - Sistema de documentação do Kotlin **API documentation** - Documentação da interface pública

### Dica de Estudos

💡 **Pratique escrevendo código!** As keywords se tornam naturais com o uso. Comece com exemplos simples e vá aumentando a complexidade gradualmente.