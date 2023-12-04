## ABSTRAÇÃO

--


## ENCAPSULAMENTO

```cs

private string nome;

public string Nome{
  get => nome;

  set{
    nome = value;
  }
}

```


## HERANÇA

Exemplo:

Aluno herda Pessoa

```cs

public class Pessoa{
  //bloco de codigo
}

public class Aluno : Pessoa{
  //bloco de codigo
}

```


## POLIMORFISMO

Exemplo:
Aluno herda Pessoa

Pessoa tem um método Apresentar() mais genérico

Aluno precisa de um método Apresentar() mais específico

```cs

public class Pessoa{
  //bloco de codigo
  public virtual string Apresentar(){
    return $"Meu nome é {nome}, e eu tenho {idade} anos";
  }
}

public class Aluno : Pessoa{
  //bloco de codigo
  public override string Apresentar(){
    return $"Meu nome é {nome}, e eu tenho {idade} anos. Minha nota é {nota}.";
  }
}

```

## CLASSES ABSTRATAS

São um modelo para ser herdado por uma classe filha

Elas não podem ser instanciadas

Conta --> ContaCorrente

Conta --> ContaPoupanca

Tudo que Conta possui é possuído pelas suas especializações.

Apenas suas especializações podem ser instanciadas.

```cs

public abstract class Conta{
  // bloco de codigo
}

```

## MÉTODOS ABSTRATOS

Servem de modelo para ser herdado pelas classes filhas

Na classe em que ele aparece como abstrato --> não possui corpo, apenas a assinatura

A classe que herda é obrigada a instanciar um método com a assinatura do método abstrato.

```cs

public abstract class Conta{
  public abstract void Creditar();
}

```


## CONSTRUTOR POR HERANÇA

Pessoa --> deve ser instanciada sempre com um nome

```cs

public class Pessoa{
  public Pessoa(string nome){
    Nome = nome;
  }
}

```

Portanto, todas as classes que herdarem Pessoa, devem mandar o nome, obrigatoriamente, para a classe Pai.

```cs

public class Aluno : Pessoa{
  public Aluno (string nome) : base(nome){
    //bloco de codigo
  }
}

```


## CLASSE SELADA

Impede que outras classes herdem a classe selada.

```cs

public sealed class Aluno : Pessoa{
  public Aluno (string nome) : base(nome){
    //bloco de codigo
  }
}

```

## MÉTODO SELADO

Impede que outras classes sobrescrevam esse método selado.

```cs

public sealed class Aluno : Pessoa{
  public Aluno (string nome) : base(nome){
    //bloco de codigo
  }

  public sealed string Apresentar (){
    //bloco de codigo
  }
}

```

## INTERFACES

Classe-contrato que deve ser implementada por outra classe

Toda classe que implementar a interface, deve implementar os métodos presentes na interface.

Uma classe pode implementar várias interfaces

Uma classe não pode herdar mais de uma classe


Interface:

```cs

public interface ICalculadora{

  double Somar(double num1, double num2);
  double Subtrair(double num1, double num2);

```

Implementando a interface:

```cs

public interface CalculadoraSimples : ICalculadora{
  
  public double Somar(double num1, double num2){
    //corpo do metodo
  }
  public double Subtrair(double num1, double num2){
    //corpo do metodo
  }

```

Instanciando uma classe que implementa a interface:

```cs

CalculadoraSimples cs = new CalculadoraSimples();
//or
ICalculadora cs1 = new CalculadoraSimples();

```

Método padrão na interface:

Não precisa ser implementado na classe que implementa interface.

```cs

public interface ICalculadora{

  double Somar(double num1, double num2);
  double Subtrair(double num1, double num2);
  double Dividir(double num1, double num2){
    return num1 / num2;
  }

```
