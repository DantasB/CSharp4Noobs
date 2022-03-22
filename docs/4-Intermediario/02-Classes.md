# 4.2 Classes

As classes em uma linguagem orientada a objetos, no caso o C#, podem ser pensadas como um template para o que um objeto deveria ser.

Representa um conjunto de propriedades ou métodos que são comuns para o objeto que está sendo pensado.

Uma classe básica pode ser declarada do seguinte modo:

```cs
// [modificador de acesso] - [palavra chave 'class'] - [nome da classe]
public class Pessoa
{
}
```

## Construtor

É basicamente o método que é chamado ao se instanciar uma classe. Serve para iniciar a classe com os dados básicos necessários para executar sua tarefa.

Os parâmetros são opcionais, podendo se instanciar a classe sem nenhum dado passado para ela.

Caso não se declare o construtor, ficará implícito que a classe contem um construtor padrão, sem nenhum parâmetro.

É possível declarar múltiplos construtores com parâmetros diferente em uma mesma classe.

```cs
public class Pessoa
{
  // Construtor padrão
  public Pessoa()
  {
  }

  // Construtor com 1 parâmetro
  public Pessoa(string nome)
  {
  }

  // Construtor com 2 parâmetros
  public Pessoa(string nome, int idade)
  {
  }
}
```

## Classes Estáticas

A inclusão da palavra chave `static` na declaração da classe define que ela não poderá ser instanciada e todos os membros (métodos, propriedades) também deverão ser estáticos. De resto, é basicamente uma classe comum.

```cs
// Definição da classe
public static class Pessoa
{
}
```

Para chamar uma classe estática, é necessário utilizar seu nome, como no exemplo abaixo:

```cs
// [nome da classe].[metodo|propriedade]
Pessoa.MetodoQualquer();
```

## Construtores estáticos

São utilizados para inicializar dados estáticos na classe, ou para executar alguma ação que precisa ser executada apenas uma vez.

Os construtores estáticos são chamados antes de qualquer construtor da instância ou membro é acessado.

Independente da classe ser estática ou não, pode ter somente 1 construtor estático, enquanto uma classe não-estática podem ter quantos construtores de instância forem necessários.

```cs
public class Pessoa
{
  // campo estático
  static readonly int idade;

  // Construtor estático
  static Pessoa()
  {
    idade = 20;
  }
}
```

## Classes sealed

Adicionando a palvra `sealed` em uma classe irá impedir que outras classes possam herdar os atributos e métodos desta classe.

```cs
public sealed class Motor
{
}

public class MotorGasolina : Motor
{
}
```

Feito isso caso uma classe deseje extender seus atributos e comportamentos irá ocasionar um erro em tempo de compilação.
O erro que irá aparecer no console será;
`'MotorGasolina': cannot derive from sealed type 'Motor'`

## Classes Genéricas

No C# é possível realizar a criação de classes genéricas, que podem utilizam parâmetros especificados em sua assinatura, exigindo que o parâmetro passado para a classe seja de determinado tipo ou não.
Neste caso abaixo veremos uma especificação genérica que não exige nenhuma herança da classe que for passada por parâmetro.

```cs
// Definição de um tipo genérico é dado geralmente entre <TipoGenericoAqui>
public class Motor<TCombustivel>
{
    Ligar(TCombustivel combustivel) {  }
}
// Abaixo ele estará passando como parâmetro para a classe `Motor` que espera algum parâmetro que o tipo esperado é a classe Gasolina
public class MotorGasolina : Motor<Gasolina>
{
}
```

No exemplo abaixo, será exigido que todo o parâmetro passado abaixo deverá conter a herança da classe `Combustivel`. Dentro da classe motor será possível manipular todos os atributos e métodos que forem definidos na classe que for exigida como parametro de entrada que no nosso caso é a `Combustivel`.

```cs
// Também é possível exigir que a classe que for passada por parâmetro siga uma pré-definição ou seja, que ela derive de uma herança.
public class Combustivel
{
  public string TipoCombustivel { get; set; }
}
// Abaixo a criação de uma classe que exige quem for passado por parâmetro tenha uma herança de Combustivel
public sealed class Motor<TCombustivel> where TCombustivel : Combustivel
{
    Ligar(TCombustivel combustivel)
    {
       //Aqui poderá manipular os atributos da classe combustivel
       Console.WriteLine(combustivel.TipoCombustivel);
    }
}
```
