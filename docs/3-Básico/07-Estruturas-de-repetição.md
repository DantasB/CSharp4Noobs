# 3.7 Estruturas de Repetição

Os comandos de repetição são um recurso que permite que um certo trecho do código de um programa dentro deste loop seja repetido um certo número de vezes.
Facilitando gerar códigos mais organizados e lógicas mais complexas.

Na liguagem C# existem três comandos de repetição: while, do-while e for.

## While

O `While` é uma estrutura de loop que funciona com um valor condicional instanciado fora do loop.
Esta estrutura irá checar primeiro a condição e, caso a condição seja `true` o código será executado

### Exemplo

```cs
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

Depois de compilado, o resultado será:

```
0
1
2
3
4
```

## Do-While

O `Do-While` é uma estrutura de loop que funciona com um valor condicional instanciado fora do loop.
Contudo, diferente do `While` regular, esta estrutura irá rodar o código primeiro, e depois verificar a condição.

### Exemplo

```cs
using System;

public class Program
{
    public static void Main()
    {
        int controle = 0;

        //Faça.
        do
        {
            Console.WriteLine(controle);

            //Soma 1 ao controle
            controle++;

        }while(controle < 5); //Enquanto controle for menor que 5.
    }
}
```

Depois de compilado, o resultado será:

```
0
1
2
3
4
```

Neste exemplo específico, o resultado para ambos os loops é igual. Contudo é necessário ter cuidado com a lógica utilizada para que não seja obtido algum resultado inesperado.

## For

O `for` é uma estrutura de loop que funciona com um valor condicional instanciado fora do loop.
Esta estrutura irá checar primeiro a condição e, caso a condição seja `true` o código será executado

### Exemplo

```cs
using System;

public class Program
{
    public static void Main()
    {
        //Para cada i, enquanto i for menor que 5, soma 1 ao i após o término do primeiro passo.
        for(int i = 0; i<5; i++)
        {
            Console.WriteLine(i);
        }
    }
}
```

Depois de compilado, o resultado será:

```
0
1
2
3
4
```

## Foreach

O `foreach` é uma estrutura de loop que funciona um pouco diferente das outras estruturas.
Esta função em específico irá iterar cada objeto que está dentro de outro objeto maior. (será melhor observando o exemplo abaixo)

### Exemplo

```cs
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

Depois de compilado, o resultado será:

```
s
u
c
e
s
s
o
```
