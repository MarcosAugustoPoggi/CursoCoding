
### 1. **Tipos Primitivos*

Estes são os tipos de dados básicos em Java, usados para armazenar valores simples.

- **`int`**: Números inteiros
  ```java
  int idade = 25;
  ```

- **`float`**: Números de ponto flutuante de precisão simples (decimais)
  ```java
  float altura = 1.75f;
  ```

- **`double`**: Números de ponto flutuante de precisão dupla (decimais)
  ```java
  double peso = 70.5;
  ```

- **`char`**: Um único caractere
  ```java
  char inicial = 'M';
  ```

- **`boolean`**: Verdadeiro ou falso
  ```java
  boolean ativo = true;
  ```

- **`byte`**: Números inteiros pequenos (8 bits)
  ```java
  byte pequenosNumeros = 127;
  ```

- **`short`**: Números inteiros de 16 bits
  ```java
  short pequenoNumero = 1000;
  ```

- **`long`**: Números inteiros grandes (64 bits)
  ```java
  long grandeNumero = 123456789L;
  ```

### 2. **Tipos de Referência**

Estes são usados para objetos e arrays, baseados em classes.

- **`String`**: Cadeia de caracteres
  ```java
  String nome = "Marcos";
  ```

- **`Array`**: Conjunto de elementos do mesmo tipo
  ```java
  int[] numeros = {1, 2, 3, 4};
  ```

- **`Classes e Objetos`**: Instâncias de classes personalizadas
  ```java
  MinhaClasse objeto = new MinhaClasse();
  ```

### 3. **Inferência de Tipo com `var` (Java 10+)**

Java 10 introduziu a palavra-chave `var` para permitir a inferência de tipo pelo compilador.

- **`var`**: O tipo é inferido pelo compilador
  ```java
  var idade = 25;  // inferido como int
  var nome = "Marcos";  // inferido como String
  ```

### Resumo

- **Primitivos**: `int`, `float`, `double`, `char`, `boolean`, `byte`, `short`, `long`
- **Referência**: `String`, `Array`, `Classes e Objetos`
- **Inferência**: `var` para inferir o tipo automaticamente

Esses tipos cobrem a maioria das necessidades de armazenamento de dados em Java e são fundamentais para a construção de programas Java.