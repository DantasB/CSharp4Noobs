# 3.5 Entrada e Sa�da

Para voc� observar alguns resultados em C# ou receber entradas de usu�rios, precisamos utilizar fun��es padr�es (Console.WriteLine() e Console.ReadLine())
Lembrando que, � necess�rio utilizar no in�cio do programa : using System para que essas fun��es possam ser utilizadas.

## Console.WriteLine()

A fun��o ``Console.WriteLine()`` exibe um ou mais dados na tela. Dependendo do n�mero de par�metros passados, separados por v�rgula.

Esta fun��o, diferente de algumas linguagens, pode imprimir qualquer tipo, ou at� mesmo ser chamada sem par�metro nenhum, imprimindo assim uma linha vazia.

### Exemplos:

```
   //Define uma vari�vel string de nome aSerImpresso, com o valor ``vez.``
   string aSerImpresso = "vez.";

   Console.WriteLine("Estou");
   Console.WriteLine();
   Console.WriteLine("imprimindo");
   Console.WriteLine("isso!");
   Console.WriteLine(1);
   Console.WriteLine(aSerImpresso);
```

Depois de compilado, o resultado ser�:

```
	Estou

	Imprimindo
	isso!
	1
	vez.
```

Al�m disso, � poss�vel formatar valores dentro da string, passando assim multiplos par�metros.

### Exemplos:

```
   string multiplicacao = "X";
   int    valor         = 4;

   Console.WriteLine("{0} {1} {0} = {2}", valor, multiplicacao, valor*valor);
```

Depois de compilado, o resultado ser�:

```
	4 X 4 = 16
```

## Console.ReadLine()

A fun��o ``Console.ReadLine()`` para a execu��o do programa at� o usu�rio escrever um argumento e retorna uma string com o que foi inputado.


### Exemplos:

```
   Console.WriteLine("Qual o seu Nome?");

   string aSerImpresso = Console.ReadLine();

   Console.WriteLine("Ol�, {0}. Seja bem-vindo ao curso de CSharp.", aSerImpresso);
```

Depois de compilado, considerando que o usu�rio entrou o seu nome, o resultado ser�:

```
	Qual o seu Nome?
	Ol�, Bruno. Seja bem-vindo ao curso de CSharp.
```