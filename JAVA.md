
**JVM**
A Java Virtual Machine é uma máquina virtual que fornece uma camada de abstração entre o código-fonte Java e o sistema operacional, permitindo que o código Java seja executado em qualquer plataforma que tenha uma JVM instalada.

O processo de execução de um programa Java envolve várias etapas, desde o código-fonte até a execução final como código de máquina.

1 - **Compilação do Código-Fonte para Bytecode:**

```java
// Hello world em java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```

- Quando você compila o código acima usando o compilador Java (`javac HelloWorld.java`), o compilador gera um arquivo `.class` contendo o bytecode. Este bytecode é uma representação intermediária do código, que não é específico de nenhuma plataforma.

Um trecho do bytecode gerado pode parecer algo assim:
```
0:  getstatic     #2 // Field java/lang/System.out:Ljava/io/PrintStream;
3:  ldc           #3 // String Hello, World!
5:  invokevirtual #4 // Method java/io/PrintStream.println:(Ljava/lang/String;)V
8:  return
```

Este bytecode não é código de máquina, mas sim instruções que a JVM entende e pode processar.

**2 - Carregamento e Interpretação pela JVM**

Quando você executa o programa (`java HelloWorld`), a JVM carrega o bytecode do arquivo `HelloWorld.class`. Inicialmente, a JVM interpreta este bytecode, o que significa que ela lê as instruções uma por uma e as executa.

**3 - Compilação Just-In-Time (JIT) para Código de Máquina**

Durante a execução, a JVM usa o compilador Just-In-Time (JIT) para converter o bytecode em código de máquina nativo, que é específico para o processador do sistema. Esse código nativo é então executado diretamente pela CPU, permitindo que o programa funcione.

Depois de compilado, o código de máquina nativo é armazenado em cache pela JVM. Isso significa que na próxima vez que o código for executado, ele não precisará ser recompilado, resultando em uma execução muito mais rápida.

O código de máquina seria algo assim:
```
B8 01 00 00 00             ; mov eax, 1         (Chamada de sistema para saída)
BB 01 00 00 00             ; mov ebx, 1         (Saída padrão - stdout)
B9 00 60 40 00             ; mov ecx, 0x406000  (Endereço da string "Hello, World!")
BA 0D 00 00 00             ; mov edx, 13        (Tamanho da string)
CD 80                      ; int 0x80           (Chamada de interrupção para executar)

B8 01 00 00 00             ; mov eax, 1         (Chamada de sistema para saída)
31 DB                      ; xor ebx, ebx       (Código de saída 0)
CD 80                      ; int 0x80           (Interrupção para sair)

```


### **Resumo do Processo com HelloWorld.java**

1. **Código-Fonte (`HelloWorld.java`) → Bytecode (`HelloWorld.class`)**:
	- O código Java é compilado em bytecode pelo `javac`.
2. **Bytecode (`HelloWorld.class`) → Código de Máquina Nativo**:
	- A JVM carrega e interpreta o bytecode.
	- O JIT converte o bytecode em código de máquina nativo durante a execução.

Este processo permite que o código Java seja executado em qualquer sistema com uma JVM, transformando o código Java em instruções que o processador pode entender e executar.


Link para download da JDK Oracle:
https://www.oracle.com/java/technologies/downloads/#java17

Opção de gerenciador de SDKs SDKMAN
https://sdkman.io

É bom usar o SDKMAN! para gerenciar versões de Java e outros SDKs porque ele facilita a instalação, atualização e troca entre diferentes versões de SDKs com comandos simples. Ele automatiza a configuração do ambiente, economiza tempo, e evita conflitos entre versões, especialmente em projetos que exigem diferentes versões de Java ou outras ferramentas.
