# 3.10 Funções

A criação de uma função é necessária por conta da modularidade do código, ou seja, é possível fazer com que haja nenhuma repetição de código desnecessária, e também é possível fazer com que outras partes do programa utilizem uma mesma função.
Deste modo, tornamos o código mais limpo e mais fácil de ser entendido.

Para construir uma função, é importante conhecermos a estrutura básica desta, onde podemos olhar abaixo:

``<modificador> <tipo-de-retorno> <nome-do-metodo> <lista-de-parâmetros>``

As funções, diferentes de outras linguagens C, não precisa ser definida necessariamente antes da função main (porém nada te limita a construir antes).


## Exemplo:

```
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

O resultado impresso neste caso será ``30``.


Note, neste caso, que a Main não está mais com o modificador ``static`` porém, não teria problema algum de utilizar este modificador, contudo que adicionassemos este modificador a nova função criada, como podemos observar abaixo:

```
using System;

public class Program
{
	private static int somador(int a, int b)
	{
		return a+b;
	}
	
	public static void Main()
	{
		Console.WriteLine(somador(10,20));
	}	
}
```

O resultado impresso neste caso também será ``30``.