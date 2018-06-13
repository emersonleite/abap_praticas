# **Como trabalhar com o** **_ABAP Debugger_**

![enter image description here](https://raw.githubusercontent.com/emersonleite/abap_praticas/master//clip_image002.png)

**Execute um programa no modo de depuração**

Existem várias opções para iniciar um programa no modo de depuração, a partir do _Object Navigator_:

a) Na área de navegação do programa em questão, selecione o menu de contexto _Executar → Depuração_.

b) Na área do editor, selecione a linha do programa em questão, a partir da qual você quer efetuar a depuração. Selecione o botão _Definir/eliminar ponto de parada_. Depois, inicie o programa selecionando _F8_ ou, na área de navegação, por meio do menu de contexto _Executar → Direto_. (A configuração de um ponto de parada no editor, descrita acima, só é possível para textos fonte ativos.)

![enter image description here](https://raw.githubusercontent.com/emersonleite/abap_praticas/master//clip_image004.png)

**Como alternar para modo de depuração no momento da**

**execução**

Se você quiser “depurar” **determinada função de um programa**, inicie primeiro o programa sem o Debugger e, em seguida, alterne para o modo de depuração imediatamente antes de executar a função (ex. botão). Há duas maneiras de fazer isso:

a) Selecione _Sistema → Utilitários → Depuração do ABAP (ou tela)_.

b) Insira **/h** no campo de comandos da barra de ferramentas e pressione **Enter**.

![enter image description here](https://raw.githubusercontent.com/emersonleite/abap_praticas/master//clip_image006.png)

**ABAP Debugger: Etapa individual e conteúdo do campo**

No Debugger, você pode selecionar processamento em _uma etapa_ para executar o programa uma instrução por vez. Além disso, pode exibir objetos de dados e o respectivo conteúdo na exibição da variável. Basta inserir aí o nome do objeto de dados ou copiá-los com um clique duplo nos objetos de dados correspondentes no texto fonte.

Apenas o depurador clássico está disponível com o _SAP Web Application Server_ 6.40 e anteriores. Com releases posteriores, você pode utilizar o depurador novo e o clássico. Você pode alternar facilmente do novo para o ABAP Debugger clássico durante a depuração, selecionando _Depurador → Mudar para ABAP Debugger clássico_ no menu.

No depurador clássico, você pode exibir o conteúdo de até oito objetos de dados. Para isso, proceda como faria com o novo depurador.

![enter image description here](https://raw.githubusercontent.com/emersonleite/abap_praticas/master//clip_image008.png)

**ABAP Debugger: pontos de parada**

No novo depurador, você pode definir um **ponto de parada** com um único clique antes da linha do texto fonte (no depurador clássico, você utiliza um clique duplo para isso). Você também pode definir um ponto de parada para instruções ABAP específicas: _Pontos de parada → Ponto de parada em → Instrução_. Se você selecionar _Avançar_, o programa será executado até ao próximo ponto de parada.

Os pontos de parada definidos apenas são válidos para a sessão atual do depurador. Contudo, se você selecionar _Gravar_, os pontos de parada permanecerão inalterados durante toda sua sessão SAP.

![enter image description here](https://raw.githubusercontent.com/emersonleite/abap_praticas/master//clip_image010.png)

**ABAP Debugger: rastreamento de modificações de dados**

Os **watchpoints** são pontos de parada dependentes do conteúdo do campo. Se você definir um watchpoint **sem indicar um operador relacional/valor de comparação** em um campo e selecionar _Avançar_, o programa será executado até que o conteúdo do campo seja modificado. Pelo contrário, se você **tiver indicado o operador relacional e o valor de comparação** então, logo que você selecione _Avançar_, o programa será executado até que a condição indicada seja atendida. No depurador clássico, você pode definir, no máximo, 10 watchpoints. Contudo, você pode ligá-los tal como no novo depurador, utilizando um operador lógico (AND ou OR).

![enter image description here](https://raw.githubusercontent.com/emersonleite/abap_praticas/master//clip_image012.png)

**ABAP Debugger: modificação do conteúdo do campo**

Se você quiser modificar o conteúdo de um campo durante a depuração, faça um clique duplo no ícone do lápis, na exibição de variável. O valor estará então pronto para entrada. Agora, modifique o valor do campo e confirme a alteração selecionando **ENTER**. O valor será modificado durante a execução do depurador. No depurador clássico, você pode modificar o conteúdo diretamente na visão de campo. Basta clicar no ícone do lápis para aceitar o valor modificado.

![enter image description here](https://raw.githubusercontent.com/emersonleite/abap_praticas/master//clip_image014.png)

**Funções adicionais do novo depurador**

Foram adicionadas várias funções úteis ao novo depurador (contudo, a maioria foi incorporada pela primeira vez com o release 7.0 do _SAP NetWeaver_). No _Object Navigator_, você pode determinar o depurador que quer utilizar como padrão, selecionando _Utilitários → Configurações → Editor ABAP → Depurador_.
<!--stackedit_data:
eyJoaXN0b3J5IjpbNTQ3NjczNjEwXX0=
-->