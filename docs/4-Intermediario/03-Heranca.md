# 4.3 Herança
No paradigma orientado a objetos nós temos três conceitos que são pilares, e a herança é um deles.  As vantagens que a herança traz consigo são o reuso e a possibilidade de fazer polimorfismo.
Podemos pensar em uma relação de "Pai" e "Filho", onde o filho HERDA todas as características do pai (atributos e métodos). Vejamos um exemplo:

A seguir, temos uma classe  com nome *Pai* que contém os atributos nome e idade, além do método QuemEuSou.

```
using  System;

namespace  testes
{
	class Pai
	{

		public  string Nome { get; set; }

		public  int Idade { get; set; }
		
		public  Pai(){}
		
		public  Pai(string nome, int idade)
		{
			Nome = nome;
			Idade = idade;
		}
		
		public  void  QuemEuSou()
		{
			Console.WriteLine("Meu nome é: "  + Nome +  "e eu tenho: "  + Idade +  "anos.");
		}
	}
}
```

Agora, vejamos a classe com nome *Filho*:

```
using  System;

namespace  testes
{
	class Filho : Pai
	{
		public  double Altura { get; set; }
		
		public  Filho() { }
		
		public  Filho(string nome, int idade, double altura) : base (nome, idade)
		{

			Nome = nome;
			Idade = idade;
			Altura = altura;
		}
	}
}
```

Percebe-se que há uma mudança na sintaxe da classe Filho, primeiro nós temos uma ocorrência de  um ***":"*** logo após o nome da classe Filho, e na frente temos ***Pai***, além disso, no construtor com argumentos da classe Filho, nós temos um ***: base (nome, idade)*** . O que seria isso?
A ocorrência de ***": Pai"*** após o nome da classe Filho, significa que ele está *Herdando* tudo da classe Pai,  incluindo seus atributos e métodos. Já o ***: base (nome, idade)*** diz que ele está repassando os parâmetros *nome e idade* para o construtor da classe Pai. 
Nesse exemplo em específico, eu fiz com que a classe Filho tivesse um atributo a mais: o atributo *Altura*, que 	não há na classe Pai. Então, constatamos aqui o reaproveitamento do código, visto que nós não declaramos os atributos *Nome e Idade* na classe Filho.

Vejamos a instanciação:

```
using  System;

namespace  testes
{
	class Program
	{
		static  void  Main(string[] args)
		{
			//Instanciando um objeto da classe Filho
			Filho filho1 =  new  Filho("Ash", 25, 1.70);
			//Chamando o método QuemEuSou da classe Pai através do objeto da classe Filho
			filho1.QuemEuSou();
		}
	}
}
```

No código acima, nós instanciamos um objeto da classe *Filho* passando os parâmetros *nome, idade e altura* mesmo *nome e idade* não tendo sido declarado na classe *Filho* , isso se dá por causa do reaproveitamento de código proveniente da Classe *Pai*. Além disso conseguimos chamar o método QuemEuSou através desse objeto.

## 

No código abaixo, utilizaremos como exemplo uma classe pai chamada "Conta" e uma classe Filho chamada "ContaCorrente". Como vimos, a classe filho herda todos os seus atributos e métodos da classe pai.

```
using  System;

namespace  testes
{
	class Conta
	{
		public  int NumeroConta { get; set; }
		
		public  double Saldo { get; set; }

		public  Conta () {}
		
		public  Conta (int numeroConta, double saldo)
		{
			NumeroConta = numeroConta;
			Saldo = saldo;
		}

		public  void  Sacar(double valor)
		{
			Saldo = Saldo - valor;
		}
	}

	//Aqui a classe ContaCorrente herda tudo da classe Conta
	class ContaCorrente : Conta
	{
		public  string TipoConta { get; set; }
		
		public  ContaCorrente () {}
		
		public  ContaCorrente (int numeroConta, double saldo, string tipoConta) : base(numeroConta, saldo)
		{

			NumeroConta = numeroConta;
			TipoConta = tipoConta;
		}
	}

	class Program
	{
		static  void  Main(string[] args)
		{
			//Instanciando um objeto do tipo "ContaCorrente", que herda do seu pai "Conta" o atributo NumeroConta e Saldo, além do método saque
			ContaCorrente cc =  new  ContaCorrente(12345, 3000.0, "Conta Corrente");
			cc.Sacar(200.0);
		}
	}
}
```

Como podemos ver no exemplo anterior, instanciamos um objeto chamado *cc* através da classe *ContaCorrente*  onde, através desse objeto, nós chamamos o método *Sacar* que é herdado do pai.
