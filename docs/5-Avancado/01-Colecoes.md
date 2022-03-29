# 5.1 Coleções

Classes especializadas para manipulação de dados. São um aprimoramento dos _arrays_ e fornecem uma estrutura robusta para trabalhar com dados em diferentes tipos de cenários.

Existem 3 tipos de coleções:

- _Standard_ (Padrão)
- _Generic_ (Genérica)
- _Concurrent_ (Concorrente)

### **_Standard_**

São encontradas dentro do _namespace_ `System.Collections`. Não guardam dados tipados, somente objetos do tipo `Object`. São exemplos de coleções padrão: `ArrayList`, `Hashtable`, `Queue` e `Stack` .

> **Atenção** :warning: Atualmente é recomendado utilizar as coleções genéricas em `System.Collections.Generic` ou `System.Collections.Concurrent` em vez dos tipos legados em `System.Collections`.

Existe um _namespace_ chamado `System.Collections.Specialized`, que fornece coleções especializadas e tipadas como coleções _string-only_, _linked-list_ e dicionários híbridos.

### _Generic_

São encontradas dentro do _namespace_ `System.Collections.Generic`. São mais flexíveis e preferidas ao se trabalhar com dados. As coleções genéricas propiciam reuso de código, _type safety_ e performance. São exemplos de coleções genéricas: `Dictionary<T, T>`, `List<T>`, `Queue<T>`, `SortedList<T>` e `Stack<T>`.

### _Concurrent_

São encontradas dentro do _namespace_ `System.Collections.Concurrent`. São exemplos de coleções concorrentes: `BlockingCollection<T>`, `ConcurrentDictionary<T, T>`, `ConcurrentQueue<T>` e `ConcurrentStack<T>`.

Devem ser utilizadas quando for necessária a manipulação de coleções por múltiplas _threads_, pois suas implementações corrigem problemas de concorrência de suas classes correspondentes nos _namespaces_ `System.Collections` e `System.Collections.Generic`.

## Interfaces

Todas as coleções implementam algumas _interfaces_ em comum. Essas _interfaces_ definem as funcionalidades básicas em cada coleção.

As principais _interfaces_ são: `IEnumerable`, `ICollection`, `IDictionary` e `IList`.

<p align="center">
  <img src="https://user-images.githubusercontent.com/29133996/103426955-26a10400-4b9c-11eb-8d85-9ecbc2a53c8a.png">
</p>

`IEnumerable`: é a base para todos os tipos de coleções. Fornece um enumerador que possibilita iteração simples sob uma coleção não-genérica.

`ICollection`: define o tamanho, enumeradores e métodos de sincronização para todas as coleções não-genéricas.

`IDicionary`: representa uma coleção não-genérica de pares de chave-valor.

`IList`: representa uma coleção não genérica de objetos que podem ser acessados individualmente por índices.

As interfaces não são implementadas por todas as coleções, depende da natureza da coleção. Por exemplo, a interface `IDictionary` só seria implementada por coleções que faram o uso de pares chave-valor, como _Hashtable_ e _SortedList_.

## Principais coleções

### **ArrayList**

Essa coleção se encontra somente no namespace `System.Collections`. Sua classe tipada equivalente é a `List<T>`.

- Elementos podem ser adicionados e removidos da coleção a qualquer momento.
- Não é garantido de ordenação.
- A capacidade é o número de elementos que a lista pode conter.
- Os índices são baseados no zero, ou seja, o primeiro elemento tem o índice 0.
- Os elementos nessa coleção podem ser acessados utilizando um índice inteiro.
- Permite elementos duplicados.
- A utilização de arrays multidimensionais não é suportado.

É um array dinâmico. Fornece acesso dinâmico ao seus elementos. Um ArrayList automaticamente se expande quando um dado é adicionado. Ao contrário de arrays, podem guardar múltiplos tipos de dados. Os elementos são acessados por um índice inteiro, que são baseados em zero.

A indexação, inserção e remoção dos elementos no final da lista leva um tempo constante O(1). Mas inserir e remover elementos no meio do array dinâmico é mais custoso, leva um tempo linear O(n).

### **Hashtable**

- Chaves devem ser únicas e diferentes de nulas.
- Permite valores duplicados e nulos.
- Valores podem ser acessados utilizando a sua chave associada.
- Cada par de chave-valor é armazenado como um objeto _`DictionaryEntry`._

É uma coleção que armazena pares de chave-valor, ou seja, para cada valor adicionado é obrigatório informar uma chave única que irá servir para identificar o valor na lista.

**Implementação interna**

É composto de duas partes: um _array_ (geralmente de lista encadeada) e uma função _Hash_. O _array_ é onde os dados são armazenados e a função _Hash_ ajuda a decidir onde os dados devem ser salvos na memória do computador. O modo que isso funciona é que a função gera um _Hash_ a partir da chave e mapeia para um índice e o valor irá ser inserido naquela posição.

Um ótimo exemplo que é normalmente utilizado para mostrar como funciona é uma estante que pode ter no máximo 10 livros. Como é um exemplo, podemos supor que o algoritmo de mapeamento do _Hash_ funciona contando a quantidade de caracteres do título do livro para dividir pelo tamanho total da estante.

Pense da seguinte forma para esse exemplo: O livro "Guerra e Paz" tem 12 caracteres, o que significa que realizar o módulo de 12 % 10 retorna o restante que é 2, e o livro irá para a segunda prateleira da estante. Se pegarmos o livro "Cem Anos de Solidão" que tem 19 caracteres, irá para a nona prateleira e assim por diante.

