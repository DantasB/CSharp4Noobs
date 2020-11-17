# 4.1 Modificadores de acesso

São palavras-chave que servem para especificar a acessibilidade de um tipo ou membro.

No C#, temos quatro tipos de modificadores
- **public**: o acesso ao membro pode ser de qualquer lugar
- **protected**: somente as classes que derivam dela podem acessar o membro
- **internal**: só pode ser acessado de dentro do assembly em que está declarado
- **private**: não pode ser acessado de fora da própria classe

É possível também utilizar dois tipos em conjunto, como por exemplo:
- **protected internal**
- **private protected**

A omissão do modificador de acesso na declaração de uma classe deixará implícito que o acesso será do tipo **internal**.

```csharp
// O tipo de acesso será do tipo internal
class Aluno 
{
}
```

A omissão do modificador de acesso na declaração de um membro deixará implícito que o acesso será do tipo **private**.
```csharp
public class Aluno 
{
  // O tipo de acesso deste método será private
  void CalcularNota()
  {
  }
}
```