# Análise: reel "Thomas Edison wasn't a genius at first" (tipografia cinética sobre foto de arquivo)

**O que é.** Reel vertical em inglês sobre o Thomas Edison: 17,46 s, 720×1280, 24 qps, H.264 + AAC estéreo. Veio
como arquivo do usuário, baixado do Pinterest pelo pindown.io (`ridavsual_pindown.io_…`). O perfil "ridavsual" é a
pista do autor, **não confirmada**. Não tem link nem licença declarada: tratar como todos os direitos reservados. Não
entra no `catalogo.json` até termos o link, porque o catálogo exige `--url` e `--licenca`. O vídeo não fica no
repositório. A medição bruta está em `edison-tipografia-cinetica_medicao.json`.

**Como medi.** Os 419 quadros em 360×640. Para cada um: a diferença com o anterior, a nitidez (variância do
laplaciano), a transformação afim entre vizinhos (ECC) e as regiões que mudam (componentes conexos da diferença).
Também fiz folhas de contato a 4 qps e sequências a 24 qps em cada transição. No áudio: espectrograma, ataques,
energia por banda, LUFS e F0. **A fala não foi transcrita**: o modelo do Whisper não baixou, porque o proxy daquela
sessão bloqueia o Hugging Face. O texto abaixo é o que aparece na tela. A sincronia entre fala e palavra vem dos
ataques do áudio.

## Resumo em números
| medida | valor |
| --- | --- |
| planos | **9 em 17,5 s**; mediana 2,1 s (mín. 0,85, máx. 3,3) |
| eventos de texto ou desenho | ~32, **um a cada ~0,5 s** |
| passagens com desfoque | **6 de 8** |
| congelado (diferença ~0) | 6,7–7,25 · 10,2–10,9 ("times" entra no meio) · 12,9–13,7 · 16,96–17,46 → ≈2,5 s (14%) |
| cor | monocromático (saturação média 0,4 a 7,8 de 255); a única cor é uma pintura em 15,4–15,9 s |
| grão, boil, tremor | **nenhum**: o quadro parado repete idêntico. É digital e liso |
| cadência | 24 qps contínuos, sem degrau |
| voz | contínua; −18,2 LUFS integrado; faixa de volume (LRA) 1,6 LU, muito comprimida; F0 mediana 210 Hz |
| grave de transição | a banda de 20 a 150 Hz sobe ~25 dB em 7 passagens, ou seja, um "whoosh" grave em cada desfoque |

## A história (o texto na tela, que segue a fala)
"Thomas Edison / wasn't a genius at first. / He was kicked out of school / and told he couldn't learn. / He failed over
1000 times. / But he said: / I didn't fail.. / I found 1000 ways that didn't work."

Estrutura: **nome → negação → dois golpes → número → virada ("but") → citação → prova visual (carrossel)**. O gancho
(nome + negação) se fecha em 1,1 s.

