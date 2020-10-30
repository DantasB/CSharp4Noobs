# 3.9 Try-Catch

A Instru��o Try-Catch consiste em um bloco ``try`` seguido de um ou mais blocos ``catch`` onde tem como objetivo capturar as exce��es e, no geral, imprimir uma mensagem para o usu�rio.

Toda exce��o lan�ada pelo sistema, procura por um bloco catch. Caso n�o haja, exibir� uma mensagem de exce��o sem tratamento para o usu�rio e interromper� a execu��o do programa.

Esta instru��o possui a seguinte estrutura:

- Try: Tenta fazer a execu��o de um programa.
- Catch: Caso tenha algum erro na fun��o try, ele entra nesse trecho de c�digo.
- Throw: Caso algum caso seja alcan�ado, ele "arreme�a" uma exce��o, que vir� a ser tratada pelo Catch.

## Exemplos:

```
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
			//Neste caso n�o teremos uma exce��o.
			Console.WriteLine("Um erro foi detectado");
		}
	}	
}
```

```
using System;

public class Program
{
	//Como foi definido na aula de modificadores, uma fun��o sem modificadores private ou public � necessariamente private
	static void ProcessaString(string s)
	{
		if (s == null)
		{
			//Arreme�a uma exce��o (Argumento � nulo).
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
			//Neste caso vamos imprimir "Um erro foi detectado" pois o valor passado ir� arreme�ar uma exce��o.
			Console.WriteLine("Um erro foi detectado");
		}
	}	
}
```