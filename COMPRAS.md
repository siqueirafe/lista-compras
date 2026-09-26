# COMPRAS / MERCADO: Metodologia de Compras (CLARO)

> Documento principal da metodologia de compras da casa.
> Todas as preferências registradas aqui foram informadas ou confirmadas pelo usuário: na entrevista de configuração (25/09/2026) e nas decisões da primeira compra (25/09/2026).

---

## C: Contexto e Fontes

### Objetivo do projeto
Automatizar e otimizar a rotina de compras para casa. Os agentes **pesquisam, comparam, verificam, preparam o carrinho e apresentam** as opções. **A decisão final e o pagamento são sempre do usuário.**

### Tipos de compras
Tudo que se compra em mercado para casa:
- Alimentos
- Bebidas
- Produtos de limpeza
- Higiene pessoal
- Produtos para casa

### Mercados autorizados
Somente estes 4 mercados:
1. **Atacadão**
2. **Assaí Atacadista**
3. **Pão de Açúcar**
4. **Carrefour**

Outros mercados/sites **só podem ser pesquisados se o usuário pedir expressamente**.
O usuário pode **tirar um mercado de uma compra específica** (ex.: em 25/09 tirou o Pão de Açúcar porque o site exigia login). Nesse caso, a compra segue só com os demais.

### Ordem dos mercados
| Ordem | Mercado |
|---|---|
| 1º | Atacadão |
| 2º | Assaí Atacadista |
| 3º | Pão de Açúcar |
| 4º | Carrefour |

A ordem **só serve para desempate** (ver Critérios).

### Critérios de pesquisa e comparação
**Prioridade (definida pelo usuário em 25/09/2026):**
1. **Produto correto.**
2. **Disponibilidade da lista.**
3. **Concentração no menor número de mercados.**
4. **Preço e condições.**

**Como escolher o mercado:**
1. Primeiro, procurar **um único mercado com 100% dos itens**.
2. Se nenhum tiver tudo, escolher o mercado com **mais itens da lista**.
3. Só quando necessário, dividir o restante entre outros mercados, usando **o menor número possível**.
4. **Desempate:** menor total da compra. Se o empate continuar, vale a ordem Atacadão > Assaí > Pão de Açúcar > Carrefour.

**Preço:**
- O preço comparado é o do **tamanho/peso exato pedido na lista**, não o preço proporcional de outros tamanhos.
- Entre mercados que atendem a lista igualmente, vence o **menor preço**.

**Disponibilidade:**
- Um item só conta como disponível quando o estoque está **comprovado** (ex.: preço e botão de compra ativos, sem aviso de "indisponível" ou "estoque 0").
- Se o site mostrar sinais contraditórios, o item fica em ATENÇÃO e não conta como disponível.

**Marca e variante:**
- O usuário não tem marcas fixas. A marca e o tamanho de cada item vêm na própria lista de compras.
- Item **sem marca**: perguntar ao usuário antes de pesquisar.
- Se o usuário responder que não tem preferência, priorizar a marca com **melhor equilíbrio entre qualidade e preço**, justificando com dados verificáveis (ex.: avaliações nos sites), nunca com opinião apresentada como fato.
- Item **sem variante definida** (ex.: tipo de arroz, fragrância do detergente, folha e metragem do papel): pesquisar as variantes existentes e **apresentar as opções com preço para o usuário escolher**. Nunca escolher pelo usuário.

### Formato da lista de compras
Cada item da lista deve ser registrado separadamente em:

| Produto | Marca | Quantidade | Peso/Tamanho (se houver) |
|---|---|---|---|

---

## L: Limites

### Produtos, marcas ou mercados a evitar
- Nenhum definido por enquanto.

### Fora do escopo
- Pesquisar em mercados/sites fora dos 4 autorizados, a menos que o usuário peça.
- Qualquer assunto que não seja a lista de compras enviada pelo usuário.

### CEP
- O agente pode **usar o CEP que o usuário informar**, só no campo de CEP do site do mercado, para ver frete, prazo e estoque da região.
- Se o site pedir CEP, **perguntar ao usuário**. Nunca usar um CEP que ele não informou naquela compra.
- **Nunca gravar o CEP** em nenhum arquivo do projeto, porque os arquivos vão para o GitHub. Nos arquivos, escrever "CEP informado pelo usuário".
- Nenhum outro dado de endereço é autorizado.

### Os agentes NUNCA podem
- Confirmar pedido, efetuar pagamento ou finalizar uma compra.
- Incluir produtos que o usuário não pediu.
- Substituir produto, marca, tamanho ou variante sem a escolha do usuário.
- Apresentar opinião como se fosse fato.
- Pesquisar fora dos 4 mercados autorizados sem pedido do usuário.
- Pedir ou usar senha, e-mail, CPF, endereço completo, cartão ou dados de pagamento.
- Fazer login, criar conta ou aceitar termos.
- Inventar preços, estoque, promoções, links ou qualquer informação.

### Limites de autonomia
- Os agentes pesquisam, comparam, verificam e **preparam o carrinho**. **Não decidem e não pagam.**
- O carrinho só é preparado **depois que o usuário aprovar a lista** (itens, variantes e mercado).
- Se o site pedir **login**, parar e perguntar ao usuário: ele entra na conta pelo navegador **ou** tira aquele mercado da compra.
- Diante de dúvida (item sem marca ou variante, produto não encontrado, sem estoque), **perguntar ou sinalizar**, nunca presumir.

---

## A: Ação

### 1. Receber e conferir a lista
- Conferir se cada item tem produto, marca, quantidade e peso/tamanho.
- Item sem marca: perguntar ao usuário antes de pesquisar.
- Dar a cada item um código fixo (`I01`, `I02`, ...), usado em todas as etapas.
- Salvar tudo em `pesquisas/AAAA-MM-DD/`, começando por `0-lista.md`. Registrar ali cada decisão do usuário.

