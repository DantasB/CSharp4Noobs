# 2.4 Sistema Linux

Como conversamos anteriormente, sabemos que é possível programar em C# utilizando o linux. Abaixo, teremos um passo a passo de como configurar seu sistema linux para programar em C# sem maiores dificuldades.

## Passos

- [Instalem o SDK](https://docs.microsoft.com/pt-br/dotnet/core/install/linux) neste link terá uma série de códigos disponibilizados pela própria microsoft, para nos ajudar a instalar o [SDK](https://pt.wikipedia.org/wiki/Kit_de_desenvolvimento_de_software) pelo terminal.
	- Após instalado, verifique a versão do .Net Core utilizando o seguinte comando em seu terminal: ``dotnet --info``. Caso não haja erro na instalação, você verá a versão instalada do .Net Core.
- Instalem um editor de texto de seu interesse. (No geral os desenvolvedores tem um apresso por esse editor, então daremos algumas dicas de extensões para utilizar).
	- Como extensões indicaremos 3: (C#, C# Extensions e NuGet Package Manager*)
- Crie seu projeto dentro da pasta que você preferir**
- Rode seu projeto criado.

*: Para este curso básico esta extensão não é necessária. Porém, futuramente pode vir a ser.

## Criando seu projeto:

Para criar seu projeto em C#, devemos utilizar o seguinte comando no terminal:
``dotnet new <Tipo do Projeto>`` 

OBS: Se não definirmos o tipo do projeto, criaremos um console application. (Aconselho este tipo de projeto para o tutorial)

Além disso, é possível definir qual o tipo de projeto você pretende criar. [E, para facilitar nossas vidas, a microsoft nos disponibilizou uma série de argumentos para utilizar.](https://docs.microsoft.com/pt-br/dotnet/core/tools/dotnet-new)

## Executando seu projeto:

Após criado seu projeto você pode executá-lo pela sua [IDE](https://pt.wikipedia.org/wiki/Ambiente_de_desenvolvimento_integrado) ou utilizando o comando ``dotnet run`` em seu terminal.

## Alternativas de [IDE](https://pt.wikipedia.org/wiki/Ambiente_de_desenvolvimento_integrado)

Como alternativas ao VSCode, gostaria de sugerir o Rider, uma [IDE](https://pt.wikipedia.org/wiki/Ambiente_de_desenvolvimento_integrado) desenvolvida pela [JetBrains](https://www.jetbrains.com/rider/) e também o [MonoDevelop](https://www.monodevelop.com/), porém, como ressaltei no começo, escolha o editor de texto ou [IDE](https://pt.wikipedia.org/wiki/Ambiente_de_desenvolvimento_integrado) que preferir.

