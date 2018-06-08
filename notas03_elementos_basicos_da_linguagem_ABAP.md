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

### **Completos** 

- Eles já contêm uma especificação de comprimento fixa e específica de tipo:

|Standard Types|Descrição  |
|--|--|
|  D (date)| formato: AAAAMMDD, comprimento 8 (fixo) |
| T (time) | formato: HHMMSS, comprimento 6 (fixo) |
| I (integer) | comprimento 4 (fixo) |
|F (float)|comprimento 8 (fixo)|
|STRING|T ipo para cadeia de caracteres com comprimento dinâmico|
|XSTRING|Tipo para sequência de bytes com comprimento dinâmico (Cadeia heX adecimal)|
|DECFLOAT16|**DEC**imal **FLOAT**ing point - Números com mantissa e expoente. comprimento de 8 bytes com 16 casas decimais. A partir da versão 7.0 EhP2 |
|DECFLOAT34|**DEC**imal **FLOAT**ing point - Números com mantissa e expoente. Comprimento de 16 bytes com 34 casas decimais. A partir da versão 7.0 EhP2 |

### **Incompletos**
- Não tem comprimento fixo. Quando utilizados precisam vir com o comprimento da variável discriminado.

|Standard Types|Descrição  |
|--|--|
|C|Tipo para cadeia de caracteres ( **C**aractere) para a qual se deve indicar o comprimento fixo|
|N|Tipo para cadeia de caracteres numéricos (caractere **N**umérico) para a qual se deve indicar o comprimento fixo.|
|X|Tipo para sequência de bytes (cadeia He**X**adecimal) para a qual se deve indicar o comprimento fixo.|
|P|Tipo para número compactado (número Com**P**actado) para a qual se deve indicar o comprimento fixo. Na definição de um número compactado, também é possível indicar o número de casas decimais.|

### Tipos de dados locais

- Declarados localmente (no programa). Podem ser utilizados somente no programa em que foram declarados;
- Declaração utilizando a instrução *TYPES*.

Exemplo:

```abap
REPORT...
TYPES gty_c_type TYPE c LENGTH 8.
TYPES gty_p_type TYPE p LENGTH 3 DECIMALS 2.
```

> Dica:  Existe uma sintaxe alternativa para indicar o comprimento  com o suplemento *LENGTH*, que você encontrará frequentemente em programas mais antigos. Aqui, o comprimento é indicado entre parênteses
imediatamente após o nome da categoria. Os exemplos incluem:
```abap
TYPES gty_c_type(3) TYPE c.
TYPES gty_p_type(3) TYPE p DECIMALS 2.
```
> Para melhorar a legibilidade de seu programa, você não deve mais utilizar esta sintaxe obsoleta.

### Tipos de dados globais

- Uma categoria de dados definida no *ABAP Dictionary* denomina- se global porque pode ser utilizada em todo o sistema (ou seja, em todo o sistema da SAP em questão): 

- *Data element*, *Structure* ou *Table Type*.