## Os planos (o molde da montagem)
| # | tempo (s) | texto e quando entra | imagem | movimento | saída |
| --- | --- | --- | --- | --- | --- |
| 1 | 0,00–1,08 | "Thomas Edison" (fina, fade em 0,08–0,25) | Edison com a lâmpada, recortado sobre o cartão cinza; duas lâmpadas recortadas (a de cima desce, a de baixo sobe) | o cartão começa em ~133% e assenta em 100% em ~0,6 s; **a foto sobe por dentro do cartão** (0–0,42) | desfoque em 2 quadros, corte |
| 2 | 1,08–3,79 | wasn't 1,21 · a genius 1,58 (caixas de marca-texto) · at 2,25 · first 2,50 | close do mesmo Edison, **foto viva** (a cabeça e os olhos mexem) | entra desfocado e foca em ~0,8 s; câmera ×1,04 e −29 px (em 720) em 2,5 s, para a esquerda e freando | o texto apaga e desfoca em 3,3–3,75; corte |
| 3 | 3,79–5,62 | He was 3,83 (desliza da direita, com sombra) · kicked 4,21 (sobe) · out 4,50 · of school 4,83 (cortina da esquerda para a direita) | Edison menino recortado sobre um disco cinza com sombra | a foto desliza para a esquerda e freia (−45 px, ×1,03); uma linha fina diagonal se desenha (4,8–5,2) | **chicote para baixo** com borrão em 5,25–5,58 (~30 px por quadro em 720); corte |
| 4 | 5,62–7,88 | and told 5,79 (embaixo, com seta curva) · he couldn't learn 6,29 (no alto, com seta curva) | retrato sépia autografado, no cartão | o cartão entra desfocado e foca em 0,2 s; **a foto desliza da direita dentro do cartão** (5,7–6,6); **congela** em 6,7–7,25 | linhas pretas se desenham; o cartão sobe e cresce (7,3–7,8); desfoque; corte |
| 5 | 7,88–8,96 | he failed, **letra a letra** (7,92–8,42), com elipse e risco feitos à mão | Edison idoso sentado; o cartão começa pequeno e vazio | **a foto sobe por dentro do cartão** enquanto ele cresce (7,96–8,5) | desfoque instantâneo em 8,75, 0,2 s borrado; corte com **soco de zoom** (~×1,5) |
| 6 | 8,96–11,25 | over (já está) · 1000 9,21 (fina) · times 10,33 (fina, branca) | o mesmo Edison mais perto; **foto viva** sutil nas mãos e no rosto | quase parado; congela em 10,2–10,9 | desfoque em 10,92–11,2; corte |
| 7 | 11,25–12,10 | but he said, **digitado** em 11,29–11,92 (~1 letra por quadro), com cursor piscando | sem foto: "BUT" gigante e fantasma (letras de ~650 px, cinza claro translúcido) e o manuscrito do Edison | parado | o cartão do plano 8 entra por cima |
| 8 | 12,10–14,17 | I didn't fail.., digitado em 12,75–12,9 (fina, branca) | Edison com a lâmpada, **recorte sem fundo**, duas fitas pretas e a assinatura | **o cartão abre na horizontal** a partir de um filete (12,12–12,33); a foto sobe dentro dele (12,33–12,6); o fundo do cartão some e ficam o recorte e as fitas (12,6–12,7); congela em 12,9–13,7 | **desfoque de foco** sem movimento (13,7–14,1); corte |
| 9 | 14,17–17,46 | found 14,33 · I ~14,9 · 1000 15,13 · ways that 15,75 · didn't work 16,5–16,75 | moldura com duas fitas (600×745 em 720) e a assinatura fixa embaixo; **carrossel de 6 fotos**, uma colorida | **a foto nova empurra de baixo para cima** em 0,33–0,38 s, acelerando; trocas em 14,71 · 15,29 · 15,63 · 16,17 · 16,58 (0,33 a 0,58 s entre elas, mais rápidas no fim) | congela 0,5 s no fim |

## As peças (o kit visual)
1. **Fundo.** Uma carta datilografada de 1922 para "Mr. Edison", com anotações manuscritas por cima, em P&B e com
   contraste baixo (~15%). Por cima vai um **degradê vertical** de `#BEBEBE` no alto até `#777774` em y 1250
   (`#565553` na base). Cada plano mostra um trecho diferente da carta, sem deriva própria.
2. **Cartão.** Um retângulo sem borda com degradê vertical cinza (~`#5E5E5B` no alto, ~`#A5A5A2` embaixo) e sombra
   grande e macia (desfoque ~40 px, deslocada ~20 px para baixo, ~50%). Ocupa ~75% da largura.
3. **Recorte que vaza.** A pessoa, sem fundo, fica na frente do cartão com a cabeça **passando da borda de cima**. No
   plano 8 o cartão some e fica só o recorte com as fitas.
