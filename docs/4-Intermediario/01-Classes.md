# 4.1 Classes

As classes em uma linguagem orientada a objetos, no caso o C#, podem ser pensadas como um template para o que um objeto deveria ser.

Representa um conjunto de propriedades ou métodos que são comuns para o objeto que está sendo pensado.

Uma classe básica pode ser declarada do seguinte modo:
```csharp
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

```csharp
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