# Debugger 

- Existem dois tipos de pontos de parada: internos e externos. 

- Pontos de parada podem ser definidos dentro do debugger, ma s precisam ser salvos para continuarem externamente. 

- É possível se editar valores de variáveis clicando no ícone de lápis, para verificar o comportamento do programa.

- Utilizar, de preferência a tela 'Desktop 3' no debugger.

- Nas abas possível se vizualizar variáveis locais e globais, além daquelas em que se deu duplo clique. 

- **Para estapas no debugger:** 
- F5 - passo a passo.
- F6 - pula as funções, por exemplo. 
- F7 - retorna.
- F8 - vai para o final, direto.

- transação **/hx** para fechar o debugger. 

- Iniciar debug na tela de seleção - **/h**.

- Quando o debbuger entrar numa outra tela padrão, que não é a do programa que está sendo analisado, entrar com F7 até voltar para o progrma em análise.

- >>>>>>> aponta o local do dump. 

- Transação **st22** para a procura de dumps.

- Duplo clique para verificar o dump. Dentro da st22. 

- Modificar valor padrão com default:

```abap
PARAMETERS: P_NAME   TYPE STRING default 'emerson'
```

## form/ perform. 

- O que se declara dentro, abaixo do Start of selection é variável local. Informação corrigida depois pelo instrutor. A variável é global. 

## Criar grupo de funções:
- Através da transação SE80;
- Após criar, clicar com o direito e ativar. 

## Criar função:

- Transação para modificar e criar funções - SE37;

- Na coluna Valor proposto pode se colocar valores padrão (default);

- Na coluna Importação são colocados dados de entrada da função;

- A coluna Tabelas está obsoleta-> Obsoleto

- Coluna Modific. corresponde a campos que serão modificados.

- A coluna Exportação corresponde a dados de retorno. 

- Os programas do tipo INCLUDES podem ser chamados em qualquer programa. 

- O INCLUDE TOP é utilizado somente para declaração de variáveis globais. Essas variáveis são visíveis em todo o grupo de função. 

- Para testar a função recém criada pode-se se utilizar o comando F8. 