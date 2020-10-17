# 3.3 Modificadores

Modificadores, tamb�m conhecidos como modificadores de acesso, s�o necess�rios para definir a visibilidade desta vari�vel, fun��o ou classe, ou seja, como outras classes ver�o este objeto.

Como dito anteriormente, a vari�vel n�o precisa ser declarada com modificador de acesso, contudo, internamente, o C# define um modificador chamado *private*.

Abaixo voc�s podem observar melhor a lista de Modificadores existentes no C#:

Modificador		   | Funcionamento
-------------	   | -------------
public			   | O acesso n�o � restrito.
protected	   	   | O acesso � limitado �s classes ou tipos derivados daclasse que a vari�vel est�.
Internal		   | O acesso � limitado ao conjunto de m�dulos(assembly) corrente.
protected internal | O acesso � limitado ao conjunto corrente ou tiposderivados da classe recipiente.
private			   | O acesso � limitado � classe que a vari�vel est�.
readonly		   | A escrita n�o � permitida.
