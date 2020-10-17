# 3.3 Modificadores

Modificadores, também conhecidos como modificadores de acesso, são necessários para definir a visibilidade desta variável, função ou classe, ou seja, como outras classes verão este objeto.

Como dito anteriormente, a variável não precisa ser declarada com modificador de acesso, contudo, internamente, o C# define um modificador chamado *private*.

Abaixo vocês podem observar melhor a lista de Modificadores existentes no C#:

Modificador		   | Funcionamento
-------------	   | -------------
public			   | O acesso não é restrito.
protected	   	   | O acesso é limitado às classes ou tipos derivados daclasse que a variável está.
Internal		   | O acesso é limitado ao conjunto de módulos(assembly) corrente.
protected internal | O acesso é limitado ao conjunto corrente ou tiposderivados da classe recipiente.
private			   | O acesso é limitado à classe que a variável está.
readonly		   | A escrita não é permitida.
