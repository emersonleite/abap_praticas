# Usando instruções básicas em ABAP

## Atribuições de valor

Quando o programa é iniciado, o contexto do programa é carregado na área de memória do servidor de aplicação e é disponibilizada memória para os objetos de dados definidos no programa. A todos os objetos de dados elementares é previamente atribuído um valor inicial específico de tipo, exceto se tiver sido definido um valor diferente por meio do suplemento *VALUE.*


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

#### Campos de sistema
- Não precisam ser declarados com antecedência.

- Exemplos abaixo:

![Campos de sistema](https://github.com/emersonleite/abap_praticas/blob/master/fig11.png?raw=true)

-  Dos campos do sistema mais importantes é o campo ***sy- subrc***. Ele serve para indicar se a instrução pode ou não ser executada com êxito. O valor **0 (zero)** significa que a instrução foi executada com êxito.

![Aplicação do sy-subrc](https://github.com/emersonleite/abap_praticas/blob/master/fig13.png?raw=true)
 
 #### Mensagens interativas

- Utiliza-se a instrução ***MESSAGE***;

- Indicar o numero da mensagem (3 dígitos) e a classe da mensagem;

- Indicar o tipo da mensagem, com letra antes dos três dígitos.

- Utilizar o suplemento ***WITH*** se houver valores a indicar. Esse valores aparecerão no corpo da mensagem.

- Exemplo abaixo:
![Mensagens interativas](https://github.com/emersonleite/abap_praticas/blob/master/fig12.png?raw=true)

