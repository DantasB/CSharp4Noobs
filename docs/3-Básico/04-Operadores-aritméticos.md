# 3.4 Operadores Aritméticos

Os operadores matemáticos são de importancia fundamental para qualquer tipo de linguagem de programação. Eles são os operadores de adição, subtração, multiplicação, divisão, mod (resto da divisão), incremento e decremento.

## Operador de Adição

Como o nome já diz, é um operador que realiza uma soma, ele pode ser atribuido dentro de variáveis ou realizando soma de duas variáveis, no exemplo abaixo fará mais sentido.

```csharp
using System;
					
public class Program
{
	public static void Main()
	{
        int sum = 10 + 10; //variável inteira de nome "soma" recebe o valor da soma entre 10 e 10;

        /*Aqui foi utilizada uma maneira diferente de formatar strings, utilizando o String.Format, ele funciona independente
		se estiver em um WriteLine ou não, veremos exemplos desta utilização mais abaixo. */

        Console.WriteLine(String.Format("O valor da soma 10 + 10 = {0}", sum));
	}
}
```

Note que, com o conhecimento que possuimos de variáveis, também podemos definir os valores separadamentes em variáveis distintas.

## Operador de subtração
Como o nome já diz, é um operador que realiza uma subtração, ele pode ser atribuido dentro de variáveis ou realizando subtrações de duas variáveis, no exemplo abaixo fará mais sentido.

```csharp
using System;
					
public class Program
{
	public static void Main()
	{
        int firstNumber = 10; //variavel inteira de nome "firstNumber" recebe o valor de 10.

        int secondNumber = 4; //variavel inteira de nome "secondNumber" recebe o valor de 4.

        int sub = firstNumber - secondNumber; //variavel de nome "sub" recebe o valor da subtração entre as variaveis de nome "firstNumber" e "secondNumber".

        string result = "O Resultado da subtração entre {0} e {1} será {2}";

        //Substitui o valor da variável result pela string formatada com os valores de "firstNumber", "secondNumber" e "sub" respectivamente.
        result = String.Format(result, firstNumber, secondNumber, sub);

        Console.WriteLine(result);
	}
}
```

## Operador de multiplicação
Como o nome já diz, é um operador que realiza uma multiplicação, ele pode ser atribuido dentro de variáveis ou realizando subtrações de duas variáveis, no exemplo abaixo fará mais sentido.

```csharp
using System;
					
public class Program
{
	public static void Main()
	{
        int number = 5; //variavel inteira de nome "number" recebe o valor de 5.

        int mult = 10 * number; //variável inteira de nome "mul" recebe o valor da multiplicação entre 10 e 5.

        //Note que a maioria dos tipos em c# possui o método ToString() que faz o type cast desta variável para o tipo string
        //permitindo o usuário concatenar este resultado com outra string.
        Console.WriteLine("O valor da multiplicacao 10 * 5 = " + mult.ToString());
	}
}
```

## Operador de divisão
Como o nome já diz, é um operador que realiza uma divisão, ele pode ser atribuido dentro de variáveis ou realizando subtrações de duas variáveis, no exemplo abaixo fará mais sentido.

```csharp
using System;
					
public class Program
{
	public static void Main()
	{
        int number = 5; //variavel inteira de nome "number" recebe o valor de 5.

        int division = 10 / number; //variável inteira de nome "division" recebe o valor da multiplicação entre 10 e 5;

        Console.WriteLine("O valor da divisão 10 / 5 = {0}", division);

        Console.WriteLine("O valor da divisão {0} / 2 = ", division, division/2);
	}
}
```

Para este caso específico, vamos observar como ficou o output:

```
O valor da divisão 10 / 5 = 2
O valor da divisão 2 / 2 = 
```

Note que o segundo WriteLine foi escrito errado propositalmente para atentar o leitor a um caso específico, onde há o esquecimento do ``{1}``, o C#, particularmente, não apresentará erro de compilação neste caso e irá imprimir o resultado de maneira incompleta. 
Portanto, tenha atenção com a forma que você escolhe explicitar a sua saída.


## Operador de Mod
Esse operador retorna o resto de uma divisão. O exemplo abaixo fica mais simples de entender.

```csharp
using System;
					
public class Program
{
	public static void Main()
	{
        int mod = 10 % 5; //variável inteira de nome "mod" recebe o valor do resto da divisão entre 10 e 5.

        int mod2 = num1 % num2; //variavel de nome "mod2" recebe o valor do resto da divisão entre as variaveis de nome "num1" e "num2".

        Console.WriteLine("O resto da divisão 10 / 5 = {0}", mod2);
	}
}
```

## Operações resumidas 
Se uma variável for subtrair uma variável com 1, pode-se fazer das seguintes maneiras:

```csharp
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
		x--; //subtrai somente 1 da variavel após essa linha de código.
        Console.WriteLine(x);

		x = 10;
		Console.WriteLine(x--); //Antes de ver qual o valor impresso, tente pensar um pouco sobre qual será o resultado!
		Console.WriteLine(--x);
		x = 10;		
		Console.WriteLine(--x); //Antes de ver qual o valor impresso, tente pensar um pouco sobre qual será o resultado!


		//Se uma variável for somar uma variável com 1, pode-se fazer das seguintes maneiras:
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

		//O mesmo teste do x-- e --x pode ser feito com x++ e ++x, fica como exercício para o leitor.
	}
}
```

Para este caso específico, vamos observar a saída do programa ficará da seguinte forma:

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