### 2. Pesquisar
- Pesquisar **cada item nos mercados autorizados** da compra.
- Buscar exatamente o produto, a marca e o tamanho pedidos. Se a variante não estiver definida, registrar as variantes encontradas.
- Registrar o link da página de cada produto.
- Se um site bloquear a leitura automática, o navegador pode ser usado **só para ler**.

### 3. Verificar
- Conferir domínio oficial, link, produto, preço e estoque de cada oferta.
- Classificar como **VALIDADO**, **ATENÇÃO** ou **NÃO PROSSEGUIR**.
- Aplicar a regra de concentração de mercados (seção C).
- **Parar e perguntar ao usuário** antes do carrinho se houver variante, substituição ou qualquer decisão pendente.

### 4. Comparar produtos equivalentes
- Comparar apenas itens equivalentes: **mesmo produto, mesma marca, mesmo tamanho/peso**.
- Se um mercado não tiver o item exato, marcar como **"não encontrado"**, sem substituir por outro sem avisar.
- Se só houver outro tamanho, mostrar como observação, **claramente sinalizado**, fora do cálculo principal.

### 5. Preparar o carrinho (só com a lista aprovada)
- Antes de adicionar cada item, conferir de novo: **Produto + Marca + Tamanho + Preço + estoque**.
- Não adicionar se o preço mudar mais de 10% ou se estiver sem estoque. Nesse caso, avisar o usuário.
- Colocar exatamente a quantidade aprovada, mesmo que exista promoção para levar mais (ex.: "50% na 2ª unidade").
- Deixar desmarcado o "substituir por similar". Não remover itens que já estavam no carrinho, só avisar.
- Parar na tela do carrinho, antes de continuar para o pagamento.

### 6. Item sem estoque
- Pesquisar alternativas **só nas marcas ou linhas que o usuário indicar**.
- Apresentar as opções com preço, preço por rolo/kg/litro e disponibilidade, e esperar a escolha do usuário.

### 7. Validar e montar o briefing
- Comparar Lista → Pesquisa → Verificação → Carrinho.
- Seguir o padrão da seção **R: Resultado**.

---

## R: Resultado

### Primeira linha
Uma frase que o usuário entenda em 5 segundos: mercado, itens no carrinho, valor e status.

### Resultado final (bloco curto)
```
Mercado(s) escolhido(s): ...
Itens encontrados: X de Y solicitados
Valor estimado da compra: R$ ... (produtos + frete)
Itens pendentes: ... (ou "nenhum")
Status: PODE COMPRAR | REVISAR ANTES DE COMPRAR
Link do carrinho: ... (só se o site oferecer; senão, como acessar)
```

### Tabela de comparação por produto (na pesquisa)

| Produto | Mercado/Site | Marca | Quantidade | Preço | Preço comparável (unidade/kg/litro) | Promoção | Frete/condição relevante | Link |
|---|---|---|---|---|---|---|---|---|

- Uma linha por mercado pesquisado para cada produto.
- Item não encontrado: indicar "não encontrado".

### Tabela final (na validação)

| Produto | Marca | Quantidade | Mercado | Preço | Status | Link |
|---|---|---|---|---|---|---|

Depois da tabela: itens solicitados, encontrados e no carrinho; itens não encontrados; decisões pendentes; número de mercados; valor de cada carrinho e total. Quando houver dados comprovados, mostrar também o total da lista em cada mercado e a economia.

### Status
- **PODE COMPRAR**: o carrinho corresponde à lista aprovada e não há pendências. **Não é autorização para pagamento.**
- **REVISAR ANTES DE COMPRAR**: há divergência, item faltando, substituição, diferença relevante de preço ou algo que precisa da decisão do usuário.

### Destaques
- Apontar o que merece atenção, com **breve motivo** (ex.: "menos papel no total", "frete exato só no checkout").
- **Sem tomar a decisão pelo usuário.**

---

## O: Observáveis

Uma compra está bem preparada quando:
- [ ] Todos os preços foram pesquisados **somente nos mercados autorizados** da compra.
- [ ] Cada preço tem **link para a página do produto**.
- [ ] **Nenhum produto fora da lista** foi incluído.
- [ ] Nenhuma substituição ou variante foi escolhida sem o usuário.
- [ ] A comparação é entre **produtos equivalentes** (mesmo produto, marca e tamanho).
- [ ] Estoque só contou quando **comprovado**.
- [ ] **Nenhuma informação inventada**: o que não foi confirmado aparece como "não confirmado".
- [ ] A regra de concentração de mercados foi aplicada.
- [ ] O carrinho bate com a lista aprovada: nada a mais, nada a menos.
- [ ] Nenhum pedido confirmado, nenhum pagamento, nenhum login feito pelo agente.
- [ ] O CEP não aparece em nenhum arquivo.
- [ ] O briefing é **simples e rápido de analisar**, com a primeira linha e o status.

---

## Observações dos mercados (25/09/2026)
Fatos vistos na primeira compra. Podem mudar; reconferir a cada compra.
- **Pão de Açúcar:** exige login para colocar itens no carrinho.
- **Carrefour:** exige CEP ou loja para colocar itens no carrinho; não exigiu login para montar o carrinho. Bloqueia leitura automática, então a pesquisa precisa do navegador.
- **Atacadão:** sem CEP, mostra preços da loja padrão do site. A página do produto e o catálogo do site podem divergir no estoque.
- **Assaí:** o site não mostra preço nem vende; direciona para o app "Meu Assaí", iFood e Rappi.
- Nenhum dos mercados ofereceu link de carrinho para compartilhar.
