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
