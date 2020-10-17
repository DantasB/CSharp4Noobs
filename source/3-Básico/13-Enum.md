# 3.13 Enum

Uma enumeração é um conjunto de inteiros constantes nomeados. Um tipo ``enumerate`` é declarado quando utilizamos ``enum``

A estrutura básica de um enum em c# é da seguinte forma:

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
        Console.WriteLine("Sábado: {0}", fimDaSemana);
		
	}
}
```

A saída deste código será:

```
Domingo: 0
Sábado: 6
```

