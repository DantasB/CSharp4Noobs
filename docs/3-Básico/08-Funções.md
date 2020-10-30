# 3.8 Fun��es

A cria��o de uma fun��o � necess�ria por conta da modularidade do c�digo, ou seja, � poss�vel fazer com que haja nenhuma repeti��o de c�digo desnecess�ria, e tamb�m � poss�vel fazer com que outras partes do programa utilizem uma mesma fun��o.
Deste modo, tornamos o c�digo mais limpo e mais f�cil de ser entendido.

Para construir uma fun��o, � importante conhecermos a estrutura b�sica desta, onde podemos olhar abaixo:

``<modificador> <tipo-de-retorno> <nome-do-metodo> <lista-de-par�metros>``

As fun��es, diferentes de outras linguagens C, n�o precisa ser definida necessariamente antes da fun��o main (por�m nada te limita a construir antes).


## Exemplo:

```csharp
using System;

public class Program
{
	private int somador(int a, int b)
	{
		return a+b;
	}
	
	public void Main()
	{
		Console.WriteLine(somador(10,20));
	}	
}
```

O resultado impresso neste caso ser� ``30``.


Note, neste caso, que a Main n�o est� mais com o modificador ``static`` por�m, n�o teria problema algum de utilizar este modificador, contudo que adicionassemos este modificador a nova fun��o criada, como podemos observar abaixo:

```csharp
using System;

public class Program
{
	private static int somador(int a, int b) => a + b;
	
	public static void Main()
	{
		Console.WriteLine(somador(10,20));
	}	
}
```

O resultado impresso neste caso tamb�m ser� ``30``.