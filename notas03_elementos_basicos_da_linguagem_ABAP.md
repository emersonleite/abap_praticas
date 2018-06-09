# Tipos de dados e objetos de dados 

Uma descrição formal de uma variável é uma categoria de dados **(data type)**. Inversamente, uma variável ou uma constante definida concretamente por meio de uma tipo de dados é um objeto de dados **(data object)**.

Pode-se usar tipos de dados nas situações a seguir:

1. *Definição de objetos de dados*:
A categoria de um objeto de dados define suas propriedades técnicas (e, possivelmente, também semânticas).

2. *Definição de parâmetros da interface:*
O tipo de um parâmetro da interface determina o tipo do próprio parâmetro que é transferido quando se chama a unidade de modularização.

3. *Definição de campos de entrada/saída:*
O tipo de um campo de entrada/saída pode fornecer outras informações além das características técnicas, como a ajuda de campo e de entrada de valores.

## Tipos de dados padrão em ABAP  (*standard data types*)

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

**Os objetos de dados são sempre definidos com a palavra- chave *DATA***. Você pode utilizar um ABAP do tipo padrão, local ou global para atribuir o tipo a um objeto de dados.
V ocê pode referenciar um objeto de dados já definido quando estiver definindo variáveis adicionais (suplemento *LIKE*).

