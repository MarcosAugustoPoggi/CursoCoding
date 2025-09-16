
# Evolução das Linguagens de Programação

## 1. Assembly (1940s-1950s)
**Características:**
- Linguagem de baixo nível, próxima ao código de máquina
- Cada instrução corresponde quase diretamente a uma operação do processador
- Específica para cada arquitetura de processador
- Controle total sobre hardware e memória

**Exemplo conceitual:**
```assembly
MOV AX, 5    ; Move valor 5 para registro AX
ADD AX, 3    ; Adiciona 3 ao valor em AX
```

**Importância:** Base fundamental - todas as linguagens eventualmente se traduzem para assembly/código de máquina.

---

![[NBFft.png]]

## 2. C (1972)
**Criador:** Dennis Ritchie (Bell Labs)

![[c02_08_01.gif]]


**Características:**
- Linguagem de nível médio (entre assembly e linguagens de alto nível)
- Gerenciamento manual de memória (malloc/free)
- Compilada para código nativo
- Sintaxe limpa e expressiva
- Base para sistemas operacionais (Unix/Linux)

**Exemplo:**
```c
#include <stdio.h>
int main() {
    printf("Hello, World!");
    return 0;
}
```

**Influência:** Estabeleceu sintaxe que influenciou praticamente todas as linguagens modernas (chaves {}, ponto e vírgula, etc.).

---

## 3. C++ (1985)
**Criador:** Bjarne Stroustrup

![[funcao-cpp.drawio-2.webp]]

**Características:**
- Extensão do C com Programação Orientada a Objetos (POO)
- Múltiplos paradigmas: procedural, orientado a objetos, genérico
- Compilada, performance alta
- Complexidade maior que C

**Exemplo:**
```cpp
#include <iostream>
using namespace std;

class MinhaClasse {
public:
    void saudar() {
        cout << "Olá do C++!" << endl;
    }
};
```

**Influência:** Popularizou POO e inspirou Java, C#, e outras linguagens orientadas a objetos.

---

## 4. Java (1995)
**Criador:** James Gosling (Sun Microsystems)

![[Jteqd.png]]

**Características:**
- "Write Once, Run Anywhere" - portabilidade via JVM
- Orientada a objetos pura
- Gerenciamento automático de memória (Garbage Collection)
- Tipagem estática forte
- Compilada para bytecode

**Exemplo:**
```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```

**Influência:** Demonstrou viabilidade de máquinas virtuais e influenciou C#, Kotlin, Scala.

---

## 5. Kotlin (2011)
**Criador:** JetBrains

![[kotlin_1440.png]]

**Características:**
- **Interoperabilidade 100% com Java** - usa a mesma JVM
- **Null Safety** - sistema de tipos previne NullPointerException
- **Sintaxe concisa e expressiva** - menos código verboso que Java
- **Multiplatform** - Android, JVM, JavaScript, Native
- **Orientada a objetos + Funcional** - paradigmas combinados
- **Compilada** para bytecode JVM (ou JavaScript/nativo)

**Exemplo:**
```kotlin
data class Pessoa(val nome: String, val idade: Int)

fun saudar(pessoa: Pessoa?) {
    pessoa?.let { 
        println("Olá, ${it.nome}! Você tem ${it.idade} anos.")
    } ?: println("Pessoa não encontrada")
}

// Uso
val pessoa = Pessoa("Maria", 25)
saudar(pessoa)
```

**Por que Kotlin é importante:**
- **Android:** Linguagem oficial preferida do Google desde 2019
- **Solve Java's pain points:** Verbosidade, null pointer exceptions, boilerplate
- **Interoperabilidade:** Migração gradual de projetos Java existentes
- **Multiplatform:** Uma linguagem para múltiplas plataformas

**Influências que Kotlin recebeu:**
- **Java:** Base da JVM, orientação a objetos
- **Scala:** Funcionalidades funcionais, expressividade
- **C#:** Null safety, propriedades
- **Swift:** Sintaxe limpa, optionals (similar ao null safety)
- **JavaScript:** Flexibilidade, funções de alta ordem

---

## 6. JavaScript (1995)
**Criador:** Brendan Eich (Netscape)

![[JS.png]]

**Características:**
- Originalmente para web browsers
- Interpretada (hoje também JIT compiled)
- Tipagem dinâmica e fraca
- Multiparadigma: funcional, orientada a objetos, procedural
- Baseada em protótipos, não classes (até ES6)

**Exemplo:**
```javascript
function saudar(nome) {
    return `Olá, ${nome}!`;
}
console.log(saudar("Mundo"));
```

**Influência:** Provou que linguagens dinâmicas podem ser poderosas; inspirou TypeScript, popularizou programação funcional.

---

## 7. Python (1991)
**Criador:** Guido van Rossum

![[python.png]]

