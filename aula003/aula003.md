Derivação de um Código a partir da Gramática do PHP

1. Linguagem escolhida

A linguagem escolhida foi o PHP.

A fonte consultada foi a documentação oficial do PHP: Manual do PHP.

A gramática será apresentada de forma simplificada, utilizando uma notação semelhante à BNF/EBNF.

2. Produções utilizadas

Para representar um pequeno programa, foram selecionadas estas regras:

<programa> ::= "<?php" <comando> "?>"

<comando> ::= <variavel> "=" <expressao> ";"

<variavel> ::= "$" <identificador>

<identificador> ::= "x"

<expressao> ::= <numero> "+" <numero>

<numero> ::= "5" | "3"


Os elementos entre < > são símbolos não terminais. Eles representam partes da estrutura do programa.

Os elementos entre aspas são símbolos terminais, pois aparecem diretamente no código final.

3. Código escolhido

O código que será gerado é:

<?php
$x = 5 + 3;
?>


Esse exemplo foi escolhido por ser simples e apresentar uma variável, uma atribuição e uma expressão matemática.

4. Derivação

A derivação começa pelo símbolo inicial <programa>:

<programa>
⇒ "<?php" <comando> "?>"

⇒ "<?php" <variavel> "=" <expressao> ";" "?>"

⇒ "<?php" "$" <identificador> "=" <expressao> ";" "?>"

⇒ "<?php" "$" "x" "=" <expressao> ";" "?>"

⇒ "<?php" "$" "x" "=" <numero> "+" <numero> ";" "?>"

⇒ "<?php" "$" "x" "=" "5" "+" <numero> ";" "?>"

⇒ "<?php" "$" "x" "=" "5" "+" "3" ";" "?>"


Assim, a sequência final é:

<?php
$x = 5 + 3;
?>

5. Conclusão

A derivação demonstra como uma gramática pode ser usada para construir um programa válido.

Partimos do símbolo inicial <programa> e, aplicando as regras de produção, substituímos os símbolos não terminais até obter somente símbolos terminais, formando o código PHP.

Dessa forma, é possível perceber, na prática, a relação entre:

Gramática formal
Símbolos terminais
Símbolos não terminais
Regras de produção
Linguagens de programação

A partir desse processo, fica evidente como uma sequência de regras formais pode descrever a estrutura e a formação de um programa em uma linguagem de programação.