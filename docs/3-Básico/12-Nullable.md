# 3.12 Tipos de valores anulaveis

C# disponiliza para nós um tipo especial de estrutura de dados chamado de ``nullable``, onde você pode designar um um limite padrão do seu tipo além de um valor ``nulo`` adicional
Por exemplo, uma variável ``nullable`` do tipo ``bool``, poderia assumir 3 resultados possíveis: ``true``, ``false`` ou ``null``.

Para utilizar este tipo utilizamos da seguinte estrutura:

```
<Tipo da estrutura de dados> ? <Nome da variável> = null;
```

Porque utilizar esta estrutura ?

Normalmente, em alguns programas, é possível que a gente obtenha um comportamento indefinido de variáveis.
Por exemplo o tipo booleano. É esperado que o resultado dele seja true ou false. Contudo, em alguns casos, é possível que este valor seja indefinido ou ausente. Por isso optamos pelo nullable.

### Exemplo

```csharp
using System;

public class Program
{
	public static void Main()
	{
         int? num1 = null;
         int? num2 = 45;
         
         double? num3 = new double?();
         double? num4 = 3.14157;
         
         bool? boolVal = new bool?();

         Console.WriteLine("Resultado das variáveis acima: {0}, {1}, {2}, {3}", num1, num2, num3, num4);
         Console.WriteLine("Valor padrão de uma variável nullable: {0}", boolVal);
	}
}
```

Após compilado a saída será:

```
Resultado das variáveis acima: , 45, , 3.14157
Valor padrão de uma variável nullable:

```

## Operador de coalescência nula

O operador de coalescência nula ``??`` retornará o valor do operando esquerdo se não for ``null``.Caso contrário, ele avaliará o operando direito e retornará seu resultado.
Este operador não avaliará o operando do lado direito se o operando esquerdo for diferente de ``null``.

### Exemplo

```csharp
using System;

public class Program
{
	public static void Main()
	{
         double? num1 = null;
         double? num2 = 3.14157;
         double num3;
         
         num3 = num1 ?? 5.34;      
         Console.WriteLine("Valor de num3: {0}", num3);
         
         num3 = num2 ?? 5.34;
         Console.WriteLine("Valor de num3: {0}", num3);
	}
}
```

Após compilado a saída será:

```
Valor de num3: 5.34
Valor de num3: 3.14157
```