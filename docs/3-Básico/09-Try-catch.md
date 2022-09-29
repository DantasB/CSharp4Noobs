# 3.9 Try-Catch

A instrução Try-Catch consiste em um bloco `try` seguido de um ou mais blocos `catch` onde tem como objetivo capturar as exceções e, no geral, imprimir uma mensagem para o usuário.

Toda exceção lançada pelo sistema, procura por um bloco catch. Caso não haja, exibirá uma mensagem de exceção sem tratamento para o usuário e interromperá a execução do programa.

Esta instrução possui a seguinte estrutura:

- Try: Tenta fazer a execução de um programa.
- Catch: Caso tenha algum erro na função try, ele entra nesse trecho de código.
- Throw: Caso algum caso seja alcançado, ele dispara uma exceção, que virá a ser tratada pelo Catch.

## Exemplos:

```cs
using System;

public class Program
{

	public static void Main()
	{
		int n = 0;
		try
		{
			//Imprime 0.
			Console.WriteLine(n);
		}
		catch
		{
			//Neste caso não teremos uma exceção.
			Console.WriteLine("Um erro foi detectado");
		}
	}
}
```

```cs
using System;

public class Program
{
	//Como foi definido na aula de modificadores, uma função sem modificadores private ou public é necessariamente private
	static void ProcessaString(string s)
	{
		if (s == null)
		{
			//lança uma exceção (Argumento é nulo).
			throw new ArgumentNullException();
		}
	}

	public static void Main()
	{
		string s = null;
		try
		{
			//Processa uma string null.
			ProcessaString(s);
		}
		catch(Exception ex)
		{
			//Neste caso vamos imprimir "Um erro foi detectado" pois o valor passado irá disparará uma exceção.
			Console.WriteLine("Um erro foi detectado");
		}
	}
}
```

### Finaly

Alem dos blocos try e catch, tambem existe o bloco `finally`, que deve acompanhar um try-catch, a ideia do bloco finally é rodar uma instrução depois do try-catch, geralmente é utilizado quando se é necessário fazer algo na aplicação independente se o sistema gerou uma exceção ou não.

## Exemplo:

```cs
using System;

public class Program
{
	public static void Main()
	{
	try 
	{ 
		//lança uma exceção (Argumento é nulo).
		throw new ArgumentNullException();
	} 
	catch
	{
		//lança outra exceção (Argumento é nulo)
		throw new ArgumentNullException();
	}
	finally
	{ 
		//essa mensagem é executada após o catch
		Console.WriteLine("Mensagem Finally"); 
        }
	//Essa mensagem não é executada, uma exceção dentro do catch fez o sistema ser interrompido
	Console.WriteLine("Teste depois try");
    }
}
```