**Características:**
- Filosofia: "código legível e simples"
- Tipagem dinâmica forte
- Interpretada
- Multiparadigma
- Sintaxe baseada em indentação
- Bibliotecas extensas

**Exemplo:**
```python
def saudar(nome):
    return f"Olá, {nome}!"

print(saudar("Mundo"))
```

**Influência:** Demonstrou que simplicidade e legibilidade são fundamentais; influenciou Go, Swift, Ruby.

---

## Linguagens Complementares Importantes

### Fortran (1957)
- Primeira linguagem de alto nível
- Focada em computação científica
- Ainda usada em supercomputação

### COBOL (1959)
- Linguagem para negócios
- Ainda executa grande parte do sistema financeiro mundial
- Demonstrou importância de linguagens específicas para domínios

### Lisp (1958)
- Segunda linguagem de alto nível
- Introduziu conceitos funcionais
- Influenciou JavaScript, Python, e linguagens funcionais modernas

### SQL (1970s)
- Linguagem específica para bancos de dados
- Demonstrou poder de Domain-Specific Languages (DSLs)

---

## Linha do Tempo da Influência

```
1940s-50s: Assembly → Base de tudo

1970s: C → Sintaxe fundamental
    ↓
1980s: C++ → Orientação a Objetos
    ↓
1990s: Java → Máquinas Virtuais + OOP refinada
       JavaScript → Dinamismo + Funcional
       Python → Simplicidade + Legibilidade
    ↓
2010s: Kotlin → Interoperabilidade + Null Safety + Multiplatform

2000s+: Linguagens modernas combinam os melhores aspectos
```

---

## Paradigmas e Evolução

### Evolução dos Paradigmas:
1. **Procedural** (C, Assembly) → Sequência de instruções
2. **Orientado a Objetos** (C++, Java) → Modelagem com classes e objetos
3. **Funcional** (influência do Lisp, presente em JS e Python) → Funções como cidadãos de primeira classe
4. **Multiparadigma** (Python, JavaScript) → Flexibilidade de escolha

### Tendências Observadas:
- **Abstração crescente**: De controle direto do hardware para conceitos de alto nível
- **Segurança de tipos**: De assembly (sem tipos) para sistemas de tipos sofisticados
- **Gerenciamento de memória**: Manual → Automático (Garbage Collection)
- **Portabilidade**: Específico de máquina → "Write once, run anywhere"
- **Expressividade**: Menos código para expressar a mesma ideia

---

## Influências Cruzadas Principais

**C influenciou:**
- Sintaxe de praticamente todas as linguagens modernas
- Modelo de compilação

**C++ influenciou:**
- Java (OOP, mas simplificou herança múltipla)
- C# (criado pela Microsoft como resposta ao Java)

**Java influenciou:**
- C# (quase um "clone" melhorado)
- Popularizou JVMs e bytecode

**JavaScript influenciou:**
- Mostrou poder da tipagem dinâmica
- Programação funcional mainstream

**Python influenciou:**
- Importância da legibilidade
- Linguagens como Go, Swift (sintaxe mais limpa)

---

## Conceitos Fundamentais

### Linguagens Compiladas vs. Interpretadas vs. Script

#### **Linguagens Compiladas**
**Como funcionam:** Código fonte é traduzido completamente para código de máquina antes da execução.

**Exemplos:** C, C++, Go, Rust

**Processo:**
```
Código Fonte (.c) → Compilador → Executável (.exe) → Execução
```

**Vantagens:**
- Performance alta (código nativo)
- Detecção de erros em tempo de compilação
- Não precisa do compilador na máquina final

**Desvantagens:**
- Processo de desenvolvimento mais lento
- Específico para cada arquitetura/sistema operacional

---

#### **Linguagens Interpretadas**
**Como funcionam:** Código é lido e executado linha por linha por um interpretador.

**Exemplos:** Python (CPython), JavaScript (em browsers), PHP

**Processo:**
```
Código Fonte (.py) → Interpretador → Execução direta
```

**Vantagens:**
- Desenvolvimento mais rápido (sem compilação)
- Portabilidade (mesmo código em diferentes sistemas)
- Interativo (REPL - Read-Eval-Print Loop)

**Desvantagens:**
- Performance menor
- Precisa do interpretador instalado
- Alguns erros só aparecem em tempo de execução

---

#### **Linguagens Script**
**Conceito:** Normalmente interpretadas, focadas em automatizar tarefas e "colar" sistemas.

**Exemplos:** Python, JavaScript, Bash, PowerShell, Perl

**Características:**
- Tipagem geralmente dinâmica
- Sintaxe concisa
- Bibliotecas ricas para tarefas comuns
- Execução direta sem compilação explícita

