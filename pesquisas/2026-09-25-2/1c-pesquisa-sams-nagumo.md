# Pesquisa Sam's Club e Nagumo: 25/09/2026 (2ª compra), feita em 26/09/2026

Agente: pesquisador. Mercados: **Sam's Club** (www.samsclub.com.br) e **Nagumo** (www.nagumo.com.br), incluídos pelo usuário em 26/09/2026 (ver `0-lista.md`, "Novos mercados").
Consulta: 26/09/2026, das 12h50 às 13h09 (horário de Brasília).
Nenhum CEP digitado, nenhum login, nada adicionado ao carrinho, nenhum termo ou aviso de cookies aceito. Abri uma aba nova no Chrome (e fechei no fim); as abas do Carrefour, Atacadão e Pão de Açúcar não foram tocadas.

## Lista pesquisada (itens aprovados)

| Código | Item |
|---|---|
| I01 | Fermento químico em pó Dr. Oetker 100 g (sachê ou pote; anotar qual) |
| I02 | Margarina Doriana com sal 500 g |
| I03 | Coco ralado seco (desidratado) Sococo 100 g |
| I04 | Sabão líquido para roupas Omo Puro Cuidado 3 L |
| I05 | Sabão em pó Omo Lavagem Perfeita 2,2 kg (ou 2,4 kg) |

## Como foi pesquisado
- **Sam's Club:** site VTEX. Busquei pela API pública de catálogo do próprio site (`/api/catalog_system/pub/products/search`) e abri no Chrome as páginas de I02 e I03 para conferir preço e botão "Adicionar ao Carrinho". Os links antigos (`...-EAN/p`) redirecionam para `/produto/...-código`; registro os dois.
- **Nagumo:** site Salesforce Commerce Cloud. A leitura automática não traz os produtos (carregam por script), então li o HTML da busca e das páginas de produto (dados embutidos: preço, "available", estoque da loja atual) e conferi no Chrome as páginas de I01, I02, I03, I04 e I05. Os preços do Chrome e da leitura automática foram iguais em todos.
- "Preço comparável" = preço ÷ peso (kg) ou volume (L).

---

## Condições dos sites

