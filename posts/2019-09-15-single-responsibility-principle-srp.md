---
title: Single Responsibility Principle
description: A importância da alta coesão e baixo acoplamento fundamentado neste
  princípio do SOLID.
date: 2019-09-15T11:45:00.000Z
category: solid
background: "#cf4647"
image: /assets/img/desert.jpg
thumbnail: assets/img/Varm.png
---
Fala galera, tudo beleza? Começando então a fase de aprofundamento dos princípios do SOLID, nada mais lógico que começar com a letra *S*. **Single Responsibility Principle** ou Princípio da Responsabilidade Única diz que

> Uma classe deve ter um, e apenas um, motivo para mudar.

Mas, espera aí, um *motivo para mudar*? O que isso significa? Vamos lá!

### Coesão

Podemos explicar este princípio utilizando um conceito muito difundido na área de TI, que é a coesão. A coesão é medida através da número de responsabilidades de uma classe. Quanto mais coesa, menor é seu número de responsabilidades.

Buscamos a alta coesão não só com o objetivo de simplificar o entendimento da classe, mas também de facilitar sua manutenção, já que se ao alterarmos uma classe com uma responsabilidade bem definida(alta coesão) corremos menor risco de inviabilizar outros serviços que não tem relação com real problema. 

### Um motivo para mudar

Voltamos então à definição principal do SRP, *uma classe deve ter um, e apenas um, motivo para mudar*. Se fizermos uma correlação entre esta definição e o conceito de coesão abordado, podemos definir que uma classe tem vários motivos para mudar quando possuir várias responsabilidades, 
ou de forma inversa: uma classe tem um, e apenas um, motivo para mudar, quando possuir apenas uma responsabilidade.

Este conceito é tão importante que me darei o direito de repeti-lo: *Cada responsabilidade de uma classe é um motivo para mudança, deste modo, uma classe deve ter apenas uma responsabilidade*.

Falando de forma prática, pense na seguinte classe:

```csharp
public class Pedido
{
    public decimal CalcularValorTotal() { }

    public void EmitirComprovante() { }

    public void GerarNotaFiscal() { }
}
```

Cada um dos seus métodos possuem responsabilidades distintas. O método _CalcularValorTotal()_ possui total sinergia com o que a Classe se propõe, não é mesmo? Não causa nenhuma estranheza vê-lo ali, e criar esse senso de _estranheza_ é uma das coisas mais importantes para esse princípio (já já falarei mais a respeito).

Nos outros dois métodos, apesar de ter uma certa ligação com _pedidos_, cada um possui um propósito que não cabe a Classe. Pense que, no caso do método _EmitirComprovante()_, cada vez que a regra de comprovante mudar teremos que mexer também na classe de Pedidos. Somado isso, mais as mudanças que teremos que realizar caso regras referentes a pedidos se alterem, já temos no mínimo dois motivos para mudar (opa!).
