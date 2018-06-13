# **Modularização - princípios básicos e síntese**

## **Técnica de modularização**

![enter image description here](https://raw.githubusercontent.com/emersonleite/abap_praticas/master/clip_image002.png)

 **Opções para utilização de unidades de modularização**

Uma **unidade de modularização** é uma parte de um programa na qual uma determinada função se encontra encapsulada. Você arquiva parte do texto fonte  em um módulo, para melhorar a transparência do programa e também para utilizar a função correspondente **várias vezes**, sem precisar implementar novamente todo o texto fonte em cada ocasião (veja o gráfico acima).

A melhoria na transparência resulta do fato de o programa se tornar mais orientado a funções: ele divide a tarefa global em subfunções, que são da responsabilidade de unidades de modularização correspondentes.

A modularização torna **mais fácil atualizar** programas, pois você apenas precisa efetuar modificações na função ou correções nas respectivas unidades de modularização, e não em diversos pontos do programa principal. Além disso, você pode processar uma chamada “como uma unidade” no depurador, enquanto executa seu programa, e depois observar o resultado. Habitualmente, isso torna mais fácil encontrar a origem do erro.

## **Modularização de programas locais**

![enter image description here](https://raw.githubusercontent.com/emersonleite/abap_praticas/master/clip_image004.png)

**Modularização de programas locais**

Existem duas técnicas para modularização de programas locais na linguagem de programação ABAP:

• **Subprogramas**, também conhecidos como **rotinas FORM**

• **Métodos em classes locais**

Com ambas as técnicas de modularização, as unidade de modularização apenas estão disponíveis no programa em que foram implementadas. Para chamar o módulo local, não pode estar carregado nenhum outro programa para o contexto do usuário no momento da execução. Classes, métodos e subprogramas locais podem ter o mesmo nome em programas distintos sem que daí resultem conflitos. Isso acontece porque o texto fonte dos programas é processado separadamente, na memória principal do servidor de aplicação.

## **Modularização global**

![enter image description here](https://raw.githubusercontent.com/emersonleite/abap_praticas/master/clip_image006.png)

**Modularização global**

Também existem duas técnicas para modularização global na linguagem de programação ABAP:

• **Módulos de função** que estão organizados em **grupos de funções**.

• **Métodos em classes globais**

**Unidades de modularização definidas globalmente** podem ser utilizadas por qualquer número de programas ao mesmo tempo. As unidade de modularização definidas globalmente são arquivadas centralmente **no repositório** e carregadas quando for necessário (em outras palavras, quando forem chamadas) para o contexto do programa de chamada.

## **Encapsulamento de dados**

![enter image description here](https://raw.githubusercontent.com/emersonleite/abap_praticas/master/clip_image008.png)

**Separação de dados**

Idealmente, as unidades de modularização que são chamadas não utilizam diretamente os objetos de dados do programa de chamada. Isso se aplica também no sentido inverso: os dados nas unidades de modularização não devem ser diretamente modificados pelo programa de chamada. Este princípio é conhecido como **encapsulamento de dados**.

O encapsulamento de dados é uma ajuda importante no desenvolvimento de texto fonte transparente e atualizável. Ele torna muito mais fácil compreender em que local do programa foram modificados conteúdos de objetos de dados. Além disso, é mais fácil garantir que os **dados** dentro das unidades de modularização sejam modificados **consistentemente** se, por exemplo, os conteúdos de vários objetos de dados dentro de uma unidade de modularização forem mutuamente dependentes.

Nós tomaremos como exemplo uma unidade de modularização em que é processada uma série de faturas. Ocorreriam consequências graves se fossem entrados números de faturas diferentes para itens de faturas que pertencessem uns aos outros. Isso é o que ocorreria se existisse acesso externo aberto a itens individuais de faturas. Seria difícil, para os responsáveis pela unidade de modularização, determinar a causa da inconsistência dos dados.

## **Transportes de dados, parâmetros e interface**

![enter image description here](https://raw.githubusercontent.com/emersonleite/abap_praticas/master/clip_image010.png)

**Transportes de dados entre o programa e a unidade de Modularização**

Os **parâmetros** são utilizados para o **intercâmbio de dados** entre o programa e o módulo. O número total de parâmetros em uma unidade de modularização denomina-se **interface** ou **assinatura**. Os parâmetros disponíveis são determinados quando você define a unidade de modularização. Os parâmetros são diferenciados com base no fato de eles serem utilizados, ou não, para transmitir dados à unidade de modularização (**parâmetros de importação**), devolver dados da unidade de modularização para o chamador (**parâmetros de exportação**), ou transmitir dados à unidade de modularização e devolver os dados após a respectiva modificação (**parâmetros de modificação)**.


> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEwNDczODUwMjNdfQ==
-->