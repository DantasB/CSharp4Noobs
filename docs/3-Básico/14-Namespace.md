# 3.16 Namespace

Os namespaces, em C#, tendem a ser utilizados para organizar suas classes e projetos dentro de uma mesma solução.
Somente para ilustrar ao leitor, a maioria dos aplicativo do C#, começam com uma seção de `using`.
Esta seção lista todos os namespaces que o aplicativo usará com frequência, evitando que o programador repita o nome a cada vez que o método contido for utilizado.

Podemos observar melhor com o exemplo abaixo:

```cs
using System; //Neste caso fazemos uma referência ao namespace System.

public class Program
{
	private int somador(int a, int b)
	{
		return a+b;
	}

	public void Main()
	{
		Console.WriteLine(somador(10,20));
		System.Console.WriteLine(somador(10,20)); //Também é possível executar o código acima, desta forma, fazendo com que não seja necessário adicionar a diretiva using System
	}
}

```

No exemplo acima, não criamos nenhum namespace, porém, é possível fazer isso da seguinte forma:

```
namespace nome_do_namespace {
   // código
}
```

Ou seja, é possível encapsular toda a parte de soma em um namespace único e utilizar em outro código de maneira mais organizada. Como podemos observar abaixo:

```cs
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

é importante ressaltar também que a criação de namespaces, não se limitam a um só por código ou projeto. Também é possível criar namespaces `aninhados`, onde, neste caso, teremos que acessar o namespace utilizando `ponto(.)`.

Observe o exemplo abaixo:

```cs
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
