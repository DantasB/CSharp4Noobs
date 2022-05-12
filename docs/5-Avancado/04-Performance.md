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

<img loading="lazy" src="https://s3.us-west-2.amazonaws.com/secure.notion-static.com/7d8507d0-3cc0-4357-b90f-1ee62713e97c/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45EIPT3X45%2F20220509%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20220509T234202Z&X-Amz-Expires=86400&X-Amz-Signature=50afc20809665452a7aa1d3c50421094d0e6d9e7f5c099e7e19ad44010231c8a&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22&x-id=GetObject">

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

- **Join** é usado quando normalmente você quer adicionar vários texto separado por um caracter. 

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

- **StringBuilder** é usado para concatenar strings e essa classe vem com algo diferenciado para concatenação, mas primeiro vamos entender a diferença entre usar o StringBuilder e uma concatenação por exemplo.

Quando fazemos 

```csharp
var texto = texto + "qualquer mensagem";
```
estamos fazendo algo perigoso dependendo na onde fazemos e se você pensou que o C# substituiu o valor anterior da varíavel pelo texto que adicionamos você acabou esquecendo um conceito importante chamado IMUTABILIDADE. Strings são imutáveis, ou seja, uma vez criada não pode ser alteradas, elas só podem ser alteradas criando um novo objeto na memória e descartando o valor anterior. Então imagina o seguinte cenário onde estamos dentro de um **FOR** percorrendo 100 vezes e nessas 100 vezes estamos fazendo o código acima, quanta memória não alocamos para fazer o processo não é mesmo? 

Peço que olhe com carinho os Method **ConcatenaçãoManual**, **StringBuilder**, **ConcatenacaoManualFor1000Elementos** e **StringBuilderFor1000Elementos**

Perceba que ConcatenaçãoManual e StringBuilder não há uma diferença grande, o teste realizado foi feito com poucas strings, mas agora repare em ConcatenacaoManualFor1000Elementos e StringBuilderFor1000Elementos que foi utilizado uma repetição de 1000x adiciona texto. Olhe a diferença colossal de memória alocada com a concatenaçãoManual em um **FOR** e usando o StringBuilder.

Mas ai pode surgir aquela pergunta, o que o StringBuilder tem de diferente da concatenação?
R:. Ele não cria um novo objeto a cada atribuição e sim expande dinamicamente a memória para caber mais strings, ou seja, não fica criando vários objetos que serão descartados rapidamente e sem contar que isso custa também para o garbage collector matar esse objetos.

Quando devo usar o StringBuilder ?
R:. Utilize o StringBuilder quando tiver que trabalhar com muita string, como por exemplo geração de arquivo de texto ou algo que envolva muito volume. Se for trabalhar com pouco texto utilize uma das funções citadas anteriormente, **MAS LEMBRE-SE, UTILIZE STRINGBUILDER COM GRANDES VOLUMES DE TEXTO**

<img loading="lazy" src="https://s3.us-west-2.amazonaws.com/secure.notion-static.com/989aad6e-a2e0-4255-9d90-1416d01ce9f0/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45EIPT3X45%2F20220512%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20220512T012415Z&X-Amz-Expires=86400&X-Amz-Signature=e093c4030bfd8a9592788e3358ed43f1bb209c50e5d9ff2989f754fed032189d&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22&x-id=GetObject">