**Exemplo Python (script):**
```python
#!/usr/bin/env python3
# Automatiza backup de arquivos
import shutil
import os

for arquivo in os.listdir('.'):
    if arquivo.endswith('.txt'):
        shutil.copy(arquivo, 'backup/')
        print(f'Backup de {arquivo} realizado')
```

---

#### **Híbridas e Casos Especiais**

**Java - Compilada + Interpretada:**
```
Código Java (.java) → Compilador javac → Bytecode (.class) → JVM interpreta/compila
```

**JavaScript Moderno:**
- Interpretado + JIT (Just-In-Time) compilation
- V8 (Chrome) compila para código nativo durante execução

**Python:**
- Interpretado, mas gera bytecode (.pyc) internamente
- PyPy usa JIT compilation

---

### Gerenciamento de Memória

#### **Gerenciamento Manual (C/C++)**

**malloc() e free():**
```c
#include <stdlib.h>
#include <stdio.h>

int main() {
    // Aloca memória para 10 inteiros
    int *numeros = malloc(10 * sizeof(int));
    
    if (numeros == NULL) {
        printf("Erro: não foi possível alocar memória\n");
        return 1;
    }
    
    // Usa a memória
    for(int i = 0; i < 10; i++) {
        numeros[i] = i * i;
    }
    
    // IMPORTANTE: libera a memória
    free(numeros);
    numeros = NULL; // Boa prática
    
    return 0;
}
```

**Problemas comuns:**
- **Memory leak:** Esquecer de chamar `free()`
- **Dangling pointer:** Usar ponteiro após `free()`
- **Double free:** Chamar `free()` duas vezes
- **Buffer overflow:** Escrever além do espaço alocado

---

#### **Gerenciamento Automático (Garbage Collection)**

**Como funciona:**
- Sistema monitora automaticamente objetos na memória
- Remove objetos que não são mais referenciados
- Linguagens: Java, Python, JavaScript, C#

**Exemplo Java:**
```java
public void exemploGC() {
    String texto = new String("Hello"); // Aloca memória
    texto = new String("World");        // Primeiro objeto vira "lixo"
    
    // Garbage Collector automaticamente limpa o primeiro "Hello"
    System.gc(); // Sugere limpeza (não garante)
}
```

**Vantagens:**
- Menos erros de memória
- Desenvolvimento mais rápido
- Código mais limpo

**Desvantagens:**
- Overhead de performance
- Pausas imprevistas (GC pause)
- Menos controle preciso

---

### Tipos de Sistemas de Tipos

#### **Tipagem Estática vs. Dinâmica**

**Estática (C, Java, C++):**
```c
int numero = 10;        // Tipo definido em tempo de compilação
numero = "texto";       // ERRO: não pode mudar tipo
```

**Dinâmica (Python, JavaScript):**
```python
numero = 10             # Tipo determinado em tempo de execução
numero = "texto"        # OK: pode mudar tipo
```

#### **Tipagem Forte vs. Fraca**

**Forte (Python):**
```python
numero = 10
texto = "5"
resultado = numero + texto  # ERRO: não converte automaticamente
```

**Fraca (JavaScript):**
```javascript
let numero = 10;
let texto = "5";
let resultado = numero + texto;  // OK: resultado = "105" (conversão automática)
```

---

### Paradigmas de Programação Detalhados

#### **Programação Procedural**
**Foco:** Sequência de funções que operam em dados

**Exemplo C:**
```c
// Dados globais
int conta = 0;

// Funções que operam nos dados
void depositar(int valor) {
    conta += valor;
}

int obter_saldo() {
    return conta;
}
```

#### **Programação Orientada a Objetos**
**Foco:** Objetos que encapsulam dados e comportamentos

**Exemplo Java:**
```java
class ContaBancaria {
    private int saldo;  // Encapsulamento
    
    public void depositar(int valor) {
        this.saldo += valor;
    }
    
    public int getSaldo() {
        return this.saldo;
    }
}
```

#### **Programação Funcional**
**Foco:** Funções como cidadãos de primeira classe, imutabilidade

**Exemplo JavaScript:**
```javascript
// Função como valor
const somar = (a, b) => a + b;

// Função de alta ordem
const numeros = [1, 2, 3, 4, 5];
const dobrados = numeros.map(x => x * 2);  // [2, 4, 6, 8, 10]
```

---

## Conceitos para Discussão em Aula

1. **Por que tantas linguagens diferentes?**
   - Diferentes problemas requerem diferentes ferramentas
   - Evolução tecnológica e mudança de necessidades
   - **Kotlin surge para resolver limitações do Java mantendo compatibilidade**

2. **Trade-offs fundamentais:**
   - Performance vs. Facilidade de desenvolvimento
   - Controle vs. Segurança
   - Flexibilidade vs. Simplicidade
   - **Kotlin tenta equilibrar todos esses aspectos**

