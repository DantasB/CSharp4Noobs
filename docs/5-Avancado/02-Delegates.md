# 5.2 Delegates

Um delegate é uma referência a um método com a mesma assinatura, ou seja, podemos chamar métodos através de delegates desde que seu tipo de retorno e seus parâmetros sejam convergentes.

Declaração de um delegate:

-   _public delegate void MyDelegate();_
    Onde _void_ é o tipo de retorno e _MyDelegate_ é o nome do delegate.

### Instanciação de um delegate

Para instanciar um delegate, o método em que o delegate irá referenciar, precisa ser passado como parâmetro, exemplo:

-   _MyDelegate delegate1 = new MyDelegate(método);_

### Chamada do delegate

Para chamar o delegate, apenas digite o nome do objeto instanciado adicionando os parênteses na frente.

-   _delegate1();_

## Exemplos

-   _Delegate sem retorno e sem parâmetros_

```csharp
using System;

namespace testes
{
    class Program
    {
        //Delegate
        public delegate void MyDelegate();

        //Metodo
        static void Print()
        {
            Console.WriteLine("Olá, mundo!");
        }
        static void Main(string[] args)
        {
            //Instanciando um delegate
            MyDelegate delegate1 = new MyDelegate(Print);

            //Chamando o delegate
            delegate1();
        }
    }
}
```

-   _Delegate sem retorno e com parâmetros_

```csharp
using System;

namespace testes
{
    class Program
    {
        //Delegate
        public delegate void MyDelegate(string messagem);

        //Metodo
        static void Print(string msg)
        {
            Console.WriteLine(msg);
        }
        static void Main(string[] args)
        {
            //Instanciando um delegate
            MyDelegate delegate1 = new MyDelegate(Print);

            //Chamando o delegate e atribuindo a uma variavel local
            delegate1("Olá, mundo!");
        }
    }
}
```

-   _Delegate com retorno e com parâmetros_

```
using System;

namespace testes
{
    class Program
    {
        //Delegate
        public delegate int MyDelegate(int numero1, int numero2);

        //Metodo
        static int Area(int n1, int n2)
        {
            return n1 * n2;
        }
        static void Main(string[] args)
        {
            int x = 10;
            int y = 5;
            int resultado = 0;

            //Instanciando um delegate
            MyDelegate delegate1 = new MyDelegate(Area);

            //Chamando o delegate e atribuindo a uma variavel local
            resultado = delegate1(x, y);

            //Exibindo no console a saída do método apontado pelo delegate
            Console.WriteLine(resultado);
        }
    }
}
```