4. **Disco.** Um círculo cinza com sombra atrás do recorte, no lugar do cartão (plano 3).
5. **Fita.** Duas tiras pretas foscas a ~45° nos cantos de cima (planos 8 e 9).
6. **Assinatura do Edison**, em preto, na base da foto (planos 8 e 9).
7. **Lâmpadas recortadas**, penduradas, que entram por cima e por baixo (plano 1).
8. **Desenho à mão.** Setas curvas com ponta (traço de ~4 px, preto ou branco), a elipse em volta de "he failed", um
   risco e linhas finas que cruzam a tela na diagonal. Tudo se desenha: o traço cresce.
9. **Palavra fantasma.** "BUT" em corpo gigante, cinza claro translúcido, como fundo da virada.

## Tipografia: quatro famílias, e o peso marca a ênfase
| papel | palavras | aparência | substituta livre |
| --- | --- | --- | --- |
| nome e sussurro | Thomas Edison, 1000, times, I didn't fail.., I found | fina humanista, cinza ou branca | Inter Light (no plugin) |
| a palavra que pesa | wasn't, over | sem serifa muito pesada | Archivo Black (no plugin) |
| o golpe | first, He was, of school, didn't work | condensada pesada, com sombra ou degradê | Archivo Narrow Bold (no plugin) ou Anton |
| a frase falada | he couldn't learn, he failed, and told, ways that, but he said | arredondada em negrito | Nunito ExtraBold (OFL; não está no plugin) |
| marca-texto | a genius | regular, cada palavra numa caixa cinza (`#9A9A9A`) | Inter Regular |

As regras do texto:
- Cada frase mistura 2 ou 3 pesos e tamanhos. As palavras se empilham e se encaixam numa "escada", em vez de formar
  uma linha só.
- A cor é cinza-escuro (~`#3E3E3E`) sobre o fundo claro e branca sobre a foto escura.
- O corpo é grande: a palavra-golpe tem ~90 a 120 px de altura em 720 (≈ 130 a 180 px em 1080).

## O vocabulário de movimento
| mecânica | duração | curva | planos |
| --- | --- | --- | --- |
| a foto sobe por dentro do cartão (máscara) | 0,4–0,55 s | sai rápida e assenta | 1, 5, 8 |
| a foto desliza de lado dentro do cartão | ~0,9 s | sai rápida e freia | 4 |
| o cartão abre na horizontal, de filete a cheio | 0,25 s | — | 8 |
| entrada que assenta (133% → 100%) | ~0,6 s | sai rápida e freia | 1 |
| foco que chega (o corte entra desfocado) | 0,2–0,8 s | sai rápida e freia | 2, 4, 5 |
| saída por desfoque | 0,1–0,4 s; às vezes segura 0,2 s borrado | acelera | 6 das 8 passagens |
| chicote para baixo com borrão | ~0,35 s | acelera | 3 → 4 |
| soco de zoom no corte (~×1,5) | 1 quadro | — | 5 → 6 |
| deriva lenta da câmera | ×1,03–1,04 e 30–45 px (em 720) por plano | freia | 2, 3 |
| congelar | 0,5–0,8 s | — | 4 vezes, sempre depois que a frase fecha |
| foto viva (imagem animada por IA) | o plano todo | — | 2, 6 |
| carrossel: a foto nova empurra a velha de baixo para cima | 0,33–0,38 s | acelera | 9 |

O texto entra de cinco jeitos:
- fade com uma subida curta (20–60 px, 0,15–0,25 s);
- deslizando de lado;
- por cortina da esquerda para a direita;
- letra a letra (~1 letra por quadro);
- digitado com cursor.

Entra uma palavra nova a cada 0,25 a 0,6 s. O texto sai junto com o desfoque do plano.

## Som
- **Voz** narrada o tempo todo, a −18,2 LUFS, com faixa de volume de 1,6 LU (compressão forte). A F0 mediana é
  210 Hz (p10 148, p90 302), ou seja, uma voz aguda. Talvez seja sintetizada (hipótese).
