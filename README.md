# caua1f

Lista de Exercícios: CSS Flexbox (parte 1)

Disciplina: Desenvolvimento Web I

Parte A: Múltipla escolha
1) Resposta: b

O display: flex é aplicado no contêiner, que é o pai. Os filhos diretos dele viram itens flex automaticamente.

2) Resposta: c

O valor padrão do flex-direction é row, que coloca os itens em linha, lado a lado.

3) Resposta: b

Com row, o eixo principal é horizontal, da esquerda para a direita.

4) Resposta: b

O justify-content sempre age no eixo principal. Com column, o eixo principal passa a ser o vertical.

5) Resposta: c

O align-items alinha os itens no eixo cruzado.

6) Resposta: c

O padrão do align-items é stretch, que estica os itens para ocupar toda a altura (o eixo cruzado) da linha.

7) Resposta: b

O space-between coloca o primeiro item no início, o último no fim e divide o espaço restante só entre eles.

8) Resposta: b

O flex-wrap: wrap permite que os itens quebrem para a linha seguinte quando não cabem.

9) Resposta: b

O align-content distribui as linhas dentro do contêiner, então só faz diferença quando há flex-wrap: wrap (ou wrap-reverse) e mais de uma linha.

10) Resposta: b

O gap cria espaço apenas entre os itens, sem deixar espaço extra nas bordas externas do contêiner, ao contrário da margem.

11) Resposta: c

O row-reverse inverte a ordem visual no eixo horizontal, e os itens ficam da direita para a esquerda.

12) Resposta: a

Para centralizar nos dois sentidos, usa-se justify-content: center (eixo principal) e align-items: center (eixo cruzado).

Parte B: Dissertativas e análise de código
13) Contêiner flex x item flex

O contêiner flex é o elemento pai, que é quem recebe o display: flex. Os itens flex são os filhos que estão diretamente dentro dele. Depois que o pai vira flex, esses filhos diretos passam a seguir as regras do flexbox (ficam em linha, dá para alinhar, espaçar etc.). Os elementos que estão dentro dos filhos (netos) não são afetados.

14) Análise do código

Com flex-direction: column os itens A, B e C ficam um embaixo do outro. Como agora o eixo principal é o vertical, o justify-content: center junta os três no centro da altura de 300px, com a mesma sobra em cima e embaixo. Na horizontal, o align-items está no padrão (stretch), então cada item ocupa a largura inteira da caixa.

15) Sem flex-direction: column e com width: 300px

Sem o column, o flex-direction volta para row e os itens ficam lado a lado. Como o flex-wrap padrão é nowrap, eles não pulam para outra linha. Se forem largos demais, primeiro tentam encolher e, se mesmo assim não couberem, vazam para fora da caixa de 300px.

16) justify-content x align-items
(a) Em row: o justify-content age no eixo horizontal (principal) e o align-items age no eixo vertical (cruzado).
(b) Em column: os eixos se invertem. O justify-content passa a agir na vertical e o align-items passa a agir na horizontal.
17) Por que o align-content: center não faz efeito com nowrap

O align-content serve para distribuir as linhas dentro do contêiner. Com nowrap só existe uma linha, então não há o que distribuir. Para ele funcionar é preciso flex-wrap: wrap (ou wrap-reverse), ter mais de uma linha e o contêiner ter altura maior do que o conteúdo.

18) gap: 16px x margin-right: 16px

O gap cria o espaço apenas entre os itens. A margin-right é aplicada em cada item, então o último também fica com 16px sobrando na direita. Esse é o problema típico: é preciso criar uma exceção, como :last-child { margin-right: 0; }. Além disso, a margem fica mais trabalhosa quando os itens quebram de linha.
