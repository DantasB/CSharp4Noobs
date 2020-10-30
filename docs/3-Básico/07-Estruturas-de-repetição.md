# 3.7 Estruturas de Repeti��o
Os comandos de repeti��o s�o um recurso que permite que um certo trecho do c�digo de um programa dentro deste loop seja repetido um certo n�mero de vezes. 
Facilitando gerar c�digos mais organizados e l�gicas mais complexas.

Na liguagem C# existem tr�s comandos de repeti��o: while, do-while e for.

## While

O ``While`` � uma estrutura de loop que funciona com um valor condicional instanciado fora do loop.
Esta estrutura ir� checar primeiro a condi��o e, caso a condi��o seja ``true`` o c�digo ser� executado

### Exemplo

```
using System;

public class Program
{
    public static void Main()
    {
        int controle = 0;

        //Enquanto controle for menor que 5.
        while(controle < 5)
        {
            Console.WriteLine(controle);

            //Soma 1 ao controle.
            controle++;
        }
    }
}
```

Depois de compilado, o resultado ser�:

```
0
1
2
3
4
```

## Do-While

O ``Do-While`` � uma estrutura de loop que funciona com um valor condicional instanciado fora do loop.
Contudo, diferente do ``While`` regular, esta estrutura ir� rodar o c�digo primeiro, e depois verificar a condi��o.

### Exemplo
```
using System;

public class Program
{
    public static void Main()
    {
        int controle = 0;

        //Fa�a.
        do
        {
            Console.WriteLine(controle);

            //Soma 1 ao controle
            controle++;

        }while(controle < 5); //Enquanto controle for menor que 5.
    }
}
```

Depois de compilado, o resultado ser�:

```
0
1
2
3
4
```

Neste exemplo espec�fico, o resultado para ambos os loops � igual. Contudo � necess�rio ter cuidado com a l�gica utilizada para que n�o seja obtido algum resultado inesperado. 

## For

O ``for`` � uma estrutura de loop que funciona com um valor condicional instanciado fora do loop.
Esta estrutura ir� checar primeiro a condi��o e, caso a condi��o seja ``true`` o c�digo ser� executado

### Exemplo

```
using System;

public class Program
{
    public static void Main()
    {
        //Para cada i, enquanto i for menor que 5, soma 1 ao i ap�s o t�rmino do primeiro passo.
        for(int i = 0; i<5; i++)
        {
            Console.WriteLine(i);
        }
    }
}
```

Depois de compilado, o resultado ser�:

```
0
1
2
3
4
```

## Foreach

O ``foreach`` � uma estrutura de loop que funciona um pouco diferente das outras estruturas.
Esta fun��o em espec�fico ir� iterar cada objeto que est� dentro de outro objeto maior. (Ser� melhor observando o exemplo abaixo)

### Exemplo

```
using System;

public class Program
{
    public static void Main()
    {
        string valor = "sucesso";

        //Para cada caractere na string valor, imprime esse caractere.
        foreach(char caractere in valor)
        {
            Console.WriteLine(caractere);
        }
    }
}
```

Depois de compilado, o resultado ser�:

```
s
u
c
e
s
s
o
```
