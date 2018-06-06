# Arquitetura de sistema e programa ABAP

- O SAP NetWeaver Application Server possui arquitetura modular;
- Segue o princípio cliente/servidor **orientado a software**;
- Possiblidade escalabilidade do sistema;
- O nível mais baixo éo nível do banco de dados. Aqui, os dados são administrados com a ajuda de um sistema de administração de banco de dados relacional (SADBR). Esses dados incluem, além de dados de aplicação, os programas e os metadados de que sistema da SAP necessita para auto- administração.
- Os programas ABAP são executados no **nível do servidor de aplicação**, que leem o banco de dados.
- O terceiro nível é o **nível do servidor de apresentação**, que contém a interface com o usuário.

```abap

*&---------------------------------------------------------------------*
*& Report zsplit
*&---------------------------------------------------------------------*
*&
*&
*& PRÁTICA DA FUNÇÃO SPLIT PARA STRING - EMERSON LEITE.
*&
*&
*&---------------------------------------------------------------------*
REPORT zsplit.

parameters: numero type string,
            tam type i.             "TAMANHO DA STRING FATIADA

data: numero1 like numero,
      numero2 like numero,
      numero3 like numero,
      numero4 like numero,
      numero5 like numero.

numero1 = numero+0(tam). "+0 é o off-set a partir do primeiro
numero2 = numero+1(tam). "elemento e (tam) é o tamanho da string.
numero3 = numero+2(tam).
numero4 = numero+3(tam).

numero5 = numero1 * numero2. "MULTIPLICANDO O NUMERO 1 E 2 DA STRING.

write: numero1, numero2, numero3, numero4, numero5.

```