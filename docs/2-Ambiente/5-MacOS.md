# 2.5 MacOS
Para este curso, utilizaremos o SDk do .Net Core versão 3.1 no decorrer dos tópicos, e por ser multiplataforma, você pode rodar seus projetos desenvolvidos em outros sistemas, no MacOS também!

## Instalando o .NET Core 
Instalar o SDK do .Net Core em um MacOS chega a ser tão fácil que fica chato, mas antes de tudo você deve conferir se o seu sistema MacOS tem suporte para rodar o .NET Core versão 3.1 que será utilizado nesse projeto, nesse [link](https://docs.microsoft.com/pt-br/dotnet/core/install/MacOS) você pode ver uma tabela com às versões do .Net Core suportada pro cada versão do MacOS. 

Caso o seu sistema MacOS tenha suporte a essa versão do .NET Core 3.1, você pode acessar o site oficial do .NET Core 3.1 e fazer o download do arquivo de instalação para o seu sistema MacOS.

[https://dotnet.microsoft.com/download](https://dotnet.microsoft.com/download)

> Nota: Lembre-se de selecionar a opção "macOS" e baixar o arquivo de instalação .pkg

Após baixar o arquivo de instalação basta executar ele e iniciar a instalação, nenhuma configuração será necessária para fazer o procedimento de instalação, no máximo a instalação deve solicitar a senha do usuário conectado ou o administrador da máquina.

Finalizado a instalação o MacOS deve propor a remoção do arquivo de instalação e pronto a VM (Virtual Machine) do .Net Core já está instalada no seu sistema e rodando.

Para garantir que o .Net Core está de fato rodando e instalado em sua máquina basta fazer um teste no seu sistema rodando o comando no seu terminal, o comando `dotnet --version`.

Esse comando deve solicitar qual é a versão do .Net Core instalada na sua máquina.

> Nota: Lembre-se que você deve iniciar um terminal após a instalação do dotnet, se não o shell não vai encontra a variável de ambiente dotnet

## Instalando o Visual Studio para Mac
A Microsoft disponibilizar uma versão da sua IDE para MacOS, você pode efetuar o download dessa versão acessado o site oficial do Visual Studio

[https://visualstudio.microsoft.com/pt-br/](https://visualstudio.microsoft.com/pt-br/)

Não vamos entrar em deatelhes na sua instalação já que se trata de uma instalação seguindo os padrões de aplicativo da App

> Nota: A instalação do Visual Studio vai oferecer mais algumas opções de pacotes para desenvolvimento mobile que não são necessária, instalá-los ou não vai de acordo com a sua preferência.

## Instalando o Visual Studio Code
A Microsoft disponibilizar uma versão para MacOS, você pode efetuar o download dessa versão acessado o site oficial do Visual Studio

[https://visualstudio.microsoft.com/pt-br/](https://visualstudio.microsoft.com/pt-br/)

No site do VSCode (Visual Studio Code) você deve conseguir o arquivo de aplicativo do VSCode, o arquivo .app, e para instalar o VSCode em seu MacOS, basta arrastar o arquivo para a pasta de aplicativos do MacOS.

> Nota: Caso você não queira instalar o VSCode em sua máquina você ainda pode utilizá-lo usando o navegador ou executado diretamente o arquivo .app

Um detalhe que você possa querer em seu VSCode é configurar a variável de ambiente `code` e para isso no MacOS você deve abrir o seu VSCode e executar o comando em seu teclado `Cmd + Shift + P`, deve abrir um caixa de texto na parte superior do VSCode, escrever o comando `shell command` e executar, feito isso o VSCode vai configura essa variável para você.

Para mais detalhes você pode dar uma olhada na documentação do VSCode em [https://code.visualstudio.com/docs/setup/mac](https://code.visualstudio.com/docs/setup/mac)

## Criando seu projeto
O .Net Core oferece um comando que disponibiliza a criação de alguns projetos usando modelos pré-fabricados por eles.

Para criar um novo projeto com base em algum modelo, basta executar em seu terminal o comando `dotnet new <Tipo do projeto>`.

Caso você queira dar uma olhada nos tipos de projeto e em outros comandos você pode consultar a documentação do .Net Core.
[https://docs.microsoft.com/pt-br/dotnet/core/tools/dotnet-new#arguments](https://docs.microsoft.com/pt-br/dotnet/core/tools/dotnet-new#arguments)

## Executando seu projeto

Após criado seu projeto você pode executá-lo pelo terminal utilizando o comando `dotnet run`.

> Nota: Esse comando deve ser executado dentro da pasta raiz do seu projeto
