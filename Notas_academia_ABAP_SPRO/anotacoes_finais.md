scarr

sflight

CRIAR UM PROGRAMA EXE06

As declarações globais em uma include TOP
A tela em uma include F01

Programa básico - o processamento todo. 

PARAMETROS DE ENTRADA: DENOMINAÇÃO BREVE DA COMPANHIA AÉREA, DATA DO VÔO (SLECTION_OPTIONS)

Saída:
Denominação breve da companhia aérea (scarr)
Nome de uma companhia aérea (scarr)
URL de uma companhia aérea (scarr)
Data do vôo (sflight)
Total de marcações existentes (sflight)




se11
Categoria de dados -> estrutura
Não precisa do campo mandante 

sUPLEMENTOS 
cATEGRIA DE AMPLIAÇÃO -> AMPLIÁVEL COMO PRETENDIDO


se11
Tipo de tabela 
Categoria da linha com o nome do tipo de estrutura


******************************************************

se11
gerar atualização de tabela
colocar nome da tabela
modific
Utilitários -> gerador de atualização de tabelas

Antes tem que criar um grupo de funções.


*********************************************************************

19/07

Perfumaria no alv. 

Select single - copiar do código do Ewerlon

Range

*********************************************************************

Se quiser pesquisar

SELECT MAX
SELECT MIN
SELECT AVG

SELECT UP TO 1 rows.

*********************************************************************

**Seleciona Apenas 1 dado de uma unica coluna
*    DATA: v_nome_da_cia TYPE scarr-carrname.
*    SELECT SINGLE carrname
*      FROM scarr
*      INTO v_nome_da_cia
*      WHERE carrid = 'AA'.
*
**Selecionar uma unica linha com N colunas.
*    DATA: w_scarr TYPE scarr.
*    SELECT SINGLE *
*      FROM scarr
*      INTO w_scarr
*      WHERE carrid = 'AA'.
*
**Saber apenas se o registro existe com a minha condição.
*    DATA: l_count TYPE i.
*    SELECT COUNT(*)
*      FROM scarr
*      WHERE carrid = 'AA'.
*    IF sy-subrc IS INITIAL. "se for = 0, existe registros.
*
*    ELSE. "nao existe registro.
*
*    ENDIF.

*SELECT MAX
*SELECT MIN
*SELECT AVG
*SELECT UP TO 1 rows.


*********************************************************************

RANGE DE CAMPOS:

código abaixo:

DATA: 	r_empresa TYPE RANGE OF ZTB_EJB_EMPRESA-BUKRS,
	W_Empresa linke line of r_empresa.

wr_empresa-sign = 'I'.
wr_empresa-option = 'BT'.
wr_empresa-low = '1000'.
wr_empresa-high = '1000'.
Append wr_empresa to r_empresa.
clear wr_empresa.

exemplo de utilização

if p_bukrs in r_empresa. " Verifica se um valor está no range.
	Condição.

*********************************************************************

Descrevendo quantidade de linhas de uma tabela interna:

    DATA: l_linhas TYPE i.
    DESCRIBE TABLE t_ztb_ejb_empresa LINES l_linhas.

    "l_linhas vai ter a quantidade de registros na tabela interna.

*********************************************************************

se16n

zrtr_ebl_prova_02
ZGFTR_EBL_PROVA_02









 


