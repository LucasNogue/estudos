# 3 - Comportamentos de classe

**FUNÇÕES OU MÉTODOS**

Funções ou métodos são ações que os objetos instanciados da classe podem executar.

A função retorna um valor já o método não, mas tanto função quanto método são

nomenclaturas corretas de se utilizar nessas ocasiões.

**REGRAS**

- Todo nome de método começa com a letra maiúscula
- Todo método representa uma ação
- Utilizar verbos no infinitivo para a nomenclatura

**Exemplo:**

```csharp
public class ContaCorrente
{
	public string titular;
    public int agencia;
    public int numero;
    public double saldo = 200;
		
		
	//Método Sacar da classe ContaCorrente
	public bool Sacar(double valor)
	{
		if(this.saldo <valor)
		{
			return false;
		}
		else
		{
			this.saldo-= valor;
			return true;
		}
	}		
}
```

**MÉTODO SEM RETORNO (MÉTODO)**

Declaramos um método sem retorno colocando o seu tipo como **void**

**Exemplo:**

```csharp
public Class ContaCorrente
{
	public string titular;
    public int agencia;
    public int numero;
    public double saldo = 200;
		
		
	//Método Sacar da classe ContaCorrente
	public void Depositar(double valor)
	{
		this.saldo+=valor;
	}
}
```

**MÉTODOS COM MUITOS ARGUMENTOS**

```csharp

//A variável contaDestino é do tipo ContaCorrente com isso temos acesso aos objetos 
//criados por essa classe
public bool Transferir(double valor, ContaCorrente contaDestino)
{
	if (this.saldo <valor)
	{
		return false;		
	}
	else
	{
		contaDestino.Depositar(valor);
		this.saldo-=valor;
		return true;
	}
}
```

**BOA PRÁTICA DE PROGRAMAÇÃO COM IF**

Como o código com  **if** termina após o return não é necessário utilizar um **else**

**Exemplo:**

```csharp

//A variável contaDestino é do tipo ContaCorrente com isso temos acesso aos objetos 
//criados por essa classe
public bool Transferir(double valor, ContaCorrente contaDestino)
{
		//Caso a condição do if esteja correta o código irá parar no **return false**
		if (this.saldo <valor)
		{
			return false;		
		}
		//Se a condição do **if** não estiver correta o bloco de código abaixo será executado
		contaDestino.Depositar(valor);
		this.saldo-=valor;
		return true;
		
}
```