Mas essa função de _Hash_ tem um problema, se inserirmos outro livro com 12 caracteres no título a posição será a mesma do primeiro livro, ou seja, segunda prateleira. Isso é o que chamamos de Colisão, quando dois ou mais elementos são hasheados ou mapeados para a mesma posição no _array_. A melhor forma de evitar é utilizar uma função que distribui os elementos uniformemente através da _HashTable_.

A versão genérica da coleção `Hashtable` é a `Dictionary<TKey,TValue>` que utiliza `KeyValuePair<TKey,TValue>`(chave-valor genérica) para enumeração em vez de `DictionaryEntry`.

### **Queue (Fila)**

- Permite elementos duplicados.
- Aceita `null` como um valor válido a ser inserido.

É uma coleção que representa uma fila, ou seja, o primeiro a entrar é o primeiro a sair. Quando um elemento é adicionado, entra no final da lista. Quando um elemento é removido, será sempre o primeiro da lista. Essa coleção é implementada como uma matriz circular.

As principais operações que podemos executar em uma fila são as seguintes:

- Enqueue: adiciona um elemento no final da fila.
- Dequeue: remove o primeiro elemento da fila.
- Peek: retorna o elemento mais antigo da fila, ou seja, o que está na primeira posição. Mas não o remove igual ao comando _Dequeue_.

### **Stack (Pilha)**

- Permite elementos duplicados.
- Aceita `null` como um valor válido a ser inserido.

É uma coleção que representa uma pilha, ou seja, o ultimo a entrar é o primeiro a sair. Quando um elemento é adicionado, entra no final da lista. Quando um elemento é removido, será também o último da fila.

As principais operações que podemos executar em uma fila são as seguintes:

- _Push_: adiciona um elemento no final da fila.
- _Pop_: remove o último elemento da fila.
- _Peek_: retorna o elemento mais novo da fila, ou seja, o que está na última posição. Mas não o remove igual ao comando _Pop_.

### **List**

É uma coleção que pertence ao _namespace `System.Collections.Generic`._ Equivale à classe `ArrayList`, mas fortemente tipada.

- Os elementos são acessados por índices, que começam em zero.
- Só pode conter elementos do tipo especificado em sua inicialização.
- São mais rápidas do que o `ArrayList` e menos suscetíveis a erros.
- Aceita `null` como um valor válido a ser inserido para tipos de referência.
- Aceita valores duplicados.
- Aumenta a capacidade dinamicamente.

Fornece múltiplos métodos de ordenação, procura e outros para a manipulação de seus elementos, o que facilita bastante seu uso em cenários diversos.

A lista não é ordenada ao inserir elementos, mas sim após realizarmos manualmente alguma operação como o método interno _Sort_.

**Implementação interna**

Quando acessamos um elemento utilizando índices, por debaixo dos panos estamos acessando a propriedade indexadora da lista que se chama `Item[Int32].` Recuperar e definir um valor utilizando essa propriedade são operações O(1).

Filas e pilhas são recomendadas para quando você precisa de armazenamento temporário, ou seja, será necessário descartar o valor após lê-lo. Use fila quando precisa ler os valores na mesma ordem em que são adicionados na coleção e pilha quando precisar ler a informação na ordem inversa. Se for necessária a leitura a partir de várias threads simultâneas, utilize a coleção `ConcurrentQueue<T>` ou `ConcurrentStack<T>`.

**É possível ver as notações Big-O de diferentes estruturas de dados e algoritmos no link a seguir: [https://www.bigocheatsheet.com/](https://www.bigocheatsheet.com/)**

## Thread-Safe

As coleções Standard `ArrayList` e `Hashtable` por exemplo fornecem uma pequena implementação _thread-safe_ através da propriedade `Syncronized`, que retorna um _wrapper thread-safe_ em torno da coleção. O _wrapper_ funciona bloqueando a coleção inteira em cada operação de escrita e remoção. Então, cada _thread_ que tenta acessar a coleção deve aguardar sua vez para pegar obter a permissão de bloqueio. O problema é que isso não é escalável e pode causar problemas de performance se utilizarmos listas com uma enorme quantidade de elementos. Esse design também não é totalmente protegido de _race conditions_ (falha em um sistema ou processo em que o resultado do processo é inesperadamente dependente da sequência ou sincronia doutros eventos).

Algumas das coleções concorrentes no namespace `System.Collections.Concurrent` utilizam mecanismos leves de sincronia como _SpinLock, SpinWait, SemaphoreSlim e CountdownEvent_ que foram introduzidos no .NET Framework 4. Esses tipos de sincronização utilizam _busy spinning_ por breves períodos antes de colocarem a thread em um estado de _true Wait._ Quando os tempos de espera são esperados serem curtos, _spinning_ é muito menos computacionalmente custoso do que esperar(_waiting_), que envolve uma transição de _kernel_ que geralmente é custosa. Para classes de coleção que utilizam _spinning,_ essa eficácia significa que multiplas _threads_ podem adicionar e remover itens em uma taxa muito alta. As classes `ConcurrentQueue<T>` e `ConcurrentStack<T>` não utilizam _locks._ Em vez disso, elas utilizam operações interligadas (_Interlocked operations_) para alcançar a _thread safety_.
