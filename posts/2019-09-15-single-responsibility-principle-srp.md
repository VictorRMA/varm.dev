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

Agora, se quando bateu os olhos na classe, mais especificamente no último método _GerarNotaFiscal_() e aquela sensação de estranheza subiu no seu coração, você está no caminho certo!

### Cultive a sensação de estranheza (aka. sensor aranha)

Parece meio engraçado, mas é pura realidade. No mundo real, com implementações que de tão complexas fogem de qualquer exemplo, às vezes se torna muito complicado saber se determinada implementação está no local que deveria. Mas, com mais e mais experiência esses casos vão ficando cada vez menores e um senso de percepção começa a surgir, que chamo de _senso de estranheza_. Me darei o direito de criar uma tangente a seguir para exemplificar o que estou querendo dizer com isso.

Durante minha adolescência, tive uma professora de português que me ensinou o seguinte truque: _Caso tenha dúvidas sobre a escrita de uma palavra, escreva das formas com que pensa ser, você vai descobrir qual é o certo só de olhar (na maioria das vezes rsrs)_. O fato é, pensar em escrever uma palavra, como "desli*z*ar" ou "desli*s*ar", pode causar certo problema para alguns, mas quando vemos a palavra "desli*s*ar" escrita, imediatamente nos vem aquela sensação de estranheza, como se algo não estivesse certo. E o melhor de tudo é que geralmente isso se confirma :).

Voltando para o mundo do desenvolvimento, essa sensação de estranheza é muito importante e vai ficando mais forte e assertiva conforme nossa bagagem vai aumentando. Às vezes não sabemos o porque, ou até como resolver, mas sabemos que algo não está certo. Quem nunca?

### Conclusão

Como dito, o SRP é um dos princípios do SOLID mais simples de entender, porém, as aplicações vão de casos simples como o do exemplo demonstrado, até casos complexos onde não se torna trivial a detecção e ajuste. Lembre-se: ao se detectar motivos distintos de se alterar uma mesma classe, uma oportunidade de refatoração muito importante pode estar surgindo aí!

Qualquer crítica, dúvida, elogio ou sugestão, ficarei extremamente feliz de discutir na seção de comentários logo abaixo. Até a próxima, valeu!