### Sam's Club
| Ponto | O que foi visto | Fonte |
|---|---|---|
| Vende online com entrega? | Sim, site com "Adicionar ao Carrinho" e política de entregas | páginas de produto; https://www.samsclub.com.br/institucional/politica-de-entregas |
| Exige ser sócio? | **Sim.** O blog oficial diz que "somente sócios ativos" podem comprar, nas lojas, no site ou no app. Anuidade: R$ 95 (Sócio Club) ou R$ 175 (Sócio Plus, com frete grátis nas compras online) | https://www.samsclub.com.br/blog/sams-club/quem-pode-comprar-no-sams-club-veja-regras-e-vantagens/ (publicado em 10/09/2025) |
| CEP/login para ver preço? | **Não.** Preço e botão aparecem sem CEP e sem login. O cabeçalho mostra "Insira seu CEP e veja produtos na sua região" (sortimento/estoque pode mudar com o CEP) | Chrome |
| Área de entrega | Segundo a política de entregas (lida por resumo automático, não conferida no navegador): cerca de 5 km de um endereço de referência na Barra Funda, São Paulo | politica-de-entregas |
| Pedido mínimo / frete | **Não confirmado.** A política diz que "valores de pedido mínimo podem variar". Uma busca na web citou mínimo de R$ 150 e frete de R$ 24,90, mas não achei isso em página oficial | — |
| Observação | O título das páginas termina em "- Carrefour" (o Sam's Club Brasil é do Grupo Carrefour) | Chrome |

### Nagumo
| Ponto | O que foi visto | Fonte |
|---|---|---|
| Vende online com entrega? | Sim: entrega e "Retirada" na loja. Rodapé: "Pagamento Online / Pagamento na entrega" | site; https://www.nagumo.com.br/termos-de-uso.html |
| Exige cadastro/login? | **Para comprar, sim.** O menu do carrinho mostra "Entre para continuar sua compra", e os termos pedem que o cliente preencha o cadastro. **Para ver preço, não.** | Chrome; termos de uso |
| CEP para ver preço? | Não. Os preços aparecem por **loja**. No Chrome a sessão já estava em "Retirada, Loja 026-STO AND2" (definido antes; **não alterei**). A leitura sem sessão mostrou os mesmos preços | Chrome |
| Frete | Calculado pelo CEP no pedido ("o custo do frete será calculado automaticamente") | termos de uso |
| Pedido mínimo | Não informado nos termos. Uma busca na web citou cupom de frete/retirada grátis acima de R$ 99 e "frete grátis na primeira compra", mas **não confirmei** em página oficial | — |
| Preço "Oferta/Preço baixou" | Alguns itens mostram "De R$ X por R$ Y" na página, sem login. Nos dados da página, esse preço vem com o selo **"meunagumo.png"** (programa Meu Nagumo). **Não confirmado** se esse preço exige cadastro no Meu Nagumo. Os termos lidos não falam em preço exclusivo | páginas de produto |
| Observação | O mini-carrinho da sessão do Chrome já tinha 2 itens que não são desta lista (queijo mussarela fatiado e azeite Gallo). Não mexi | Chrome |

---

## I01: Fermento químico em pó Dr. Oetker 100 g

| Código | Produto | Mercado | Marca | Tamanho | Preço | Preço comparável | Promoção/condição | Frete | Link | Consultado em | Situação |
|---|---|---|---|---|---|---|---|---|---|---|---|
| I01 | Fermento Em Pó Químico Dr. Oetker 100G | Nagumo | Dr. Oetker | 100 g (**embalagem não informada**: a página não diz se é sachê ou pote; descrição curta "FERMENTO DR OETKER 100G") | **R$ 4,49** (página: "Preço baixou! De R$ 5,98 por R$ 4,49", -25%) | R$ 44,90/kg (R$ 59,80/kg pelo preço "de") | preço "por" tem selo Meu Nagumo (ver condições); "Em estoque", botão ativo, estoque da loja 164 | pelo CEP no pedido | https://www.nagumo.com.br/categoria/mercearia-salgada/confeitaria-e-preparo/fermento-po/fermento-em-p%C3%B3-qu%C3%ADmico-dr.-oetker-100g-303552.html | 26/09 12h55 | encontrado (embalagem não confirmada) |
| I01 | Dr. Oetker 100 g | Sam's Club | — | — | — | — | — | — | — | 26/09 12h52 | **não encontrado** |

Sam's Club: alternativas (fermento químico em pó, tamanho mais próximo; não escolhi):
- (a) Fermento Químico em Pó Royal Pote 250g: R$ 10,98 (R$ 43,92/kg), estoque 100 no catálogo. https://www.samsclub.com.br/fermento-quimico-em-po-royal-pote-250g-7622300119652/p
- (b) Fermento Químico em Pó Dr. Oetker Pote 200g: **sem preço e sem estoque** (indisponível). https://www.samsclub.com.br/fermento-quimico-em-po-dr-oetker-pote-200g-7891048040089/p
- Não há outro fermento químico em pó no Sam's Club. Os demais resultados são fermento biológico ou farinha com fermento.

Nagumo: outros fermentos químicos (registro): Royal 100 g R$ 5,69; Dona Benta 100 g R$ 4,98 (por R$ 3,79, selo Meu Nagumo); Nagumo 100 g R$ 4,29; Dr. Oetker 200 g R$ 10,49 (por R$ 8,59), **indisponível**; Nita 100 g, indisponível.

## I02: Margarina Doriana com sal 500 g

| Código | Produto | Mercado | Marca | Tamanho | Preço | Preço comparável | Promoção/condição | Frete | Link | Consultado em | Situação |
|---|---|---|---|---|---|---|---|---|---|---|---|
| I02 | Margarina Cremosa com Sal Doriana Pote 500g | Sam's Club | Doriana | 500 g, pote | **R$ 8,98** | R$ 17,96/kg | sem promoção; botão "Adicionar ao Carrinho" ativo; estoque 10 no catálogo; **só para sócios** | ver condições | https://www.samsclub.com.br/produto/margarina-cremosa-com-sal-doriana-pote-500g-110301 (antigo: https://www.samsclub.com.br/margarina-cremosa-com-sal-doriana-pote-500g-nova-7894904571956/p) | 26/09 13h00 | encontrado |
| I02 | Margarina Cremosa com Sal Doriana 500G | Nagumo | Doriana | 500 g | **R$ 7,98** | R$ 15,96/kg | sem promoção; botão ativo; estoque da loja 454 | pelo CEP no pedido | https://www.nagumo.com.br/categoria/departamentos/frios-e-laticinios/passadores/margarina/margarina-cremosa-com-sal-doriana-500g-474979.html | 26/09 13h00 | encontrado |

## I03: Coco ralado seco (desidratado) Sococo 100 g

| Código | Produto | Mercado | Marca | Tamanho | Preço | Preço comparável | Promoção/condição | Frete | Link | Consultado em | Situação |
|---|---|---|---|---|---|---|---|---|---|---|---|
| I03 | Coco Ralado Desidratado Sococo 100g ("desidratado parcialmente desengordurado", pacote) | Sam's Club | Sococo | 100 g | **R$ 9,98** | R$ 99,80/kg | sem promoção; botão ativo; estoque 99999 no catálogo; só para sócios | ver condições | https://www.samsclub.com.br/produto/coco-ralado-desidratado-sococo-100g-148496 (antigo: https://www.samsclub.com.br/coco-ralado-desidratado-sococo-100g-7896004400013/p) | 26/09 13h05 | encontrado |
| I03 | Coco Ralado Sococo 100G. (descrição curta "COCO RAL SOCOCO 100G DES"; texto: "100g de coco desidratado") | Nagumo | Sococo | 100 g | **R$ 8,69** | R$ 86,90/kg | sem promoção; botão ativo; estoque da loja 305 | pelo CEP no pedido | https://www.nagumo.com.br/categoria/mercearia-salgada/confeitaria-e-preparo/coco-ralado/coco-ralado-sococo-100g.-291408.html | 26/09 12h58 | encontrado |

Não confundir: os dois sites também têm Sococo **Sweet** (úmido e adoçado) 100 g: Sam's R$ 9,98; Nagumo R$ 8,98 (por R$ 7,29, selo Meu Nagumo). Esse é outro produto.

## I04: Sabão líquido Omo Puro Cuidado 3 L

| Código | Produto | Mercado | Marca | Tamanho | Preço | Preço comparável | Promoção/condição | Frete | Link | Consultado em | Situação |
|---|---|---|---|---|---|---|---|---|---|---|---|
| I04 | Sabão Líquido Puro Cuidado Omo 3L | Nagumo | Omo | 3 L | **R$ 42,98** | R$ 14,33/L | sem promoção; botão ativo; estoque da loja 63 | pelo CEP no pedido | https://www.nagumo.com.br/categoria/departamentos/limpeza/cuidado-roupa/lava-roupa/sab%C3%A3o-l%C3%ADquido-puro-cuidado-omo-3l-592284.html | 26/09 12h57 | encontrado |
| I04 | Omo Puro Cuidado 3 L | Sam's Club | — | — | — | — | — | — | — | 26/09 12h53 | **não encontrado** |

Sam's Club: alternativas (não escolhi). Estoque pelo catálogo do site, página não aberta no Chrome:
- (a) Lava-Roupas Líquido Omo Puro Cuidado Galão 5L Embalagem Econômica: **R$ 57,99** (de R$ 62,98), R$ 11,60/L, estoque 99999. https://www.samsclub.com.br/lava-roupas-liquido-omo-puro-cuidado-galao-5l-embalagem-economica-7891150080492/p
- (b) Lava-Roupas Líquido Lavagem Perfeita Omo Galão 5l: R$ 57,99 (de R$ 62,98), R$ 11,60/L, estoque 99999. https://www.samsclub.com.br/lava-roupas-liquido-omo-lavagem-perfeita-5l-7891150025103/p
- Omo Pro Galão 7l: sem preço e sem estoque.

## I05: Sabão em pó Omo Lavagem Perfeita 2,2 kg (ou 2,4 kg)

| Código | Produto | Mercado | Marca | Tamanho | Preço | Preço comparável | Promoção/condição | Frete | Link | Consultado em | Situação |
|---|---|---|---|---|---|---|---|---|---|---|---|
| I05 | Sabão Em Pó Lavagem Perfeita Omo 2,2Kg | Nagumo | Omo | 2,2 kg | **R$ 25,98** (página: "Preço baixou! De R$ 29,98 por R$ 25,98", -13%) | R$ 11,81/kg (R$ 13,63/kg pelo preço "de") | preço "por" tem selo Meu Nagumo (ver condições); botão ativo; estoque da loja 277 | pelo CEP no pedido | https://www.nagumo.com.br/categoria/departamentos/limpeza/cuidado-roupa/lava-roupa/sab%C3%A3o-em-p%C3%B3-lavagem-perfeita-omo-2%2C2kg-234661.html | 26/09 12h59 | encontrado |
| I05 | Omo Lavagem Perfeita 2,2 kg / 2,4 kg | Sam's Club | — | — | — | — | — | — | — | 26/09 12h53 | **não encontrado** |

Sam's Club: todos os sabões em pó Omo do site estão **sem preço e sem estoque**. Não há alternativa Omo em pó disponível:
- Lava-Roupas em Pó Lavagem Perfeita Omo Caixa 1,6kg: indisponível. https://www.samsclub.com.br/lava-roupas-em-po-lavagem-perfeita-omo-caixa-1-6kg-7891150064331/p
- Lava-Roupas em Pó Lavagem Perfeita Omo Pacote 3,6Kg: indisponível. https://www.samsclub.com.br/lava-roupas-em-po-omo-lavagem-perfeita-pacote-36kg-embalagem-economica-7891150064584/p
- Lava-Roupas em Pó Lavagem Perfeita Omo Pacote 4kg: indisponível. https://www.samsclub.com.br/lava-roupas-em-po-omo-lavagem-perfeita-4kg-tamanho-familia-7891150069053/p

Nagumo: também tem **Omo Lavagem Perfeita 2,4 kg** (R$ 43,45), **indisponível**. https://www.nagumo.com.br/categoria/departamentos/limpeza/cuidado-roupa/lava-roupa/lava-roupas-p%C3%B3-omo-lavagem-perfeita-pacote-2%2C4kg-tamanho-fam%C3%ADlia-216910.html

---

## Tabela final: 5 itens em 4 mercados (preço de 1 unidade)

| Código | Item | Sam's Club | Nagumo | Atacadão (carrinho) | Carrefour (carrinho) |
|---|---|---|---|---|---|
| I01 | Fermento Dr. Oetker 100 g | **não encontrado** (Dr. Oetker 200 g indisponível; Royal 250 g R$ 10,98) | R$ 4,49 (de R$ 5,98; embalagem não informada) | R$ 3,98 (**pote**) | R$ 5,39 (**sachê**) |
| I02 | Margarina Doriana com sal 500 g | R$ 8,98 | R$ 7,98 | R$ 8,40 | R$ 6,89 |
| I03 | Coco ralado Sococo 100 g | R$ 9,98 | R$ 8,69 | R$ 7,49 | R$ 9,59 |
| I04 | Omo Puro Cuidado líquido 3 L | **não encontrado** (só 5 L, R$ 57,99) | R$ 42,98 | R$ 45,90 | R$ 45,79 |
| I05 | Omo Lavagem Perfeita pó | **não encontrado** (todos indisponíveis) | R$ 25,98 (2,2 kg; de R$ 29,98) | R$ 24,90 (**2,4 kg**) | R$ 30,09 (2,2 kg) |
| | **Itens atendidos** | **2 de 5** | **5 de 5** | 5 de 5 (2 com substituição autorizada) | 5 de 5 (exatos) |
| | **Total dos produtos** | — (incompleto) | **R$ 90,12** (R$ 95,61 pelos preços "de") | R$ 90,67 | R$ 97,75 |
| | Condições | só para sócios (anuidade R$ 95 ou R$ 175); pedido mínimo/frete não confirmados | cadastro/login para comprar; frete pelo CEP; mínimo não confirmado | mínimo R$ 250 (faltam R$ 159,33); taxa de serviço R$ 5,44 | frete a partir de R$ 10,90 |

Conta do Nagumo: 4,49 + 7,98 + 8,69 + 42,98 + 25,98 = **R$ 90,12**. Pelos preços "de" (caso o desconto exija Meu Nagumo): 5,98 + 7,98 + 8,69 + 42,98 + 29,98 = **R$ 95,61**.

## Observações e pendências para o Verificador
- **Nagumo tem os 5 itens** com o tamanho pedido (I05 em 2,2 kg, igual ao Carrefour). Pendências: (1) embalagem do fermento (sachê ou pote) não informada na página; (2) se o preço "por" de I01 e I05 exige o Meu Nagumo (**não confirmado**); (3) os preços e o estoque são da **loja** que já estava selecionada na sessão (026-STO AND2, modo "Retirada"). Com entrega em outro CEP, a loja pode mudar; (4) para comprar é preciso login/cadastro.
- **Sam's Club:** só 2 de 5 itens (I02, I03), e comprar exige ser sócio pagante.
- Estoque do Sam's pelo catálogo do site. Para I02 e I03 também conferi a página (preço e botão ativo). As alternativas de I01 e I04 não foram abertas no Chrome.
- As informações de pedido mínimo e frete que vieram só de buscas na web (Sam's R$ 150 / R$ 24,90; Nagumo R$ 99) ficam como **não confirmadas**.
