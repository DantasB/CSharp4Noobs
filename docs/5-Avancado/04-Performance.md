# 5.4 Performance

Hoje no mundo da programação temos diversos problemas que conseguimos resolver de maneiras variadas. Mas já pensou em qual cenário sua aplicação ganharia desempenho? Será que utilizar função X é melhor que a função Y ? A biblioteca Benchmark.NET, nos dá uma gama de resultados que conseguimos mensurar o desempenho de cada parte do nosso código.

## **Cases**

### For x Foreach

Tanto **_For_** quanto **_Foreach_** servem para percorrer uma coleção. Primeiro vamos entender cada um.

- **For**: utilizamos quando queremos ter um controle maior sobre a iteração dos elementos. Com ele conseguimos criar regras mais complexa na iteração, pois temos acesso a posição de cada elemento.

- **Foreach**: visualmente mais simples de usar, normalmente usamos quando queremos percorrer todos os elementos da coleção sem ter a necessidade de ficar se preocupando com a iteração.

Quais deles é melhor ?

- Isso depende da sua necessidade. Em termos de desempenho o **_For_** é melhor do que o **_Foreach_**. Mas por quê?

    - R:. Dentro do **_Foreach_** existe algumas validações e ele usa os métodos GetEnumerator() e Next() para poder verificar se existe mais elementos para percorrer, o que acaba degradando o desempenho. Imagem abaixo mostra testes realizados com **_for_**, **_foreach_** e o **_foreach do linq_**. De momento reparemos apenas na coluna **Mean** que foi o tempo levado para realizar as tarefas.

<img src="https://s3.us-west-2.amazonaws.com/secure.notion-static.com/7d8507d0-3cc0-4357-b90f-1ee62713e97c/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45EIPT3X45%2F20220509%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20220509T234202Z&X-Amz-Expires=86400&X-Amz-Signature=50afc20809665452a7aa1d3c50421094d0e6d9e7f5c099e7e19ad44010231c8a&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22&x-id=GetObject">

- Se ficar em dúvida em qual utilizar utilize o seguinte pensamento:
    - Preciso da maior otimização possível no meu código ?
        - Se sim, opte pelo **_for_**.
        - Se não, utilize o **_foreach_**.
    - Vale lembrar que precisamos pensar na legibilidade do nosso código, se onde você está utilizando essa iteração for um lugar sombrio e difícil de dar manutenção como códigos legados, talvez seja uma boa usar o **_foreach_**.