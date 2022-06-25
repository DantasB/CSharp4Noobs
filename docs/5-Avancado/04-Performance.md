# 5.4 Performance

Hoje no mundo da programação temos diversos problemas que conseguimos resolver de maneiras variadas. Mas já pensou em qual cenário sua aplicação ganharia desempenho? Será que utilizar função X é melhor que a função Y ? A biblioteca Benchmark.NET, nos dá uma gama de resultados que conseguimos mensurar o desempenho de cada parte do nosso código.

## **Cases**

### **For x Foreach**

Tanto **_For_** quanto **_Foreach_** servem para percorrer uma coleção. Primeiro vamos entender cada um.

- **For**: utilizamos quando queremos ter um controle maior sobre a iteração dos elementos. Com ele conseguimos criar regras mais complexa na iteração, pois temos acesso a posição de cada elemento.

- **Foreach**: visualmente mais simples de usar, normalmente usamos quando queremos percorrer todos os elementos da coleção sem ter a necessidade de ficar se preocupando com a iteração.

Quais deles é melhor ?

- Isso depende da sua necessidade. Em termos de desempenho o **_For_** é melhor do que o **_Foreach_**. Mas por quê?

    - R:. Dentro do **_Foreach_** existe algumas validações e ele usa os métodos GetEnumerator() e Next() para poder verificar se existe mais elementos para percorrer, o que acaba degradando o desempenho. Imagem abaixo mostra testes realizados com **_for_**, **_foreach_** e o **_foreach do linq_**. De momento reparemos apenas na coluna **Mean** que foi o tempo levado para realizar as tarefas.

![Performance iteracao](https://user-images.githubusercontent.com/39220517/168403053-34efadf2-4a82-4642-9af5-1530cdded009.png)

- Se ficar em dúvida em qual utilizar utilize o seguinte pensamento:

    - Preciso da maior otimização possível no meu código ?
        - Se sim, opte pelo **_for_**.
        - Se não, utilize o **_foreach_**.
    - Vale lembrar que precisamos pensar na legibilidade do nosso código, se onde você está utilizando essa iteração for um lugar sombrio e difícil de dar manutenção como códigos legados, talvez seja uma boa usar o **_foreach_**.

-------

### **Join x StringBuilder x Concatenação x Concat**
<br>
Dentro do C# temos algumas maneiras de trabalhar com texto, são elas:

- StringBuilder
- Concatenação
- Concat
- Join

Certo, e quando devo usar cada uma delas ?

- **Join** é usado quando normalmente você quer adicionar vários textos separados por um caracter. 

```csharp
 var mensagem = string.Empty;
 string[] animais = {"cachorro", "gato", "dinossauro", "marmota", "esquilo"};

 mensagem = string.Join(" ", animais);
```
Nesse caso estou criando um texto com todos os nomes dos animais separados com um espaço que foi definido no primeiro argumento da função Join.

- **Concatenação** é usado quando precisamos fazer algo simples com texto como por exemplo, mostrar uma mensagem de erro com alguma informação extra vindo de uma variável.

```csharp
 var mensagemBase = "Houve um erro ao gravar a informação. ";
 var mensagemErro = "A informação X não pode ser nula";

 var mensagemFinal = mensagemBase + mensagemErro;
 
```
ou poderiamos usar a interpolação

```csharp
 var mensagemBase = "Houve um erro ao gravar a informação. ";
 var mensagemErro = "A informação X não pode ser nula";

 var mensagemFinal = $"{mensagemBase} {mensagemErro}";
 
```

- **Concat** é quando temos um array de string, podendo ser uma lista ou um array mesmo e queremos tornar essa lista em uma string.

```csharp
IEnumerable<string> lista = new List<string>() { "Testando ", "a ", " função", " Concat."};
string mensagem = string.Concat(lista);
Console.WriteLine(mensagem);

/*
    Retorno: Testando a  função Concat.
*/
```
**E por último, a cereja do bolo**

- **StringBuilder** é usado para concatenar strings e essa classe vem com algo diferenciado para concatenação, mas primeiro vamos entender a diferença entre usar o StringBuilder e uma concatenação por exemplo:

Quando fazemos o código abaixo

```csharp
var texto = texto + "qualquer mensagem";
```
estamos realizando algo perigoso dependendo na onde fazemos e se você pensou que o C# substituiu o valor anterior da varíavel pelo texto que adicionamos você acabou esquecendo um conceito importante chamado IMUTABILIDADE. Strings são imutáveis, ou seja, uma vez criada não pode ser alteradas, elas só podem ser alteradas criando um novo objeto na memória e descartando o valor anterior. Então imagina o seguinte cenário onde estamos dentro de um **FOR** percorrendo 100 vezes e nessas 100 vezes estamos fazendo o código acima, quanta memória não alocamos para fazer o processo não é mesmo? 

Peço que olhe com carinho os Method **ConcatenaçãoManual**, **StringBuilder**, **ConcatenacaoManualFor1000Elementos** e **StringBuilderFor1000Elementos**

Perceba que ConcatenaçãoManual e StringBuilder não há uma diferença grande, o teste realizado foi feito com poucas strings, mas agora repare em ConcatenacaoManualFor1000Elementos e StringBuilderFor1000Elementos que foi utilizado uma repetição de 1000x adicionando texto. Olhe a diferença colossal de memória alocada com a concatenaçãoManual em um **FOR** e usando o StringBuilder.

Mas ai pode surgir aquela pergunta, o que o StringBuilder tem de diferente da concatenação?
R:. Ele não cria um novo objeto a cada atribuição e sim expande dinamicamente a memória para caber mais strings, ou seja, não fica criando vários objetos que serão descartados rapidamente e sem contar que isso custa também para o Garbage Collection matar esses objetos.

Quando devo usar o StringBuilder ?
R:. Utilize o StringBuilder quando tiver que trabalhar com muito texto, como por exemplo geração de arquivo ou algo que envolva muito volume. Se for trabalhar com pouco texto utilize uma das funções citadas anteriormente, **MAS LEMBRE-SE, UTILIZE STRINGBUILDER COM GRANDES VOLUMES DE TEXTO**

![Performance texto](https://user-images.githubusercontent.com/39220517/168403154-96911543-9709-4ea0-850e-9c039859f0bf.png)

-------

### **Lista vazia**

Hoje para podermos validar se uma lista está preenchido temos algumas funções que realizam isso pra gente. Vamos ver quais são eles:

- Propriedade Count
- Método Count (disponibilizado pelo linq)
- Any (disponibilizado pelo linq)
- FirstOrDefault (disponibilizado pelo linq)

Abaixo vemos que a propriedade que Count que existe na lista é a campeã, porque a cada remoção e adição de um elemento na lista ela incrementa ou decrementa nessa propriedade.

![lista](https://user-images.githubusercontent.com/39220517/168930958-7a65b18c-7cd3-46f2-b9f7-ff59b82fa79c.png)

 Já as demais maneiras como Count(), Any() e FirstOrDefault() há mais validações e chamadas de métodos como GetEnumerator() e MoveNext() o que gera o uso de recursos levando mais tempo. Então se caso precisar validar se a lista está vazia, opte para a propriedade que há na lista.


