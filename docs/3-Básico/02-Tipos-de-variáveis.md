# 3.2 Tipos de Variáveis

## Tipos Padrões
Como toda linguagem de programação, o C# possui alguns tipos de variáveis padrões (tipos internos), onde estes podem ser vistos abaixo:


Palavra chave | Intervalo
------------- | -------------
bool		  | true ou false.
byte          | 0 ..255
sbyte         | -128 ..127
short         | -32,768 ..32,767
ushort        | 0 ..65,535
int           | -2,147,483,648 ..2,147,483,647
uint          | 	0 ..4,294,967,295
long          | -9,223,372,036,854,775,808..9,223,372,036,854,775,807
ulong         | 0 ..18,446,744,073,709,551,615
float         | -3.402823e38 ..3.402823e38
char		  | 	U+0000 .. U+ffff
decimal       | -79228162514264337593543950335..79228162514264337593543950335
double        | -1.79769313486232e308 ..1.79769313486232e308

Além de possuir os tipos string e object.

Uma coisa que vale ressaltar, é sobre o ``var`` e também o ``dynamic`` que podem ser facilmente mal entendidos.

### var
Essa paravra-chave do C# é utilizada para 2 contextos.
1. Puramente sintático - ou seja, quando voce utiliza **var** no seu código, o tipo atribuido é interpretado pelo compilador pelo resultado da expressao de atribuiçao, ex:
```csharp
var @int = 10; // isso é entendido pelo compilador como um numero inteiro (int)
var @double = 10.0 // este é visto como o tipo double, ja que nao foi explicitado o tipo flutuante (D, d, m, M, f, F) repectivamente double, decimal e float
```

2. Tipos anonimos - isso ocorre quando o resultado da expressao de atribuiçao não possui um tipo explicitado, e o compilador é o responsavel por gerar um tipo em tempo de compilação, ex:
```csharp
var value = new { IsValue = true };

//um exemplo de como é para compilador:
<T>x__1 a = new <T>x__1 { IsValue = true };
```

### dynamic
Essa palavra-chave, permite que voce acesse um metodo/prop/campo sem que precise saber o seu tipo.
O termo tecnico disso é dado por [Late Binding](https://en.wikipedia.org/wiki/Late_binding#Late_binding_in_.NET).

Uma coisa interessante sobre o **dynamic** é que caso durante o acesso do tipo, caso ele não encontre, irá disparar um erro em tempo de execuçao, a famosa, Exception!

**Uma coisa muito importante, é que o [var] e nem o [dynamic] sao tipos**

## Tipos Personalizados
CSharp, por ser uma linguagem orientada à objeto, permite a criação de classes para serem utilizadas como objetos. Além disso, permitem, enum, structs e interface.

