# 3.13 Enum

Uma enumera��o � um conjunto de inteiros constantes nomeados. Um tipo ``enumerate`` � declarado quando utilizamos ``enum``

A estrutura b�sica de um enum em c# � da seguinte forma:

```
enum <nome do enum> {
   Valor_1,
   Valor_2,
   Valor_3,
   ...,
};
```

Cada Valor, pode ser visto na verdade como um inteiro, logo, se fizermos:  ``(int)Valor_1`` Obteremos o inteiro 0. Observaremos isso melhor abaixo:

```
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

