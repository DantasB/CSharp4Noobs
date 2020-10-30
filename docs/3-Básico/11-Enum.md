# 3.11 Enum

Uma enumera��o � um conjunto de inteiros constantes nomeados. Um tipo ``enumerate`` � declarado quando utilizamos ``enum``

A estrutura b�sica de um enum em c# � da seguinte forma:

```csharp
enum <nome do enum> {
   Valor_1,
   Valor_2,
   Valor_3,
   ...,
};
```

Cada Valor, pode ser visto na verdade como um inteiro, logo, se fizermos:  ``(int)Valor_1`` Obteremos o inteiro 0. Observaremos isso melhor abaixo:

```csharp
using System;

public class Program
{
	enum Dias { 
		Dom,
		Seg,
		Ter,
		Qua,
		Qui,
		Sex,
		Sab 
	};

	public static void Main()
	{
		int comecoDaSemana = (int)Dias.Dom;
		int fimDaSemana    = (int)Dias.Sab;
         
        Console.WriteLine("Domingo: {0}", comecoDaSemana);
        Console.WriteLine("S�bado: {0}", fimDaSemana);
		
	}
}
```

A sa�da deste c�digo ser�:

```
Domingo: 0
S�bado: 6
```

Uma observa��o interessante, � que, para evitar poss�veis problemas de ordem do enum, � poss�vel atribuir valores aos enums.

Podemos observar melhor abaixo:

```csharp
enum Dias { 
	Dom = 0,
	Seg = 1,
	Ter = 2,
	Qui = 4,
	Qua = 3,
	Sex = 5,
	Sab = 6 
};
```

Notem que mesmo invertendo a ordem de Quinta com Quarta, como os valores foram definidos na ordem correta, n�o teremos problemas na l�gica.