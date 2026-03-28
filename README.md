# CodingRodrigo

Base de conhecimento para aprendizado de programação, com foco no ecossistema JVM — especialmente **Java** e **Kotlin**. O conteúdo é organizado como um curso progressivo, indo desde conceitos fundamentais até aplicação prática, tudo escrito em português.

---

## O que é esse repositório?

Um vault [Obsidian](https://obsidian.md/) com anotações de estudo e material didático estruturado para quem está começando a programar. Cada tópico é explicado com analogias do cotidiano, exemplos de código funcionais e glossários de termos.

---

## Estrutura

```
CodingRodrigo/
├── Linha do Tempo.md       # Evolução das linguagens de programação
├── JVM e JDK.md            # Como funciona a JVM, JDK, JRE e compilação
├── Kotlin/
│   ├── Variáveis.md        # val, var, tipos de dados, null safety
│   ├── Keywords.md         # Palavras reservadas da linguagem
│   ├── For Loop.md         # Estruturas de repetição e iteração
│   ├── Comentários.md      # Boas práticas de comentários e KDoc
│   └── Soma.md             # Exemplo básico de função
├── JAVA/
│   ├── Java Basics.md      # Tipos primitivos e de referência
│   ├── Java JVM.md         # Pipeline de execução: .java → bytecode → máquina
│   ├── Java - Numeros.md   # Tabela de tipos numéricos com tamanhos e limites
│   └── Java Tipagem.md     # Tipagem forte e verificação em tempo de compilação
└── Imagens/                # Recursos visuais usados nas notas
```

---

## Conteúdo

### Fundamentos Gerais

| Arquivo | O que cobre |
|---|---|
| `Linha do Tempo.md` | História das linguagens desde Assembly (anos 40) até Kotlin/Python. Paradigmas, compilação vs interpretação, gerenciamento de memória e glossário com 80+ termos. |
| `JVM e JDK.md` | Arquitetura da JVM (Class Loader, Heap, Stack, GC), JIT compilation, diferença entre JDK/JRE/JVM, distribuições e versões LTS. |

### Kotlin

| Arquivo | O que cobre |
|---|---|
| `Variáveis.md` | `val` vs `var`, tipos básicos, templates de string, conversão de tipos, nullable types e boas práticas. |
| `Keywords.md` | Palavras-chave organizadas por grupo: declarações, controle de fluxo, OOP, modificadores de visibilidade e recursos avançados (`sealed`, `suspend`, `inline`). |
| `For Loop.md` | 12 padrões de loop: ranges, `step`, `downTo`, `withIndex`, filtros, `break`/`continue`, loops aninhados e labels. |
| `Comentários.md` | Comentários de linha, bloco e KDoc. Quando comentar, o que evitar e exemplos com código documentado. |

### Java

| Arquivo | O que cobre |
|---|---|
| `Java Basics.md` | Tipos primitivos (`int`, `double`, `char`, `boolean`, etc.) e tipos de referência. |
| `Java JVM.md` | Fluxo completo de execução: código-fonte → compilação → bytecode → JVM → JIT → código de máquina. |
| `Java - Numeros.md` | Tabela comparativa de tipos numéricos com tamanho em bits, intervalo e quando usar cada um. |
| `Java Tipagem.md` | Por que Java é fortemente tipado, como isso difere de JavaScript/Python e os benefícios em tempo de compilação. |

---

## Como usar

O repositório é um **vault Obsidian**. Para a melhor experiência:

1. Instale o [Obsidian](https://obsidian.md/)
2. Abra a pasta `CodingRodrigo` como vault
3. Navegue pelas notas com links internos e visualização em grafo

Também pode ser lido diretamente como arquivos Markdown em qualquer editor.

---

## Tecnologias

- **Linguagens estudadas:** Kotlin, Java
- **Plataforma:** JVM
- **Formato:** Markdown
- **Ferramenta:** Obsidian (com plugins `execute-code` e `obsidian-git`)
- **Controle de versão:** Git
