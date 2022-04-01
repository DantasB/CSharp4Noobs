# 4.3 Records

Record é um novo tipo de dado introduzido a partir do C# 9. Os records são imutáveis o que significa que uma vez que o objeto é instanciado passandos os dados no seu construtor, esses não podem mais ser alterados. Assim como classes o record possue herança e para podermos criar uma record devemos utilizar a palavra reservada `record` da mesma forma como criamos classes e structs.

```cs
public record Pessoa
{
  public string Nome {get; init;}
  public int Idade {get; init;}

  public Pessoa(string nome, int idade)
  {
    Nome = nome;
    Idade = idade;
  }
}
```
Também podemos abreviar a criação de records da seguinte forma.

```cs
public record Pessoa(string Nome, int Idade)
```

O código acima é equivalente do primeiro exemplo, dessa forma já declaramos o contrutor automáticamente e por padrão quando criamos um record utilizando essa sintaxe curta, o record é iniciado com a propriedade `init` que iremos falar em seguida.

## Propriedade init e expressão with

Como mencioado no início o record é imutável. Por padrão os records utilizam a propriedade `init` que funciona como instrução única, uma vez passado um valor este valor não pode ser alterado, se tentarmos alterar o valor após instanciar o objeto recebemos a seguinte mensagem de error

```cs
public record Pessoa(string Nome, int Idade);

var pessoa1 = new Pessoa("Larissa", 27);
pessoa1.Idade = 32; // 'Pessoa.Idade' só pode ser atribuído em um inicializador de objeto.
```

Certo, mas se record são imutáveis como alteramos o valor?

Com o C# 9 recebemos a expressão `with`. O with permite criar uma cópia de um objeto e alterar o valor das propriedades do objeto copiado.

```cs
public record Pessoa(string Nome, int Idade);

var pessoa1 = new Pessoa("Larissa", 27);

// nome Maia e idade 27
var pessoa2 = with pessoa1 { Nome = "Maia" };
```
No exemplo todas as propriedades de `pessoa1` foram copiadas para `pessoa2` mas o nome alteramos para Maia e `pessoa1` não sofreu nenhuma alteração, preservando a imutabilidade.

## Igualdade de referência

Assim como as classes os records representam um conjunto de propriedades e também possuem um tipo de refência, no caso dos records o tipo de referência é por igualidade. Mas o que isso significa?

Significa que enquanto as classes possuem seus tipos de referência dos seus dados armazenados na memória, os records possuem seus tipos de referência por valor. Na prática podemos observar com o exemplo abaixo onde temos uma classe `Pessoa1` e um record `Pessoa2`:

```cs
public record Pessoa1
{
  public string Nome {get; init;}
  public int Idade {get; init;}

  public Pessoa(string nome, int idade)
  {
    Nome = nome;
    Idade = idade;
  }
}

public record Pessoa2
{
  public string Nome {get; init;}
  public int Idade {get; init;}

  public Pessoa(string nome, int idade)
  {
    Nome = nome;
    Idade = idade;
  }
}
Pessoa1 pessoa1 = new Pessoa1("Adriano", 24);
Pessoa1 pessoa2 = new Pessoa1("Adriano", 24);

// resultado ao comparar as classes é false
Console.WriteLine(pessoa1==pessoa2);

Pessoa2 pessoa3 = new Pessoa2("Adriano", 24);
Pessoa2 pessoa3 = new Pessoa2("Adriano", 24);

// resultado ao comparar os records é true
Console.WriteLine(pessoa3==pessoa4);
```

O que acontece é que pessoa1 e pessoa2 possuem endereços diferentes na memória, então mesmo se tiverem propriedades iguais o resultado será `false` ao comparar. Por outro lado os records por ter seu tipo de referência por igualidade ao comparar duas instanciasa de records se os seus respectivos valores das propriedades forem iguais o resultado é ao realizar a comparação é `true`. Essa comparação por igualidade se dá atráves do metódo `Equals`

## Quando usar Record?

Records é um ótimo caso de uso quando é preciso comparar objetos, quando queremos garantir que os valores das propriedades de um objeto não possam ser alterados durante a execução de outros processos, copiar dados e usar records como DTO(Data Transport Object).

