- Dois tipos de pontos de parada: internos e externos. 

- Pontos de parada dentro do debugger precisam ser salvos para continuarem externamente. 

- Editando variáveis com o lápis.

- Usar tela desktop 3 de preferência no debugger.

- F5 - passo a passo.
- F6 - pula as funções, por exemplo. 
- F8 - vai para o final, direto.

- transação **/hx** para fechar o debugger. 

- Iniciar debug na tela de seleção - **/h**.

- Quando o debbug entrar numa tela padrão, que não é a do programa, entrar com F7. 

- Aba Globais - variáveis do programa. 

- >>>>>> aponta o local do dump. 

- Transação **st22** para a procura de dumps.

- Duplo clique para verificar o dump. Dentro da st22. 

- Modificar valor padrão com default:z\7t5

```abap
PARAMETERS: P_NAME   TYPE STRING default 'emerson'
```

ZRTR_EBL_EXE03

Programa	R3TR	PROG	ZRTR_EBL_EXE03
Transação	R3TR	TRAN	Z_EXE03_EBL

- form/ perform. 

- O que se decalra dentro, abaixo do Start of selection é variável local. 

- Criar grupo de funções - após criar, clicar com o direito e ativar. 

- Criar função:

- Transação para modificar e criar funções - SE37

- Valor proposto -> Valor default

- Importação -> dados de entrada. 

- Tabelas -> Obsoleto

- Modific. -> Changing.

- Exportação -> Dados de retorno. 

- INCLUDES posso chamar em qualquer programa. 

- INCLUDE TOP - SOMENTE PARA DECLARAÇÃO DE VARIÁVEIS GLOBAIS, VISIVEL EM TODO GRUPO DE FUNÇÃO. 

- Testar função com F8. 