![Exemplos da definição de objetos de dados elementares](https://raw.githubusercontent.com/emersonleite/abap_praticas/master//fig04.png)

- Pode-se utilizar o suplemento *VALUE* para atribuir previamente o valor de um objeto de dados elementar.

> **Dica**: 
> Na instrução *DATA*, você também tem a opção de indicar o comprimento entre parênteses, a seguir ao nome da variável, por exemplo:
```abap
DATA gv_myvar(15) TYPE c.
DATA gv_myvar_p(4) TYPE p DECIMALS 2.
```
Também aqui é recomendável que, em nome da legibilidade, você utilize o suplemento *LENGTH*. Essa sintaxe está obsoleta. 

- **Caso a indicação de comprimento não exista na definição de uma variável, será utilizado um comprimento proposto para o tipo padrão** (incompleto) (comprimento 1 para os tipos **C**, **N** e **X**, e comprimento 8 para o tipo **P**). Se a indicação de comprimento não existir de todo, utiliza- se o tipo padrão **C.** **Portanto, a instrução *DATA* *gd_myvar***, sem indicação de tipo e comprimento **define uma variável do tipo C** com comprimento 1.

### Literais, constantes e símbolos de texto

![Exemplos da definição de objetos de dados elementares](https://raw.githubusercontent.com/emersonleite/abap_praticas/master//fig05.png)

- Utiliza-se literais para indicar valores fixos em programas;
-  Existem literais numéricos (indicados sem aspas) e caracteres literais (indicados com aspas). A imagem abaixo mostra alguns exemplos de literais.
- Defini-se constantes utilizando a instrução *CONSTANTS*. **Seu tipo é definido de forma similar à definição de objetos de dados elementares**. O suplemento ***VALUE*** é obrigatório para constantes. É assim que você define o valor das constantes.

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

As categorias de dados locais apenas devem ser utilizadas exclusivamente no programa onde são definidas e se a informação semântica não for importante para a definição dos objetos de dados correspondentes.

# Usando instruções básicas em ABAP

## Atribuições de valor

Quando o programa é iniciado, o contexto do programa é carregado na área de memória do servidor de aplicação eé disponibilizada memória para os objetos de dados definidos no programa. A todos os objetos de dados elementares é previamente atribuído um valor inicial específico de tipo, exceto se tiver sido definido um valor diferente por meio do suplemento *VALUE.*


![Exemplos da definição de objetos de dados elementares](https://raw.githubusercontent.com/emersonleite/abap_praticas/master//fig08.png)

Pode-se utilizar *MOVE* para transferir o conteúdo de um objeto de dados para outro objeto. As duas variantes abaixo tem o mesmo resultado.

```abap
MOVE gv_var1 TO gv_var2.
gv_var2 = gv_var1.
```
Se ambos os objetos de dados *gv_var1* e *gv_var2* tiverem tipos diferentes, então existe um **conflito de tipos**. Nesse caso, será automaticamente executada uma **conversão de tipo**, caso exista uma regra de conversão.

A instrução *ADD* adiciona o valor especificado à variável:

```abap
ADD 1 TO gv_counter.
```
A instrução *CLEAR* redefine o conteúdo de um objeto de dados ao valor inicial **relacionado ao tipo**.

#### Cálculos e expressões aritméticas

![Exemplos da definição de objetos de dados elementares](https://raw.githubusercontent.com/emersonleite/abap_praticas/master//fig09.png)
 
 Em ABAP pode-se programar expressões aritméticas. As operações válidas são as seguintes:
    **+** --> Adição
    **-** --> Subtração
      * --> Multiplicação
    **/**  --> Divisão
 ** --> Exponenciação
**DIV**        - Divisão de número inteiro sem resto
**MOD**     - Resto após divisão de número inteiro

> **ATENÇÃO:** Parênteses e operadores são palavras- chave ABAP e, portanto, precisam ser separados das outras palavras por, pelo menos, um espaço.

A instrução *STRLEN* a seguir fornece o comprimento de uma *string*. 
```abap
gv_length = STRLEN( gv_cityfrom ).
```
- A sequência de operações segue regras algébricas, sendo que as expressões entre parênteses têm prioridade, depois vêm as funções, depois as potências, seguidas pela multiplicação/divisão e, finalmente, a adição/subtração.

- Para funções, o parênteses de abertura faz parte do nome da função (não há espaço entre o nome da função e o primeiro parenteses).
Novamente, o resto precisa ser separado por, pelo menos, um espaço.

 #### Condicionais e expressões lógicas

- Em ABAP, existem duas maneiras de executar diferentes sequências de instruções, dependendo de certas condições.

1. Na construção ***IF***, você pode definir qualquer expressão lógica;
 Se a condição do ***IF*** não for cumprida, será verificada a condição indicada na ramificação ***ELSEIF*** seguinte (podem existir várias
ramificações). Se nenhum aida assim não for cumprida, será executada a ramificação ***ELSE*** - caso exista. As ramificações ***ELSEIF*** e ***ELSE*** são opcionais.

2. Pode-se utilizar a instrução ***CASE*** para se distinguir claramente os casos. Nesse caso, O conteúdo do campo indicado na parte ***CASE*** é comparado com os objetos de dados listados nas ramificações ***WHEN***, para ver se eles coincidem. e. Se nenhuma comparação tiver êxito, o sistema executará a ramificação ***OTHERS***, se existir. Exceto no caso da primeira ramificação ***WHEN***, todos os outros suplementos são opcionais.

> **Dica:**: 
> Para implementar verificações de semelhança entre um campo e diferentes valores, use a construção ***CASE*** em vez de ***IF,*** já que ela é mais transparente e tem melhor performance.

- Abaixo alguns exemplos de uso da instrução ***IF***.

![Exemplos de uso da instrução IF](https://github.com/emersonleite/abap_praticas/blob/master/fig10.png?raw=true)

```abap
IF 	gv_var > 0.
* Instruções.
ELSEIF gv_var = 0.
*--> Instruções
ELSE.
*--> Instruções
ENDIF.
```
```abap
CASE gv_carrid.
	WHEN 'AA'.
	*--> Instruções
	WHEN 'LH'.
	*--> Instruções
	WHEN OTHERS.
	*--> Instruções
ENDCASE.	
```
- As negações são normalmente formuladas colocando o operador **NOT** antes da expressão lógica. Quando utilizar negações na consulta ***IS INITIAL***, você pode utilizar a consulta especial ***IS NOT INITIAL***.

- As estruturas devem ser devidamente fechadas com ***ENDIF*** ou ***ENDCASE***, a depender do caso.

- Com a utilização de ***AND*** ou ***OR*** para ligação entre sentenças, utiliza-se parenteses.  

 #### *Loops*
 
 - Existem quatro tipos de *loops*.
 
 - O campo de sistema ***SY-INDEX***, contém o *loops* atual para *loops* ***DO*** e ***WHILE***.

1. *Loop* ***DO - ENDDO*** - controlado por índice:
-- Executado continumante até que seja calcelado com ***EXIT***. Pode-se indicar o número de *loops* que se quer. 

2. *Loop* ***WHILE-ENDWHILE*** - controlado por cabeçalho:
-- Executado até que a condição indicada não seja mais cumprida. Essa condição é sempre verificada antes da execução do bloco.

3. *Loops* de leitura:
-- ***SELECT*** para ler entradas de uma tabela de banco de dados;
-- ***LOOP AT*** para tabelas internas.

#### Campos de s


 












<!--stackedit_data:
eyJoaXN0b3J5IjpbLTExNDMyNzAzOTRdfQ==
-->