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

Fala galera, tudo beleza? Começando então a fase de aprofundamento dos princípios do SOLID, nada mais lógico que começar com a letra _S_.
**Single Responsibility Principle** ou Princípio da Responsabilidade Única diz que
> Uma classe deve ter um, e apenas um, motivo para mudar.

Mas, espera aí, um _motivo para mudar_? O que isso significa? Vamos lá!

### Coesão
Podemos explicar este princípio utilizando uma conceito muito difundido na área de TI, que é a coesão.
A coesão é medida através da número de responsabilidades de uma classe. Quanto mais coesa, menor é seu número de responsabilidades.

Buscamos a alta coesão não só com o objetivo de simplificar o entendimento da classe, mas também de facilitar sua manutenção, já que
se ao alterarmos uma classe com uma responsabilidade bem definida(alta coesão) corremos menor risco de inviabilizar outros serviços
que não tem relação com real problema. 

### Um motivo para mudar
Voltamos então à definição principal do SRP, _uma classe deve ter um, e apenas um, motivo para mudar_. Se fizermos uma correlação entre esta
definição e o conceito de coesão abordado, podemos definir que uma classe tem vários motivos para mudar quando possuir várias responsabilidades, 
ou de forma inversa: uma classe tem um, e apenas um, motivo para mudar, quando possuir apenas uma responsabilidade.

Este conceito é tão importante que me darei o direito de repeti-lo: _Cada responsabilidade de uma classe é um motivo para mudança, deste modo, uma classe deve ter apenas uma responsabilidade_.

Falando de forma prática, imagine a seguinte classe:
``` csharp
public class teste {
    public int Teste { get; set; }
}
```

### Definições
E então, quem são eles e o que significam? Vamos lá:

- **SRP** - **S**ingle **R**esponsibility **P**rinciple ou Princípio da Responsabilidade Única.

> Uma classe deve ter um, e apenas um, motivo para mudar.

- **OCP** - **O**pen/**C**losed **P**rinciple ou Princípio do Aberto/Fechado

> Suas classes devem ser abertas para extensão e fechadas para modificação.

- **LSP** - **L**iskov **S**ubstitution **P**rinciple ou Princípio de Substituição de Liskov

> Classes base devem ser substituíveis pelas classes derivadas.

- **ISP** - **I**nterface **S**egregation **P**rinciple ou Princípio da Segregação de Interface

> Muitas interfaces especializadas são melhores que uma única interface generalizada.

- **DIP** - **D**ependency **I**nversion **P**rinciple ou Princípio da Inversão de Dependência

> Dependa de uma abstração, não de uma implementação.

### E por que esses princípios são importantes?
Ao seguir estes princípios temos vários benefícios, citarei alguns para exemplificar e te animar a querer saber tudo sobre eles:
- Contribui para o entendimento geral do software, facilitando a manutenção.
- Aumenta o poder da reusabilidade.
- Torna o código mais testável.
- Permite a inclusão de novas features de maneira mais simplificada.

E muitos outros benefícios que serão aprendidos ao longo de cada um dos princípios.

### Mas, se é tão bom assim, por que uma quantidade considerável de softwares ainda não o seguem?
O grande desafio fica por conta de que, apesar de relativamente simples, os princípios não são tão fáceis de serem seguidos. Há a 
necessidade dos desenvolvedores sempre pensarem claramente a respeito dos princípios ao realizar qualquer mudança no código. Tudo isso,
acrescido de uma possível pressão que a equipe de desenvolvimento poderia estar sofrendo, seria uma receita típica para causar [dívidas
técnicas](https://en.wikipedia.org/wiki/Technical_debt) ao longo do projeto, mas este é um outro tópico que pretendo abordar no futuro. :)

### Conclusão
Bom, espero que eu tenha sido claro ao apresentar uma visão geral do SOLID e os pontos do porque ele seja de fundamental importância para
qualquer profissional da área de desenvolvimento. Sendo assim, te convido para os próximos posts desta série, onde
abordarei cada um dos princípios de forma isolada. Minha recomendação é que você os aplicasse e treinasse, discutindo
os pontos de maior interesse aqui mesmo no blog, pois garanto que valerá muito a pena!

Qualquer dúvida, crítica, elogio ou sugestão, ficarei extremamente feliz de discutir na seção de comentários logo abaixo. Até a próxima, valeu!