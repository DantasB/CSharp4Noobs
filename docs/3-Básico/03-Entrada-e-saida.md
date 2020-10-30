# 3.3 Entrada e Saída

Para você observar alguns resultados em C# ou receber entradas de usuários, precisamos utilizar funções padrões (Console.WriteLine() e Console.ReadLine()).
Lembrando que, é necessário incluir a biblioteca no início do programa ``using System`` para que estas funções possam ser utilizadas.

## Console.WriteLine()

A função ``Console.WriteLine()`` exibe um ou mais dados na tela. Dependendo do número de parámetros passados, separados por vírgula.

Esta função, diferente de algumas linguagens, pode imprimir qualquer tipo, ou até mesmo ser chamada sem parámetro nenhum, imprimindo assim uma linha vazia.

### Exemplos:

```csharp
using System;

public class Program
{
	public static void Main()
	{
		//Define uma variável string de nome aSerImpresso, com o valor ``vez.``.
		string aSerImpresso = "vez.";

		Console.WriteLine("Estou");
		Console.WriteLine();
		Console.WriteLine("imprimindo");
		Console.WriteLine("isso!");
		Console.WriteLine(1);
		Console.WriteLine(aSerImpresso);
	}
}
```

Depois de compilado, o resultado será:

```
Estou

Imprimindo
isso!
1
vez.
```

Além disso, é possível formatar valores dentro da string, passando assim multiplos parámetros.

```csharp
using System;

public class Program
{
	public static void Main()
	{
		//define uma variável do tipo string de nome multiplicacao e atribui o valor "X".
		string multiplicacao = "X";

		//define uma variável do tipo int de nome valor e atribui o valor 4.
		int    valor         = 4;

		Console.WriteLine("{0} {1} {0} = {2}", valor, multiplicacao, valor*valor);
	}
}
```

Depois de compilado, o resultado será:

```
4 X 4 = 16
```

## Console.ReadLine()

A função ``Console.ReadLine()`` para a execução do programa até o usuário escrever um argumento e retorna uma string com o que foi inputado.


### Exemplo:

```csharp
using System;

public class Program
{
	public static void Main()
	{
		Console.WriteLine("Qual o seu Nome?");

		string aSerImpresso = Console.ReadLine();

		Console.WriteLine("Olá, {0}. Seja bem-vindo ao curso de CSharp.", aSerImpresso);
	}
}

```

Depois de compilado, considerando que o usuário entrou o seu nome, o resultado será:

```
Qual o seu Nome?
Olá, Bruno. Seja bem-vindo ao curso de CSharp.
```


Existem também outros métodos menos utilizados. Não abordaremos neste curso, porém é interessante lerem a respeito:

Função		      | O que faz
-------------     | -------------
Console.Read()    | Lá somente 1 char e retorna um ``int`` com o valor ASCII deste Char.
Console.ReadKey() | Lá a tecla digitada pelo usuário e retorna um ``ConsoleKeyInfo`` que é um objeto, cujo parámetro ``.key``, é o nome desta tecla.
Console.Write()   | Uma outra forma de executar o WriteLine, porém com algumas peculiaridades.
