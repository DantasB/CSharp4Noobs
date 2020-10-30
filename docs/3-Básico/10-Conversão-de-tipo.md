# 3.10 Convers�o de Tipo (Typecast)

Como pudemos observar em alguns exemplos anteriores, � poss�vel fazer a convers�o de um tipo (int, string, bool) para outro tipo em C#.

Aquela maneira que vimos n�o � a �nica. Veremos abaixo outras maneiras de fazer o ``Typecast``

� importante frizar, que esta linguagem possui duas maneiras gen�ricas:

## Convers�o Impl�cita

Este tipo de convers�o, permite que o usu�rio converta o tipo de vari�vel somente passando um ``(novo tipo)`` antes desta vari�vel ou n�o
Veremos melhor abaixo:

### Exemplo:

```
using System;

public class Program
{
	public static void Main()
	{
		double valor = 10;


		//Nesta linha abaixo teriamos um erro, pois n�o � poss�vel converter o tipo float para double implicitamente.
		//float resultado = valor; 

		float resultado = (float)valor; //Enquanto esta linha � poss�vel ser feita a convers�o implicita

		valor = resultado; //Esta linha tamb�m n�o dar� erro. Veremos melhor abaixo.
	}
}
```

Note que n�o � poss�vel fazer a convers�o impl�cita para todos os tipos. Vamos observar um pouco melhor abaixo:

```
//Ordem de containeriza��o:

byte > short > char > int > long > float > double

//Byte cont�m todos.
//Double n�o cont�m nenhum tipo.
```

Basicamente, esta sequencia diz que o todos os tipos s�o ``conteinerizados`` pelo tipo ``byte``, logo todo tipo pode ser convertido para byte, sem a adi��o do ``(tipo)`` antes da declara��o da vari�vel.

Contudo, n�o � poss�vel converter, por exemplo, o tipo double para float sem a adi��o do ``(tipo)``, pois, pelo fato do float conter o double, essa convers�o implicita n�o existe.

Logo, devemos ter cuidado com esse tipo de convers�o, a fim de evitar erros com a precis�o das nossas vari�veis.

## Convers�o Expl�cita 

Diferente do tipo de convers�o anterior, este m�todo consiste em chamar uma fun��o ``Parse`` ou ``To"Tipo"`` para fazer a convers�o da vari�vel em quest�o.

Abaixo veremos alguns exemplos, contudo, n�o � necess�rio voc� gravar todos estes m�todos, muitos deles ser�o "gravados" com o tempo.

Fun��o			   | O que faz
-------------	   | -------------
Convert.ToBoolean  | Converte qualquer n�mero para true (exceto char ou string) e retorna false para 0.
Convert.ToByte     | Converte um tipo para um Byte.
Convert.ToChar     | Converte um tipo para um Char.
Convert.ToDateTime | Converte um tipo para um DateTime (Estrutura que representa Data).
Convert.ToDecimal  | Converte um tipo para um Decimal.
Convert.ToDouble   | Converte um tipo para um Double.
Convert.ToInt16    | Converte um tipo para um Int16.
Convert.ToInt32    | Converte um tipo para um Int32.
Convert.ToInt64    | Converte um tipo para um Int64.
Convert.ToSByte    | Converte um tipo para um Byte com sinal.
Convert.ToSingle   | Converte um tipo para um Small float.
Convert.ToString   | Converte um tipo para um String.
Convert.ToUInt16   | Converte um tipo para um Int sem sinal.
Convert.ToUInt32   | Converte um tipo para um Long sem sinal.
Convert.ToUInt64   | Converte um tipo para um Big int sem sinal.
float.Parse		   | Converte um string para um Float.
.ToString		   | Converte um tipo para um String.


### Exemplo:

```
using System;

public class Program
{
	public static void Main()
	{
		double valor = 10.2;

		float resultado = float.Parse(Convert.ToString(valor)); //Enquanto esta linha � poss�vel ser feita a convers�o implicita

		valor = resultado; //Esta linha tamb�m n�o dar� erro. Veremos melhor abaixo.

		Console.WriteLine(resultado);
		Console.WriteLine(valor);

		Convert.ToString(resultado);
		
		Console.WriteLine("Este � o resultado: " + resultado + ". ");
		
	}
}
```

Onde a sa�da neste caso ser�:

```
10.2
10.1999998092651
Este � o resultado: 10.2.
```

Note que, ao converter o float para um tipo double, a precis�o varia, logo, devemos ter cuidado com o ``Type Cast`` e prestar aten��o nos tipos das nossas vari�veis.
