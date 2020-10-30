# 3.5 Operadores L�gicos e de Compara��o
Os operadores l�gicos s�o utilizados quando � necess�rio usar duas ou mais condi��es dentro da mesma instru��o if para que seja tomada uma �nica decis�o cujo resultado ser� verdadeiro ou falso.


| Operadores L�gicos | Significado           |
|--------------------|-----------------------|
| &&                 | and condicional       |
| !                  | not                   |
| \|\|               | or condicional        |
| &                  | and bit a bit         |
| \|                 | or bit a bit          |
| ^                  | xor bit a bit         |
| ~                  | complemento bit a bit |
| <<                 | shift para a esquerda |
| >>                 | shift para a direita  |

A diferen�a das condi��es condicionais para as bit a bit s�o as seguites:

- Condicional: S� testa o segundo lado se o primeiro lado for verdadeiro (no caso do and) ou falso (no caso do or).
- Bit a bit: Testa ambos os lados todas as vezes.


| Operadores de Compara��o | Significado           |
|--------------------------|-----------------------|
| >                        | maior que             |
| <                        | menor que             |
| >=                       | maior ou igual        |
| <=                       | menor ou igual        |
| ==                       | igual                 |
| !=                       | n�o igual (diferente) |


## Exemplos:

```
using System;

public class Program
{
	public static void Main()
	{
		int dinheiro = Console.ReadLine();

		if(dinheiro >= 100)
		{
			Console.WriteLine("Voc� acabou de adquirir um fone de ouvido novo");
		}
		else
		{
			Console.WriteLine("Voc� ainda n�o possui dinheiro para comprar este fone de ouvido");
		}
    }
}
```

Note que alguns dos comandos utilizados acima ser�o vistos posteriormente!