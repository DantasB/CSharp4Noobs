# 3.6 Instru��es Condicionais

As instru��es condicionais s�o utilizados quando � trazer l�gica de maneira mais simples ao nosso c�digo, como foi visto no cap�tulo anterior.

� importante frizar que, em C# existem muitas maneiras de utilizar estas instru��es e, abaixo abordaremos algumas delas:

## if-else
Uma instru��o if identifica qual instru��o executar com base no valor de uma express�o booleana.

� poss�vel utilizar simplesmente uma fun��o if-else sem mais nem menos.

### Exemplo:

```
using System;

public class Program
{
	public static void Main()
	{
		bool boolean = false;
		if(!boolean)
		{
			Console.WriteLine("A vari�vel boolean � false");
		}
		else
		{
			Console.WriteLine("A vari�vel boolean � true");
		}
	}
}
```

Tamb�m � poss�vel utilizar if's e else's aninhados.
### Exemplo:

```
using System;
					
public class Program
{
	public static void Main()
	{
		int  value   = 10;
		bool boolean = true;
		if(!boolean)
		{
			Console.WriteLine("A vari�vel boolean � false");
			if(value-- == 11)
			{
				Console.WriteLine("value = 11");
			}
			else if(value == 10)
			{
				Console.WriteLine("value = 10");
			}
			else if(value == 9)
			{
				Console.WriteLine("value = 9");
			}
			else
			{
				Console.WriteLine("N�o sei o valor da vari�vel value");				
			}
		}
		else
		{
			Console.WriteLine("A vari�vel boolean � true");
			if(value++ == 11)
			{
				Console.WriteLine("value = 11");
			}
			else if(value == 10)
			{
				Console.WriteLine("value = 10");
			}
			else if(value == 9)
			{
				Console.WriteLine("value = 9");
			}
			else
			{
				Console.WriteLine("N�o sei o valor da vari�vel value");				
			}
		}
	}
}
```

## Informa��o nerd extra:
� poss�vel escrever a instru��o if-else em uma linha, utilizando o operador ``?:`` 

Este operador funciona da seguinte forma:

``<condi��o> ? <consequ�ncia> : <alternativa>``

Se a condi��o for true, a consequ�ncia ocorrer�. Caso contr�rio, a alternativa ocorrer�.

### Exemplo:

```
using System;

public class Program
{
	public static void Main()
	{
		bool boolean = false;

		//Se o boolean for true, imprime true. Caso contr�rio imprime false.
		Console.WriteLine(boolean ? true : false);
	}
}
```

## Switch-Case:

Uma instru��o Switch-Case identifica qual instru��o executar com base no valor de uma express�o de qualquer tipo.

No geral o Switch-Case � utilizado como alternativa ao if-else, muitas vezes por organiza��o de c�digo quando h� muitos casos aninhados.


### Estrutura geral de um switch-case:

- Switch(valor): A vari�vel valor ser� respons�vel por definir qual case ser� acessado.
- Case 1: caso a vari�vel valor seja igual a 1, entraremos neste case.
- Default: caso n�o haja nenhum case referente � vari�vel valor, este caso ser� executado.

Note tamb�m que, ao final de cada case, � necess�rio haver ``return ou break``.


### Exemplo:

```
using System;

public class Program
{
	public static void Main()
	{
		int valor = 1;

		//Valor, poderia ser de qualquer tipo, n�o necessariamente um inteiro.
		//No geral utilizamos para strings, inteiros e objetos criados pelo pr�prio usu�rio
		switch (valor)
		{
			case 1:
				Console.WriteLine("Caso 1");
				break;
			case 2:
				Console.WriteLine("Caso 2");
				break;
			default:
				Console.WriteLine("Caso padr�o");
				return;
		}
	}
}
```