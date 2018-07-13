# Temas abordados

- Transação;

- Três camadas: apresentação, aplicação e banco de dados;

- Fluxo de chamadas ABAP:
	1. Dispatcher;
	2. Work Process;
	
- Navegação.

##- Teclas de atalho 

- /N - cancela a transação atual. Volta para tela inicial do sap. 
- /Nxxxx - deixa/ sai da transação atual e abre a transação xxx.
- /O - gerar ou eliminar uma tela do SAPGUI
- /Oxxxx - Abrir uma nova tela do SAPGUI chamando a transação xxxx.
- /NEND - finalizar a sessão atual com uma mensagem de confirmação.
- /Nex - finalizar a sessão atual sem uma mensagem de confirmação.
- /i - eliminar a janela atual.


## - Introdução ao ABAP Workbench

- Transação SE80.

- Para busca utilizar o caracter coringa asterisco. Dar F4 abre procura com z*, por exemplo. Isso no campo de procura da SE80.

- Criação de pacote;

## Requests

- Request - 2 tipos. Customizing e request de workbench.
 - Destino -  para onde a request vai.
 
 - SE09 - transação para criar request e para procurar requests.
 
 - Request modificável - para o caso em que haja algo a ser feito ainda. 
 
 - Liberada - Não é possível mexer nos programas sem que se associe a outra request nova. 
 
  - Request de cópias para evitar de ficar criando requests. 

## Programas

 - Todo programa tem um um padrão de nome. Depende do módulo.
 
 - Para vizualizar o help dar F1 no comando, daí aparece ajuda.
 
  - Comando - utilitários->versões->Administração de versões. Dá para verificar as requests associadas ao programa e situação das mesmas. 
 
 - Programa inativo não pode ser transportado. 
 
 - Primeiro deve se liberar as tarefas, para depois poder se liberar a request. 
 
 - Se uma request for liberada, só é possível modificar o programa criando uma nova request. 
 
 - Criação de requests de cópia.
 
 - Transação STMS - gerenciamento de transportes
 
 
 
 






