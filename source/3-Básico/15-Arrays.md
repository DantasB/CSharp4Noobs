# 3.15 Arrays

Um array, armazena uma cole��o de elementos de mesmo tipo, de forma sequencial em um tamanho fixo.

Esta estrutura de dados � utilizada para armazenar uma cole��o de dados, contudo, as vezes � mais comum pensar em um array como uma cole��o de vari�veis do mesmo tipo, armazenado em um espa�o de mem�ria cont�guo.

Em vez de declarar vari�veis de maneira individual, ``num0, num1, ...,`numn`` n�s declaramos um array de nome ``num`` e n�s podemos acessar os n�meros indexando de ``0 at� n``, para representar vari�veis individuais. 

Todos os arrays consistem em espa�os de mem�ria cont�guos. O menor endere�o corresponde ao primeiro elemento e o maior endere�o corresponde ao ultimo elemento.

Uma estrutura geral de um array � dada da seguinte forma:

```
<type>[] <arrayName>;
```

� importante ressaltar que um array, � utilizado para definir matrizes (unidimensionais, multidimensionais e etc).

Outra ressalva importante � que, ao instanciar um array, o compilador do C# implicitamente inicializa cada elemento do array para um valor ``default`` dependendo do tipo do array. Como por exemplo o caso de um ``int[]`` todos os elementos s�o inicializados em 0.

Abaixo veremos alguns exemplos de como instanciar um array.

### Exemplo

```
using System;

public class Program
{
	public static void Main()
	{
		//Define um array1 de tamanho 5. Onde os �ndices est�o definidos de 0 � 4.
		int[] array1 = new int[5];

		// Declara um array2 de tamanho 5. Onde os elementos j� est�o pr� inseridos.
        int[] array2 = new int[] { 1, 3, 5, 7, 9 };

		// Sintaxe alternativa para definir um array.
        int[] array3 = { 1, 2, 3, 4, 5, 6 };

		// Sintaxe alternativa para definir um array.
		int[] array4 = new int[5]  { 99,  98, 92, 97, 95};

		//Tamb�m � poss�vel copiarmos uma vari�vel array em outra vari�vel.
		int[] valor = new int[]  { 99,  98, 92, 97, 95};
		int[] copia = valor;

		//Podemos utilizar de exemplo como acessar o elemento de n�mero 92 deste array definida acima.
		int valorNoArray = valor[2]; 
	}
}
```

## Matrizes Multidimensionais

Uma matriz multidimensional, � na verdade um array multidimensional que pode ser declarado da seguinte forma:

```
<type>[,] <arrayName>;  //Array bidimensional.
<type>[,,] <arrayName>; //Array tridimensional.
```

Abaixo veremos alguns exemplos de como instanciar uma matriz multidimensional.

### Exemplo

```
using System;

public class Program
{
	public static void Main()
	{

		//Define uma matriz-2D de tamanho ``4x2``. Onde os �ndices est�o definidos de 0 � 3 e 0 at� 1.
		int[,] matriz2D = new int[4, 2];

		//Define uma matriz-3D de tamanho ``4x2x3``. Onde os �ndices est�o definidos de 0 � 3, 0 at� 1 e 0 at� 2.
		int[, ,] matriz3D = new int[4, 2, 3];

		//Sintaxe alternativa para definir uma matriz-2D de tamanho ``4x2``.
		int[,] matriz2D1 = new int[4, 2] { { 1, 2 }, { 3, 4 }, { 5, 6 }, { 7, 8 } };

		//Sintaxe alternativa para definir uma matriz-2D de tamanho ``4x2``.
		//Cada conjunto definido por ``{}`` significa uma linha da matriz. Enquanto cada elemento � definido pelo elemento i,j desta matriz.
		int[,] matriz2D2 = new int[,] { { 1, 2 }, { 3, 4 }, { 5, 6 }, { 7, 8 } };

		//Sintaxe alternativa para definir uma matriz-3D de tamanho ``2x2x3``.
		int[, ,] matriz3D2 = new int[,,] { { { 1, 2, 3 }, { 4, 5, 6 } },
										 { { 7, 8, 9 }, { 10, 11, 12 } } };

		//Sintaxe alternativa para definir uma matriz-3D de tamanho ``2x2x3``.
		int[, ,] matriz3D3 = new int[2, 2, 3] { { { 1, 2, 3 }, { 4, 5, 6 } },
											   { { 7, 8, 9 }, { 10, 11, 12 } } };

		//Podemos utilizar de exemplo como acessar o elemento de n�mero 12 desta matriz3D definida acima.
		int valor = matriz3D3[1,1,2]; 
	}
}
```

## Matrizes Denteadas

Uma matriz denteada � uma matriz cujos elementos s�o matrizes. Os elementos de uma matriz denteada podem ter diferentes dimens�es e tamanhos. �s vezes, uma matriz denteada � chamada de matriz de matrizes.

Tal como os exemplos anteriores, � poss�vel criar uma matriz denteada definida por n matrizes.

```
<type>[][] <arrayName>;  //Matriz bidimensional.

```

Diferente dos m�todos anteriores, criar uma matriz denteada, n�o cria o array na mem�ria. Portanto, � necess�rio fazer o seguinte:
```
using System;

public class Program
{
	public static void Main()
	{
		int[][] valores = new int[5][];

		//valores.Length � o tamanho deste array. Que neste caso � 5.
		for (int i = 0; i < valores.Length; i++) {
			
			//Cada array criado agora � um array de tamanho 4.
			valores[i] = new int[4];
		}
	}
}
```

Abaixo veremos alguns exemplos de como instanciar uma matriz denteada.

### Exemplo

```
using System;

public class Program
{
	public static void Main()
	{

		//Define uma matriz de array, onde o primeiro array possui 3 elementos e o segundo array possui 4 elementos.
		int[][] valores = new int[2][]{new int[]{92,93,94},new int[]{85,66,87,88}};

		//Define uma matriz de array, que possuem 5 arrays de tamanho 2.
		int[][] valores1 = new int[][]{new int[]{0,0}, new int[]{1,2},
						   new int[]{2,4}, new int[]{ 3, 6 }, new int[]{ 4, 8 } };

		//Podemos utilizar de exemplo como acessar o elemento de n�mero 6 desta matriz3D definida acima.
		int resultado = valores1[3][1]; 
	}
}
```