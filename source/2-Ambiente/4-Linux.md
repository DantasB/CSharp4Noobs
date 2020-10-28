# 2.4 Sistema Linux

Como conversamos anteriormente, sabemos que � poss�vel programar em C# utilizando o linux. Abaixo, teremos um passo a passo de como configurar seu sistema linux para programar em C# sem maiores dificuldades.

## Passos

- [Instalem o SDK](https://docs.microsoft.com/pt-br/dotnet/core/install/linux) neste link ter� uma s�rie de c�digos disponibilizados pela pr�pria micrososoft, para nos ajudar a instalar o SDK pelo terminal.
	- Ap�s instalado, verifique a vers�o do .NetCore utilizando o seguinte comando em seu terminal: ``dotnet --info``. Caso n�o haja erro na instala��o, voc� ver� a vers�o instalada do .Net Core.
- Instalem um editor de texto de seu interesse. (No geral os desenvolvedores tem um apresso por esse editor, ent�o daremos algumas dicas de extens�es para utilizar).
	- Como extens�es indicaremos 3: (C#, C# Extensions e NuGet Package Manager*)
- Crie seu projeto dentro da pasta que voc� preferir**
- Rode seu projeto criado.

*: Para este curso b�sico esta extens�o n�o � necess�ria. Por�m, futuramente pode vir a ser.

## Criando seu projeto:

Para criar seu projeto em C#, devemos utilizar o seguinte comando no terminal:
``dotnet new <Tipo do Projeto>`` 

OBS: Se n�o definirmos o tipo do projeto, criaremos um console application. (Aconselho este tipo de projeto para o tutorial)

Al�m disso, � poss�vel definir qual o tipo de projeto voc� pretende criar. [E, para facilitar nossas vidas, a microsoft nos disponibilizou uma s�rie de argumentos para utilizar.](https://docs.microsoft.com/pt-br/dotnet/core/tools/dotnet-new)

## Executando seu projeto:

Ap�s criado seu projeto voc� pode executa-lo pela sua IDE ou utilizando o comando ``dotnet run`` em seu terminal.

## Alternativas de IDE

Como alternativas ao VSCode, gostaria de sugerir o Rider, uma ide desenvolvida pela [JetBrains](https://www.jetbrains.com/rider/) e tamb�m o [MonoDevelop](https://www.monodevelop.com/), por�m, como ressaltei no come�o, escolha o editor de texto ou ide que preferir.

