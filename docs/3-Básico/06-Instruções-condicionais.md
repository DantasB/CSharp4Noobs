# 3.6 Instruções Condicionais

As instruções condicionais são utilizados quando é trazer lógica de maneira mais simples ao nosso código, como foi visto no capítulo anterior.

é importante frizar que, em C# existem muitas maneiras de utilizar estas instruções e, abaixo abordaremos algumas delas:

## if-else
Uma instrução if identifica qual instrução executar com base no valor de uma expressão booleana.

é possível utilizar simplesmente uma função if-else sem mais nem menos.

### Exemplo:

```csharp
using System;

public class Program
{
	public static void Main()
	{
		bool boolean = false;
		if(!boolean)
		{
			Console.WriteLine("A variável boolean é false");
		}
		else
		{
			Console.WriteLine("A variável boolean é true");
		}
	}
}
```

também é possível utilizar if's e else's aninhados.
### Exemplo:

```csharp
using System;
					
public class Program
{
	public static void Main()
	{
		int  value   = 10;
		bool boolean = true;
		if(!boolean)
		{
			Console.WriteLine("A variável boolean é false");
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
				Console.WriteLine("não sei o valor da variável value");				
			}
		}
		else
		{
			Console.WriteLine("A variável boolean é true");
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
				Console.WriteLine("não sei o valor da variável value");				
			}
		}
	}
}
```

## Informação nerd extra:
é possível escrever a instrução if-else em uma linha, utilizando o operador ``?:`` 

Este operador funciona da seguinte forma:

``<condição> ? <consequencia> : <alternativa>``

Se a condição for true, a consequencia ocorrerá. Caso contrário, a alternativa ocorrerá.

### Exemplo:

```csharp
using System;

public class Program
{
	public static void Main()
	{
		bool boolean = false;

		//Se o boolean for true, imprime true. Caso contrário imprime false.
		Console.WriteLine(boolean ? true : false);
	}
}
```

## Switch-Case:

Uma instrução Switch-Case identifica qual instrução executar com base no valor de uma expressão de qualquer tipo.

No geral o Switch-Case é utilizado como alternativa ao if-else, muitas vezes por organização de código quando há muitos casos aninhados.


### Estrutura geral de um switch-case:

- Switch(valor): A variável valor será responsável por definir qual case será acessado.
- Case 1: caso a variável valor seja igual a 1, entraremos neste case.
- Default: caso não haja nenhum case referente é variável valor, este caso será executado.

Note também que, ao final de cada case, é necessário haver ``return ou break``.


### Exemplo:

```csharp
using System;

public class Program
{
	public static void Main()
	{
		int valor = 1;

		//Valor, poderia ser de qualquer tipo, não necessariamente um inteiro.
		//No geral utilizamos para strings, inteiros e objetos criados pelo próprio usuário
		switch (valor)
		{
			case 1:
				Console.WriteLine("Caso 1");
				break;
			case 2:
				Console.WriteLine("Caso 2");
				break;
			default:
				Console.WriteLine("Caso padrão");
				return;
		}
	}
}
```