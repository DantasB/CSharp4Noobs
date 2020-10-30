# 3.10 Conversão de Tipo (Typecast)

Como pudemos observar em alguns exemplos anteriores, é possível fazer a conversão de um tipo (int, string, bool) para outro tipo em C#.

Aquela maneira que vimos não é a única. Veremos abaixo outras maneiras de fazer o ``Typecast``

é importante frizar, que esta linguagem possui duas maneiras genéricas:

## [Conversão Implícita](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/language-specification/conversions#implicit-conversions)

As conversoes implicitas, como o proprio nome diz, ocorrem quando nao é explicitado (fica evidente) o tipo da conversão.

### Boxing
Esse tipo de conversão ocorre quando o resultado expressão é atribuido a um tipo ``object``.
```csharp
//<= C# 8
Pessoa p = new Pessoa();
//C# 9
//Pessoa p = new();

object obj = p; //Boxing
```

Note que não é possível fazer a conversão implícita para todos os tipos. Vamos observar um pouco melhor abaixo:

```
//Ordem de containerização:
De sbyte -> short, int, long, float, double, decimal.
De byte -> short, ushort, int, uint, long, ulong, float, double, decimal.
De short -> int, long, float, double, decimal.
De ushort -> int, uint, long, ulong, float, double, decimal.
De int -> long, float, double, decimal.
De uint -> long, ulong, float, double, decimal.
De long -> float, double, decimal.
De ulong -> float, double, decimal.
De char -> ushort, int, uint, long, ulong, float, double, decimal.
De float -> double.
```

### Implicit Operator <img alt="Badge em breve" src="https://img.shields.io/badge/-EM%20BREVE-purple">

## Conversão Explícita 

Sao todas as implícitas, e outras conversoes onde ficam explicitados os tipos da conversão.

### Operador Cast (T)

#### Unboxing

### Operador AS

Falar sobre a diferença do Cast, nao dispara exception...

### Explicit Operator <img alt="Badge em breve" src="https://img.shields.io/badge/-EM%20BREVE-purple">
