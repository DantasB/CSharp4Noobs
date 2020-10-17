# Conversão de Tipo (Typecast)

Como pudemos observar em alguns exemplos anteriores, é possível fazer a conversão de um tipo (int, string, bool) para outro tipo em C#.

Aquela maneira que vimos não é a única. Veremos abaixo outras maneiras de fazer o ``Typecast``

É importante frizar, que esta linguagem possui duas maneiras genêricas:

## Conversão Implícita

Este tipo de conversão, permite que o usuário converta o tipo de variável somente passando um ``(novo tipo)`` antes desta variável ou não
Veremos melhor abaixo:

### Exemplo:

```
using System;

public class Program
{
	public static void Main()
	{
		double valor = 10;


		//Nesta linha abaixo teremos um erro, pois não é possível converter o tipo float para double implicitamente.
		//float resultado = valor; 

		float resultado = (float)valor; //Enquanto esta linha é possível ser feita a conversão implicita

		valor = resultado; //Esta linha também não dará erro. Veremos melhor abaixo.
	}
}
```

Note que não é possível fazer a conversão implícita para todos os tipos. Vamos observar um pouco melhor abaixo:

```
//Ordem de containerização:

byte > short > char > int > long > float > double

//Byte contém todos.
//Double não contém nenhum tipo.
```

Basicamente, esta sequencia diz que o todos os tipos são ``conteinerizados`` pelo tipo ``byte``, logo todo tipo pode ser convertido para byte, sem a adição do ``(tipo)`` antes da declaração da variável.

Contudo, não é possível converter, por exemplo, o tipo double para float sem a adição do ``(tipo)``, pois, pelo fato do float conter o double, essa conversão implicita não existe.

Logo, devemos ter cuidado com esse tipo de conversão, a fim de evitar erros com a precisão das nossas variáveis.

## Conversão Explícita 

Diferente do tipo de conversão anterior, este método consiste em chamar uma função ``Parse`` ou ``To"Tipo"`` para fazer a conversão da variável em questão.

Abaixo veremos alguns exemplos, contudo, não é necessário você gravar todos estes métodos, muitos deles serão "gravados" com o tempo.

Função			   | O que faz
-------------	   | -------------
Convert.ToBoolean  | Converte qualquer número para true (exceto char ou string) e retorna false para 0.
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
float.Parse		   | Converte um tipo para um Float.
.ToString		   | Converte um tipo para um String.