3. **Como escolher uma linguagem?**
   - Tipo de aplicação
   - Equipe e recursos disponíveis
   - Performance necessária
   - Ecossistema e bibliotecas
   - **Por isso Kotlin é excelente: aproveita ecossistema Java + sintaxe moderna**

4. **O futuro das linguagens:**
   - Interoperabilidade (Kotlin com Java)
   - Multiplatform (uma linguagem, várias plataformas)
   - Safety by design (null safety, type safety)
   - Developer experience (ferramentas, sintaxe limpa)

---

## 📖 Glossário de Termos e Acrônimos

### Acrônimos de Linguagens

- **C** - Linguagem de programação (nome simples, sem acrônimo)
- **C++** - C Plus Plus (extensão do C)
- **OOP** - Object-Oriented Programming (Programação Orientada a Objetos)
- **POO** - Programação Orientada a Objetos (português)
- **JVM** - Java Virtual Machine (Máquina Virtual Java)
- **JIT** - Just-In-Time compilation (Compilação em Tempo de Execução)
- **GC** - Garbage Collection (Coleta de Lixo)
- **SQL** - Structured Query Language (Linguagem de Consulta Estruturada)
- **API** - Application Programming Interface (Interface de Programação)
- **SDK** - Software Development Kit (Kit de Desenvolvimento)

### Paradigmas de Programação

**Procedural** - Foco em funções/procedimentos que operam em dados 
**Orientado a Objetos** - Organização em objetos que encapsulam dados e comportamentos
**Funcional** - Baseado em funções matemáticas, sem efeitos colaterais
**Imperativo** - Descreve COMO fazer algo (passo a passo)
**Declarativo** - Descreve O QUE fazer (resultado desejado)
**Multiparadigma** - Suporta múltiplos estilos de programação

### Tipos de Linguagens

**Compilada** - Traduzida para código de máquina antes da execução
**Interpretada** - Executada linha por linha por um interpretador
**Script** - Geralmente interpretada, foca em automatização
**Híbrida** - Combina compilação e interpretação (ex: Java)

### Sistemas de Tipos

**Tipagem Estática** - Tipos definidos em tempo de compilação
**Tipagem Dinâmica** - Tipos determinados em tempo de execução
**Tipagem Forte** - Não faz conversões automáticas entre tipos
**Tipagem Fraca** - Faz conversões automáticas entre tipos
**Type Safety** - Sistema previne erros de tipo
**Null Safety** - Sistema previne erros de valores nulos

### Gerenciamento de Memória

**malloc()** - Função C para alocar memória dinamicamente
**free()** - Função C para liberar memória alocada
**Memory Leak** - Vazamento de memória (não liberada)
**Dangling Pointer** - Ponteiro para memória já liberada
**Buffer Overflow** - Escrita além do espaço alocado
**Garbage Collection** - Limpeza automática de memória
**Stack** - Área de memória para variáveis locais
**Heap** - Área de memória para objetos dinâmicos

### Processo de Desenvolvimento

**Código Fonte** - Código original escrito pelo programador
**Bytecode** - Código intermediário (ex: Java, Kotlin) 
**Código de Máquina** - Instruções específicas do processador
**Assembly** - Linguagem de baixo nível, próxima ao código de máquina
**Compilador** - Traduz código fonte para executável
**Interpretador** - Executa código fonte diretamente
**REPL** - Read-Eval-Print Loop (ambiente interativo)

### Conceitos Importantes

**Portabilidade** - Capacidade de rodar em diferentes sistemas
**Interoperabilidade** - Capacidade de linguagens trabalharem juntas
**Cross-platform** - Funciona em múltiplas plataformas
**Backward Compatibility** - Compatibilidade com versões anteriores
**Boilerplate** - Código repetitivo necessário
**Sintaxe** - Regras de escrita da linguagem
**Semântica** - Significado/comportamento do código
**Abstração** - Ocultar complexidade, focar no essencial
**Encapsulamento** - Agrupar dados e métodos relacionados

### Ferramentas e Ambiente

**IDE** - Integrated Development Environment (Ambiente de Desenvolvimento)
**Compiler** - Compilador
**Debugger** - Ferramenta para encontrar erros
**Profiler** - Ferramenta para analisar performance
**Version Control** - Controle de versões (ex: Git)
**Repository** - Repositório de código

### Extensões de Arquivo Comuns

**.c** - Código fonte C 
**.cpp, .cxx** - Código fonte C++
**.java** - Código fonte Java 
**.kt** - Código fonte Kotlin
**.py** - Código fonte Python
**.js** - Código fonte JavaScript
**.exe** - Executável Windows
**.class** - Bytecode Java/Kotlin
**.o** - Arquivo objeto (compilado mas não linkado)


💡 **Não se preocupe em decorar!** Estes termos se tornarão naturais conforme você programa. Use este glossário como referência quando encontrar termos desconhecidos nas aulas.