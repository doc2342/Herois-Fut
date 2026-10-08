# Heróis Fut

Protótipo jogável de um jogo de cartas e tabuleiro com heróis e vilões, usando a química do FUT (FIFA Ultimate Team) e um draft de cartas.

Para jogar, abra `index.html` no navegador. É um arquivo único, sem dependências além das fontes do Google Fonts.

## Como funciona

1. **Draft** (9 rodadas, contra a CPU)
   - Rodada 1: escolha um **capitão** entre 4. O capitão dá +1 de química a todas as cartas da mesma facção que estiverem em campo.
   - Rodadas 2 a 9: aparecem 4 cartas e cada jogador leva 1, alternando quem escolhe primeiro.
2. **Escalação**: escolha a formação (2-3-2, 3-2-2 ou 2-2-3) e coloque 7 cartas em campo. As outras 2 ficam como reservas.
3. **Partida** (5 lances): em cada lance você escolhe por qual faixa atacar (esquerda, centro ou direita) e qual faixa reforçar na defesa.

## Química

Cada carta tem **facção**, **origem do poder** e **cidade**. Cartas ligadas no campo comparam esses atributos:

| Ligação | Condição | Valor |
|---|---|---|
| Forte (verde) | 2 ou mais atributos em comum | 2 |
| Fraca (amarela) | 1 atributo em comum | 1 |
| Nenhuma (vermelha) | nada em comum | 0 |
| Conflito | herói ao lado de vilão | −1 |
| Rivalidade | nêmesis lado a lado | 3 |

Anti-heróis nunca geram conflito. A química de cada carta (0 a 3 estrelas) vem da média das suas ligações e soma +1 em ATQ e +1 em DEF por estrela. Fora de posição, a carta perde 1 estrela e leva −2 em ATQ e DEF.

## Lances

- **Ataque na faixa** = ATQ dos atacantes + metade do ATQ dos táticos + 2d6.
- **Defesa na faixa** = 3 de base + DEF dos defensores + metade da DEF dos táticos + 1d6, mais +4 se for a faixa reforçada.
- Sai gol quando o ataque supera a defesa. Empate no fim vai para os pênaltis.
- Dá para fazer até 2 substituições durante a partida.

---

# Bomba Fut

Um "Bomberman de futebol", em `bomba-fut/index.html`. Abra no navegador para jogar.

- A bola faz o papel da bomba: com ela no pé, o chute manda a bola em linha reta. Ela quebra o primeiro cone que encontrar ou deixa tonto o rival que estiver no caminho.
- Sem a bola, o mesmo botão dá um carrinho, que rouba a bola ou derruba um cone. Quem rouba fica protegido por um instante.
- Os cones soltam itens: **Alcance** (a bola vai mais longe), **Velocidade** e **Força** (a bola atravessa cones).
- Vence quem fizer 3 gols ou estiver na frente quando os 2 minutos acabarem. Empate vai para o gol de ouro.
- Controles: jogador 1 usa `WASD` e `Espaço`, jogador 2 usa as setas e `Enter`. Contra a CPU (Fácil, Normal ou Difícil) vale qualquer um. No celular aparecem botões na tela.
