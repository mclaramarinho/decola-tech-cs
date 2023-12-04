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
