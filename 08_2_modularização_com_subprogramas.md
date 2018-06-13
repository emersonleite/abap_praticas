# Modularização com subprogramas

## Modularização de programas internos com subprogramas

fig26

** Exemplo simples de um subprograma**

Um subprograma é uma unidade de modularização dentro de um programa.
Para o interpretador ABAP, ele faz sempre parte do programa principal. No exemplo acima não se utilizam parâmetros, o que torna muito simples estruturar a chamada do subprograma. Normalmente, um subprograma utiliza valores de objetos de dados e também devolve valores. O gráfico a seguir demonstra como essas variáveis podem ser utilizadas no subprograma.

## Definição de parâmetros para subprogramas

fig27

**Transferência de parâmetros – Visibilidade de variáveis globais**

Caso tenham sido definidas variáveis no programa principal, elas serão globalmente visíveis dentro do programa e poderão ser modificadas em qualquer local do programa inteiro. Isso significa que os subprogramas definidos dentro do programa principal também podem modificá- las.

fig28

**Transferência de parâmetros – Definição de uma interface**

Você pode abordar todas as variáveis ( globais) definidas no programa principal, a partir de um subprograma. Contudo, para chamar um subprograma com objetos de dados diferentes para cada situação, você não deve utilizar variáveis globais no subprograma, mas caracteres de preenchimento. Eles são substituídos pelas variáveis globais necessárias quando se chama o subprograma. Esses caracteres de preenchimento chamam- se parâmetros formais e, juntos, formam a interface do subprograma.V ocê precisa declarar a interface no momento em que define o subprograma.
Quando se chama o subprograma, é necessário especializar parâmetros formais por meio de variáveis globais correspondentes ( parâmetros r eais), para referenciar o processamento do subprograma para variáveis reais. Essa atribuição de parâmetros reais a parâmetros formais quando se chama um subprograma é conhecida como transferência de parâmetros.

fig29

**Formas de transferir parâmetros de interface**

A forma pela qual essas variáveis do programa principal são transferidas para os parâmetros formais do subprograma chama- se tipo de transferência eé indicado para cada parâmetro da interface do subprograma.

**Existem três tipos de transferências para subprogramas:**

**chamada por valor**

**É efetuada uma cópia do parâmetro real. Essa cópia é atribuída ao parâmetro formal. Portanto, qualquer atribuição de valor ao parâmetro formal correspondente no subprograma refere- se apenas à cópia do parâmetro real e não ao original**. Utilize esse tipo de transferência para disponibilizar o valor de uma variável global para o subprograma (sob a forma de uma cópia de variável), sem possibilitar a modificação da respectiva variável global (protegendo o original). Contudo, leve em conta que, a criação de cópias, especialmente para tabelas internas extensas, pode ser demorada.


**chamada por valore resultado**

A este tipo de transferência aplica- se o mesmo que à “chamada por valor”. Contudo, no fim regular do subprograma, o valor modificado até o momento na cópia é regravado no original. Caso o programa seja prematuramente terminado por uma instrução STOP ou por uma mensagem de usuário de tipo E, a regravação do valor será suprimida.
Utilize esse tipo de transferência para transferir o valor de uma variável global para o subprograma e para regravar o valor final totalmente processado da cópia no original. Contudo, observe que pode ser demorado criar cópias e regravar valores, especialmente para tabelas internas extensas.

**chamada por referência**

O parâmetro real é atribuído **diretamente** ao parâmetro formal. Isso significa que atribuições de valores ao parâmetro formal são executadas **diretamente no parâmetro real**.
Utilize esse tipo de transferência se quiser executar um subprograma diretamente no parâmetro real indicado. É uma forma útil de evitar a demorada criação de cópias para tabelas internas extensas.

fig30

**Definição e chamada de subprogramas**


**Estrutura de um subprograma**

**- Um subprograma é introduzido com FORM.**
- Você especifica o nome ea interface do subprograma depois de FORM.
- Seguem- se depois as instruções do subprograma.
- A instrução ENDFORM conclui o subprograma.

Na definição da interface, você lista os parâmetros formais do subprograma (aqui: _f1, f2, f3_) e, se necessário, digite- os. O tipo de transferência necessário precisa ser indicado para cada parâmetro:





