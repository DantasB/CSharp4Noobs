# 3.10 Conversão de Tipo (Typecast)

Como pudemos observar em alguns exemplos anteriores, é possível fazer a conversão de um tipo (int, string, bool) para outro tipo em C#.

Aquela maneira que vimos não é a única. Veremos abaixo outras maneiras de fazer o ``Typecast``

é importante frizar, que esta linguagem possui duas maneiras genéricas:

## [Conversão Implícita](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/language-specification/conversions#implicit-conversions)

As conversoes implicitas, como o proprio nome diz, ocorrem quando nao é explicitado (fica evidente) o tipo da conversão.

Exmplo:
```csharp
float x = 10.44f

int y = x; //Conversao implicita, onde o valor de y é a parte inteira de x, ou seja, 10
```

### Boxing
Esse tipo de conversão ocorre quando o resultado da expressão é atribuido a um tipo ``pai``, normalmente, ``object``.
```csharp
// <= C# 8
Pessoa p = new Pessoa();
// >= C# 9
Pessoa p = new();

object obj = p; //Boxing
```

Como o proprio nome já diz, é feito um ``empacotamento`` do objeto, e como todos os tipos derivam de ``object``, logo, eu posso converter implicitamente ``Pessoa`` para ``object``.

A mesma coisa vale se ``Pessoa`` fosse uma derivação ``Mamifero``, entao:
```csharp
//declaraçao da classe pessoa
class Pessoas : Mamifero {}

//..

Pessoa p = new Pessoa();
Mamifero m = p;
```

Mas não se preocupe, que esses detalhes seram abordados nos conceitos de Orientaçao a Objetos.

Note que não é possível fazer a conversão implícita para todos os tipos. Vamos observar um pouco melhor abaixo:

```
//Ordem de containerização:
De sbyte -> short, int, long, float, double, decimal.
De byte -> short, ushort, int, uint, long, ulong, float, double, decimal.
De short -> int, long, float, double, decimal.
De ushort -> int, uint, long, ulong, float, double, decimal.
De int -> long, float, double, decimal.
De uint -> long, ulong, float, double, decimal.
De long -> float, double, decimal.
De ulong -> float, double, decimal.
De char -> ushort, int, uint, long, ulong, float, double, decimal.
De float -> double.
```

### Implicit Operator <img alt="Badge em breve" src="https://img.shields.io/badge/-EM%20BREVE-purple">

## [Conversão Explícita](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/language-specification/conversions#explicit-conversions)

Sao todas as implícitas, e outras conversoes onde ficam explicitados os tipos da conversão.

### Expressao Cast (T)x
Essa expressao tenta conversão dado objeto em determinado tipo, e caso essa conversão nao seja possível, uma exception será disparada, veja:
```csharp
using System;
					
public class Program
{
	public static void Main()
	{
		var x = "10";
		
		object y = x;
		int i = 0;
		
		try
		{
			i = (int)y; //Unboxing
		}
		catch 
		{
			Console.WriteLine("deu ruim");
		}
		
		Console.WriteLine($"i = {i}");
	}
}

//Saida:
// deu ruim
// i = 0
``` 

Alterando o valor de x para 10, temos:
```csharp
var x = 10;

//Saida:
// i = 10
```

### Operador AS
Este operador faz o mesmo papel da expressão cast, com uma diferença de nunca disparar exception.

Sintaxe:
```csharp
var resultado = obj as T
```

Sendo ``obj`` qualquer tipo que permita ser nulo e ``T`` o tipo do objeto que tentará ser convertido (também deve adimitir ser nulo).

Caso a conversão nao seja possivel, o valor retornado será nulo, veja o exemplo anterior com o ``as``:
```csharp
using System;
					
public class Program
{
	public static void Main()
	{
		var x = "10";
		
		object y = x;
		int? i = null;
		
		i = y as int?; //Unboxing
		
		Console.WriteLine($"i = {i}");
	}
}

//Saida:
// i =
```

Alterando o valor de x para 10, temos:
```csharp
var x = 10;

//Saida:
// i = 10
```

### Explicit Operator <img alt="Badge em breve" src="https://img.shields.io/badge/-EM%20BREVE-purple">
