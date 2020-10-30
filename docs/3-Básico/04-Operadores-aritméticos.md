# 3.4 Operadores Aritm�ticos

Os operadores matem�ticos s�o de import�ncia fundamental para qualquer tipo de linguagem de programa��o. Eles s�o os operadores de adi��o, subtra��o, multiplica��o, divis�o, mod (resto da divis�o), incremento e decremento.

## Operador de Adi��o

Como o nome j� diz, � um operador que realiza uma soma, ele pode ser atribuido dentro de vari�veis ou realizando soma de duas vari�veis, no exemplo abaixo far� mais sentido.

```
using System;
					
public class Program
{
	public static void Main()
	{
        int sum = 10 + 10; //vari�vel inteira de nome "soma" recebe o valor da soma entre 10 e 10;

        /*Aqui foi utilizada uma maneira diferente de formatar strings, utilizando o String.Format, ele funciona independente
		se estiver em um WriteLine ou n�o, veremos exemplos desta utiliza��o mais abaixo. */

        Console.WriteLine(String.Format("O valor da soma 10 + 10 = {0}", sum));
	}
}
```

Note que, com o conhecimento que possuimos de vari�veis, tamb�m podemos definir os valores separadamentes em vari�veis distintas.

## Operador de subtra��o
Como o nome j� diz, � um operador que realiza uma subtra��o, ele pode ser atribuido dentro de vari�veis ou realizando subtra��es de duas vari�veis, no exemplo abaixo far� mais sentido.

```
using System;
					
public class Program
{
	public static void Main()
	{
        int firstNumber = 10; //variavel inteira de nome "firstNumber" recebe o valor de 10.

        int secondNumber = 4; //variavel inteira de nome "secondNumber" recebe o valor de 4.

        int sub = firstNumber - secondNumber; //variavel de nome "sub" recebe o valor da subtra��o entre as variaveis de nome "firstNumber" e "secondNumber".

        string result = "O Resultado da subtra��o entre {0} e {1} ser� {2}";

        //Substitui o valor da vari�vel result pela string formatada com os valores de "firstNumber", "secondNumber" e "sub" respectivamente.
        result = String.Format(result, firstNumber, secondNumber, sub);

        Console.WriteLine(result);
	}
}
```

## Operador de multiplica��o
Como o nome j� diz, � um operador que realiza uma multiplica��o, ele pode ser atribuido dentro de vari�veis ou realizando subtra��es de duas vari�veis, no exemplo abaixo far� mais sentido.

```
using System;
					
public class Program
{
	public static void Main()
	{
        int number = 5; //variavel inteira de nome "number" recebe o valor de 5.

        int mult = 10 * number; //vari�vel inteira de nome "mul" recebe o valor da multiplica��o entre 10 e 5.

        //Note que a maioria dos tipos em c# possui o m�todo ToString() que faz o type cast desta vari�vel para o tipo string
        //permitindo o usu�rio concatenar este resultado com outra string.
        Console.WriteLine("O valor da multiplicacao 10 * 5 = " + mult.ToString());
	}
}
```

## Operador de divis�o
Como o nome j� diz, � um operador que realiza uma divis�o, ele pode ser atribuido dentro de vari�veis ou realizando subtra��es de duas vari�veis, no exemplo abaixo far� mais sentido.

```
using System;
					
public class Program
{
	public static void Main()
	{
        int number = 5; //variavel inteira de nome "number" recebe o valor de 5.

        int division = 10 / number; //vari�vel inteira de nome "division" recebe o valor da multiplica��o entre 10 e 5;

        Console.WriteLine("O valor da divis�o 10 / 5 = {0}", division);

        Console.WriteLine("O valor da divis�o {0} / 2 = ", division, division/2);
	}
}
```

Para este caso espec�fico, vamos observar como ficou o output:

```
O valor da divis�o 10 / 5 = 2
O valor da divis�o 2 / 2 = 
```

Note que o segundo WriteLine foi escrito errado propositalmente para atentar o leitor a um caso espec�fico, onde h� o esquecimento do ``{1}``, o C#, particularmente, n�o apresentar� erro de compila��o neste caso e ir� imprimir o resultado de maneira incompleta. 
Portanto, tenha aten��o com a forma que voc� escolhe explicitar a sua sa�da.


## Operador de Mod
Esse operador retorna o resto de uma divis�o. O exemplo abaixo fica mais simples de entender.

```
using System;
					
public class Program
{
	public static void Main()
	{
        int mod = 10 % 5; //vari�vel inteira de nome "mod" recebe o valor do resto da divis�o entre 10 e 5.

        int mod2 = num1 % num2; //variavel de nome "mod2" recebe o valor do resto da divis�o entre as variaveis de nome "num1" e "num2".

        Console.WriteLine("O resto da divis�o 10 / 5 = {0}", mod2);
	}
}
```

## Opera��es resumidas 
Se uma vari�vel for subtrair uma vari�vel com 1, pode-se fazer das seguintes maneiras:

```
using System;
					
public class Program
{
	public static void Main()
	{
		int x = 10;
        Console.WriteLine(x);

		x = 10;
		x = x - 1; //funciona com qualquer valor, nao somente 1.
        Console.WriteLine(x);

		x = 10;
		x -= 1; //funciona com qualquer valor nao somente 1.
        Console.WriteLine(x);

		x = 10;
		x--; //subtrai somente 1 da variavel ap�s essa linha de c�digo.
        Console.WriteLine(x);

		x = 10;
		Console.WriteLine(x--); //Antes de ver qual o valor impresso, tente pensar um pouco sobre qual ser� o resultado!
		Console.WriteLine(--x);
		x = 10;		
		Console.WriteLine(--x); //Antes de ver qual o valor impresso, tente pensar um pouco sobre qual ser� o resultado!


		//Se uma vari�vel for somar uma vari�vel com 1, pode-se fazer das seguintes maneiras:
		x = 10;
        Console.WriteLine(x);

		x = 10;
		x = x + 1; //funciona com qualquer valor, nao somente 1.
        Console.WriteLine(x);

		x = 10;
		x += 1; //funciona com qualquer valor nao somente 1.
        Console.WriteLine(x);

		x = 10;
		x++; //soma somente 1 da variavel.
        Console.WriteLine(x);

		//O mesmo teste do x-- e --x pode ser feito com x++ e ++x, fica como exerc�cio para o leitor.
	}
}
```

Para este caso espec�fico, vamos observar a sa�da do programa ficar� da seguinte forma:

```
10
9
9
9
10
8
9
10
11
11
11
```
