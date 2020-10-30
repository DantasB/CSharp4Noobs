# 3.16 Namespace

Os namespaces, em C#, tendem a ser utilizados para organizar suas classes e projetos dentro de uma mesma solu��o. 
Somente para ilustrar ao leitor, a maioria dos aplicativo do C#, come�am com uma se��o de ``using``.
Esta se��o lista todos os namespaces que o aplicativo usar� com frequ�ncia, evitando que o programador repita o nome a cada vez que o m�todo contido for utilizado.

Podemos observar melhor com o exemplo abaixo:

```csharp
using System; //Neste caso fazemos uma refer�ncia ao namespace System.

public class Program
{
	private int somador(int a, int b)
	{
		return a+b;
	}
	
	public void Main()
	{
		Console.WriteLine(somador(10,20));
		System.Console.WriteLine(somador(10,20)); //Tamb�m � poss�vel executar o c�digo acima, desta forma, fazendo com que n�o seja necess�rio adicionar a diretiva using System
	}	
}

```

No exemplo acima, n�o criamos nenhum namespace, por�m, � poss�vel fazer isso da seguinte forma:

```
namespace nome_do_namespace {
   // c�digo
}
```

Ou seja, � poss�vel encapsular toda a parte de soma em um namespace �nico e utilizar em outro c�digo de maneira mais organizada. Como podemos observar abaixo:

```csharp
using System;
using Calculadora;

namespace Calculadora
{
	public class FuncoesBasicas
	{
		public static int Somador(int a, int b)
		{
			return a+b;
		}
	}
}

public class Program
{
	public void Main()
	{
		Console.WriteLine(FuncoesBasicas.Somador(10,20));
	}	
}

```

� importante ressaltar tamb�m que a cria��o de namespaces, n�o se limitam a um s� por c�digo ou projeto. Tamb�m � poss�vel criar namespaces ``aninhados``, onde, neste caso, teremos que acessar o namespace utilizando ``ponto(.)``.

Observe o exemplo abaixo:

```csharp
using System;
using Projeto.Calculadora; //Acessa o namespace Calculadora que se encontra dentro do projeto.
using Projeto.DiasDaSemana; //Acessa o namespace DiasDaSemana que se encontra dentro do projeto.

namespace Projeto
{
	//Namespace dentro do namespace Projeto.
	namespace Calculadora
	{
		public class FuncoesBasicas
		{
			public static int Somador(int a, int b)
			{
				return a+b;
			}
		}
	}
	//Namespace dentro do namespace Projeto.
	namespace DiasDaSemana
	{
		public enum Dias { 
			Dom,
			Seg,
			Ter,
			Qua,
			Qui,
			Sex,
			Sab 
		};
	}
}

public class Program
{
	public void Main()
	{
		Console.WriteLine(FuncoesBasicas.Somador(10,20));
		Console.WriteLine(Dias.Sab);
	}	
}
```