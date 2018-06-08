# Tipo de dados e objetos de dados 

Uma descrição formal de uma variável é uma categoria de dados **(data type)**. Inversamente, uma variável ou uma constante definida concretamente por meio de uma tipo de dados é um objeto de dados **(data object)**.

Pode-se usar tipos de dados nas situações a seguir:

1. *Definição de objetos de dados*:
A categoria de um objeto de dados define suas propriedades técnicas (e, possivelmente, também semânticas).

2. *Definição de parâmetros da interface:*
O tipo de um parâmetro da interface determina o tipo do próprio parâmetro que é transferido quando se chama a unidade de modularização.

3. *Definição de campos de entrada/saída:*
O tipo de um campo de entrada/saída pode fornecer outras informações além das características técnicas, como a ajuda de campo e de entrada de valores.

## Tipos ABAP padrão (*standard data types*)

- Divididos em dois grupos: tipos **completos** e **incompletos**.

#### **Completos** 

- Eles já contêm uma especificação de comprimento fixa e específica de tipo:

|Standard Types|Descrição  |
|--|--|
|  D (date)| formato: AAAAMMDD, comprimento 8 (fixo) |
| T (time) | formato: HHMMSS, comprimento 6 (fixo) |
| I (integer) | comprimento 4 (fixo) |
|F (float)|comprimento 8 (fixo)|
|STRING|T ipo para cadeia de caracteres com comprimento dinâmico|
|XSTRING|Tipo para sequência de bytes com comprimento dinâmico (Cadeia
heX adecimal)|
|DECFLOAT16|**DEC**imal **FLOAT**ing point - Números com mantissa e expoente. comprimento de 8 bytes com 16 casas decimais. A partir da versão 7.0 EhP2 |
|DECFLOAT34|**DEC**imal **FLOAT**ing point - Números com mantissa e expoente. Comprimento de 16 bytes com 34 casas decimais. A partir da versão 7.0 EhP2 |

#### **Incompletos**
- Não tem comprimento fixo. Quando utilizados precisam vir com o comprimento da variável discriminado.

|Standard Types|Descrição  |
|--|--|
|C|Tipo para cadeia de caracteres ( **C**aractere) para a qual se deve indicar o comprimento fixo|
|N|Tipo para cadeia de caracteres numéricos (caractere **N**umérico) para a qual se deve indicar o comprimento fixo.|
|X|Tipo para sequência de bytes (cadeia He**X**adecimal) para a qual se deve indicar o comprimento fixo.|
|P|Tipo para número compactado (número Com**P**actado) para a qual se deve indicar o comprimento fixo. Na definição de um número compactado, também é possível indicar o número de casas decimais.|

#### Tipos de dados locais

- Declarados localmente (no programa). Po;
- 

> Nota: 

> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTU0MzQ1MjQ5LC0xMTgxMzc1MzM2XX0=
-->