- **Música:** nenhuma audível. Entre as frases o nível cai para −33 a −37 dB, ~20 dB abaixo da voz. Se houver leito,
  é muito baixo (não confirmado).
- **Grave de transição:** a banda de 20 a 150 Hz sobe ~25 dB em 1,0 · 3,75 · 5,5 · 7,75 · 11,0 · 12,25 · 14,0 s,
  começando ~0,1 s antes do corte. É um whoosh grave em cada desfoque. As trocas do carrossel não têm grave, só um
  brilho agudo leve.

## Como replicar no plugin
A base é a skill `motion-arquivo`. Ela é narrada, transforma cada palavra dita num evento e mede referências com a
mesma régua. Ela já tem:
- `pouso`: o corte que entra desfocado e foca;
- desfoque de saída;
- `foto_recorte` com máscara;
- frases que entram desfocadas;
- digitação letra a letra;
- `planos_galeria`.

O que muda é a "pele":

| peça | o que já existe | o que falta ou precisa de ajuste |
| --- | --- | --- |
| cadência | `cadencia` 10 ou 15 e `trechos_30qps` | 30 qps contínuos, sem grão, sem boil e sem linhas de CRT |
| fundo | papel e documento digitado | carta de arquivo em P&B com o degradê cinza vertical |
| cartão e recorte que vaza | `foto_recorte` (máscara pelo Vision, só no macOS) | cartão com degradê e sombra grande; a cabeça passando da borda; a foto que sobe ou desliza **dentro** da máscara do cartão |
| transições | `pouso` e desfoque de saída | chicote para baixo, soco de zoom e cartão que abre na horizontal |
| tipografia | Inter, Archivo Black e Archivo Narrow (`motion-vox/fontes`) | uma arredondada (Nunito, OFL) e a regra da escada de pesos |
| desenho à mão | `Traco` e `circulo` (motor de colagem), `laco` e `sublinhado` (galeria) | seta curva com ponta e linhas finas que cruzam a tela |
| carrossel com fita | `PC.fita` e `PC.cartao` | troca que empurra de baixo para cima, acelerando |
| foto viva | — | **não replicar com IA**: o `REGRAS.md` proíbe gerar ou recriar o rosto de uma pessoa real nomeada. Substituir por paralaxe 2,5D (recorte na frente, fundo atrás, empurrão lento) |
| som | sons sintetizados (`grave`, `ar`) | whoosh grave em cada transição por desfoque |

**Assets.** Retratos do Edison em domínio público: fotos publicadas antes de 1929 nos EUA, em acervos como a Library
of Congress e o Edison Papers. A licença de cada uma precisa ser conferida. A pintura colorida do plano 9 parece o
retrato de A. A. Anderson (1890), mas a identificação **não está confirmada**. Também é preciso uma carta de arquivo
com licença e a voz, gravada ou sintetizada.

**Passos:**
1. Roteiro de 8 a 10 frases curtas, na ordem nome → negação → golpes → número → "but" → citação → carrossel.
2. Voz e batidas (fase 1 da `motion-arquivo`): cada palavra com o seu tempo.
3. Um plano por batida, usando a tabela de planos acima como molde (9 planos de ~2 s).
4. Assets reais e máscaras.
5. Cenas e render. Depois, comparar com esta medição (cortes, nitidez, congelados) usando `ferramentas/comparar.py`.

## Cuidados de fato e riscos
- "Kicked out of school" e "1000 ways that didn't work" são histórias populares sobre o Edison. A citação circula com
  1.000 e com 10.000, e a fonte original é fraca. Pela regra das duas fontes, reescrever só com o que se sustenta.
- Rosto real: só fotos reais licenciadas, sem animar o rosto por IA (ver "foto viva" acima).
- O vídeo é de terceiros: estudar a gramática, não copiar a montagem quadro a quadro com as mesmas imagens.
