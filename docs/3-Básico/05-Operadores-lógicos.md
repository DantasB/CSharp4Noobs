# 3.5 Operadores lógicos e de Comparação

Os operadores lógicos são utilizados quando é necessário usar duas ou mais condições dentro da mesma instrução if para que seja tomada uma única decisão cujo resultado será verdadeiro ou falso.

| Operadores lógicos | Significado           |
| ------------------ | --------------------- |
| &&                 | and condicional       |
| !                  | not                   |
| \|\|               | or condicional        |
| &                  | and bit a bit         |
| \|                 | or bit a bit          |
| ^                  | xor bit a bit         |
| ~                  | complemento bit a bit |
| <<                 | shift para a esquerda |
| >>                 | shift para a direita  |

A diferença das condições condicionais para as bit a bit são as seguites:

-   Condicional: Só testa o segundo lado se o primeiro lado for verdadeiro (no caso do and) ou falso (no caso do or).
-   Bit a bit: Testa ambos os lados todas as vezes.

| Operadores de Comparação | Significado           |
| ------------------------ | --------------------- |
| >                        | maior que             |
| <                        | menor que             |
| >=                       | maior ou igual        |
| <=                       | menor ou igual        |
| ==                       | igual                 |
| !=                       | não igual (diferente) |

## Exemplos:

```csharp
using System;

public class Program
{
	public static void Main()
	{
		int dinheiro = Console.ReadLine();

		if(dinheiro >= 100)
		{
			Console.WriteLine("você acabou de adquirir um fone de ouvido novo");
		}
		else
		{
			Console.WriteLine("você ainda não possui dinheiro para comprar este fone de ouvido");
		}
    }
}
```

Note que alguns dos comandos utilizados acima serão vistos posteriormente!
