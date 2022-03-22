# 5.3 Threads

Um thread é um pequeno conjunto de instruções projetadas para serem agendadas e executadas pela CPU independentemente do processo pai.
Por exemplo, um programa pode ter uma thread aberta esperando a ocorrência de um evento específico ou executando uma tarefa separada, permitindo que o programa principal execute outras tarefas.
Um programa é capaz de ter vários threads abertos ao mesmo tempo e os encerra ou suspende depois que a tarefa é concluída ou o programa é fechado.

### Instanciação de um delegate

Para instanciar um delegate, o método em que o delegate irá referenciar, precisa ser passado como parâmetro, exemplo:

-   _var thread1 = new Thread(NovoMétodoThread);_
    _NovoMétodoThread_ é um método que vai ser rodado em outro thread em primeiro ou segundo plano

### Chamada do delegate

Para rodar o Thread, apenas digite o nome do objeto instanciado adicionando .Start os parênteses na frente.

-   _thread1.Start();_

### Exemplos de código

-   _Thread trabalhando em algo em segundo plano_

```cs
using System;
using System.Threading;

public class ExamploThread
{
    private static void ProcessamentoEmThread()
    {
        for (int i = 0; i < 10; i++)
        {
            Console.WriteLine("Thread em segundo plano: {0}", i);
            Thread.Sleep(0);
        }
    }

    public static void Main()
    {
        Console.WriteLine("Thread Principal: Inicia um segundo Thread.");

        //Passamos o método ProcessamentoEmThread para que seja rodado em um outra linha de processamento
        var thread1 = new Thread(ProcessamentoEmThread);

        //Iniciamos o processamento do método
        thread1.Start();

        for (var i = 0; i < 4; i++)
        {
            Console.WriteLine("Thread Principal: Fazendo Algo.");
            //Se manter em 0 o tempo para a thread principal rodar, vai ver que
            //Ambos vão estar trabalhando ao mesmo tempo e em muitas vezes os textos se misturam
            //Tanto os da principal e a secundária
            Thread.Sleep(1);
        }

        Console.WriteLine(
            "Thread Principal: Use Join(), Para que o processo principal aguarde o processamento em segundo plano.");
        thread1.Join();
        Console.WriteLine("Thread Principal: O thread em segundo plano retornou e tudo foi encerrado.");
        Console.ReadLine();
    }
}
```
