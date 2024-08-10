
Diferenças entre os tipos numéricos em Java, incluindo seus limites:

| Tipo       | Tamanho  | Valor Mínimo                      | Valor Máximo                        | Precisão (Para Decimais) |
|------------|----------|-----------------------------------|-------------------------------------|--------------------------|
| `byte`     | 8 bits   | -128                              | 127                                 | N/A                      |
| `short`    | 16 bits  | -32.768                           | 32.767                              | N/A                      |
| `int`      | 32 bits  | -2^31 (-2.147.483.648)            | 2^31 - 1 (2.147.483.647)            | N/A                      |
| `long`     | 64 bits  | -2^63 (-9.223.372.036.854.775.808)| 2^63 - 1 (9.223.372.036.854.775.807)| N/A                      |
| `float`    | 32 bits  | 1.4E-45                           | 3.4028235E38                        | Aproximadamente 6-7 dígitos |
| `double`   | 64 bits  | 4.9E-324                          | 1.7976931348623157E308              | Aproximadamente 15-16 dígitos |

- **`byte`**: É o menor tipo de dado inteiro, utilizado para economizar memória em grandes arrays.
- **`short`**: Usado para inteiros pequenos, similar ao `byte`, mas com um intervalo maior.
- **`int`**: Tipo de dado inteiro mais comum, adequado para a maioria das operações de números inteiros.
- **`long`**: Usado para inteiros muito grandes, onde `int` não é suficiente.
- **`float`**: Usado para números decimais com precisão simples, adequado para gráficos ou cálculos científicos onde a precisão absoluta não é crítica.
- **`double`**: Tipo padrão para números decimais, oferece maior precisão que `float`, usado em cálculos financeiros e científicos.

### Resumo:

- **Inteiros:** `byte`, `short`, `int`, `long` — variam em tamanho e limites, mas não suportam decimais.
- **Ponto Flutuante:** `float`, `double` — usados para números decimais, com `double` oferecendo maior precisão.