![enter image description here](https://raw.githubusercontent.com/emersonleite/abap_praticas/master//fig02.png)

### Definição de objetos de dados variáveis

![enter image description here](https://raw.githubusercontent.com/emersonleite/abap_praticas/master//fig03.png)

Os objetos de dados são sempre definidos com a palavra- chave *DATA*. Você pode utilizar um ABAP do tipo padrão, local ou global para atribuir o tipo a um objeto de dados.
V ocê pode referenciar um objeto de dados já definido quando estiver definindo variáveis adicionais (suplemento *LIKE*).

![Exemplos da definição de objetos de dados elementares](https://raw.githubusercontent.com/emersonleite/abap_praticas/master//fig04.png)

- Pode-se utilizar o suplemento *VALUE* para atribuir previamente o valor de um objeto de dados elementar.

> **Dica**: 
> Na instrução *DATA*, você também tem a opção de indicar o comprimento entre parênteses, a seguir ao nome da variável, por exemplo:
```abap
DATA gv_myvar(15) TYPE c.
DATA gv_myvar_p(4) TYPE p DECIMALS 2.
```
Também aqui é recomendável que, em nome da legibilidade, você utilize o suplemento *LENGTH*.

- Caso a indicação de comprimento não exista na definição de uma variável, será utilizado um comprimento proposto para o tipo padrão (incompleto) (comprimento 1 para os tipos **C**, **N** e **X**,**** e comprimento 8 para o tipo **P**). Se a indicação de comprimento não existir de todo, utiliza- se o tipo padrão **C.** Portanto, a instrução *DATA* *gd_myvar*. sem indicação de tipo e comprimento define uma variável do tipo **C** com comprimento 1.

### Literais, constantes e símbolos de texto

![Exemplos da definição de objetos de dados elementares](https://raw.githubusercontent.com/emersonleite/abap_praticas/master//fig05.png)

- Utiliza-se litais para indicar valores fixos em programas;
-  Existem literais numéricos (indicados sem aspas) e caracteres literais (indicados com aspas). A imagem abaixo mostra alguns exemplos de literais.
- Defini-se constantes utilizando a instrução *CONSTANTS*. **Seu tipo é definido de forma similar à definição de objetos de dados elementares**. O suplemento *VALUE* é obrigatório para constantes. É assim que você define o valor das constantes.

>**Dica:**
>Se possível, evite completamente os literais ao utilizar instruções. Em vez disso, utilize constantes e símbolos de texto. Isso facilita muito a atualização de seu programa

Um princípio muito importante no desenvolvimento ABAP é o **multilinguismo**. Isso significa que, quando são exibidos textos na interface de usuário, é levado em conta o idioma de logon do usuário atual.
Para programas produtivos que devem ser executados com idiomas de logon distintos, a linguagem de programação ABAP fornece os **símbolos de texto** (*text symbols*).

![Exemplos da definição de objetos de dados elementares](https://raw.githubusercontent.com/emersonleite/abap_praticas/master//fig06.png)

Cada um dos símbolos de texto pertence a um programa específico e pode ser utilizado diretamente nele. Eles são armazenados fora do código fonte em seu próprio objeto de repositório, o **pool de texto** do programa.

Se o programa acessar um símbolo de texto ao ser executado, o sistema considerará automaticamente o idioma  de logon do usuário e fornecerá o texto nesse idioma.
Um símbolo de texto é identificado por meio de um **ID alfanumérico de três caracteres xxx** .

- Para utilização de *text symbols*, pode-se utilizar um ***TEXT-xxx*** , onde xxx representa o ID do símbolo de texto de três caracteres. 

- A seguinte sintaxe também pode-se ser utilizada: : **'...'(xxx)** . Aqui, **'...'** deve ser o texto do símbolo de texto no idioma original do programa.

Existem duas opções para definir símbolos de texto para seu programa:

- No Editor ABAP , selecione Ir para→ Elementos de texto → Símbolos de texto, ou:

- Coloca-se o símbolo de texto no código fonte, utilizando a sintaxe descrita acima, e clica duas vezes no respectivo ID. 

- Para traduzir os símbolos de texto de seu programa, selecione Ir para→Tradução no menu do Editor ABAP.

>**Dica:**
>Os elementos de texto também precisam ser ativados. 

### Comparação: Categorias de dados locais e globais

![Exemplos da definição de objetos de dados elementares](https://raw.githubusercontent.com/emersonleite/abap_praticas/master//fig07.png)

As categorias (tipos) de dados locais só podem ser utilizadas no programa em que são definidas. As categorias (tipos) de dados globais, ao contrário, podem ser utilizados em todo o sistema.
As vantagens das tipos de dados globais:

1. A usabilidade dos tipos globais em todo o sistema aumenta a consistência do sistema e sua possibilidade de reutilização reduz a quantidade de atualização necessária.

2. No ABAP Dictionary, você pode gerar uma lista de utilizações para uma categoria de dados global. As listas de utilizações lista os objetos do Repositório que utilizam o tipo ou a categoria de dados em questão.

3. Além da informação técnica, **as categorias de dados globais também podem conter informações semânticas** que correspondem às descrições empresariais dos objetos a serem definidos. **Elas também podem ser utilizadas para
projetar exibições de telas (por exemplo, a descrição breve no lado esquerdo do campo de entrada**).











> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTI5OTY4MDA3OCwxOTAzMjMwMjQ0LDE3Mz
kyODc1NDYsNzA1MzQyODk0LDkxNDQ5MjczMSwtMTg5OTM4MTE1
OSwtMTU5MjY4MDY0OSwtMTAxNzM3ODMwNyw3MTY0Mzk1MjQsNT
U1ODI5NzQ0LC0xODY1MTUyNzMyLDE5NDQxMjA0NTksLTkyMDI4
ODQ1MSwtNjcwNjc5NDczLC0xMTU5MDk2MjM0LDEwNjMxNzA0Mj
IsLTI0MDgwMTA4MCwtMjA5MzYwMzk3MiwtNTMwODYwOTM0LC0x
OTY4NDE1MzUzXX0=
-->