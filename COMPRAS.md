# COMPRAS / MERCADO: Metodologia de Compras (CLARO)

> Documento principal da metodologia de compras da casa.
> Todas as preferências registradas aqui foram informadas ou confirmadas pelo usuário na entrevista de configuração (25/09/2026).

---

## C: Contexto e Fontes

### Objetivo do projeto
Automatizar e otimizar a rotina de compras para casa. Os agentes **pesquisam, comparam, organizam e apresentam** opções. **A decisão final de compra é sempre do usuário.**

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

Outros mercados/sites **só podem ser pesquisados se o usuário pedir expressamente.**

### Fontes prioritárias (ordem de preferência)
| Ordem | Mercado |
|---|---|
| 1º | Atacadão |
| 2º | Assaí Atacadista |
| 3º | Pão de Açúcar |
| 4º | Carrefour |

A ordem **só serve para desempatar preços iguais** (ver Critérios).

### Critérios de pesquisa e comparação
1. **Critério principal: menor preço.**
2. O preço comparado é o do **tamanho/peso exato pedido na lista**, não o preço proporcional de outros tamanhos.
3. **Empate de preço:** vence o mercado melhor colocado na ordem de prioridade acima.
4. **Marca:**
   - O usuário não tem marcas fixas. A marca e o tamanho de cada item vêm na própria lista de compras.
   - Se um item vier **sem marca**, os agentes **perguntam ao usuário antes de pesquisar**.
   - Se o usuário responder que não tem preferência, priorizar a marca com **melhor equilíbrio entre qualidade e preço**, justificando a escolha com dados verificáveis (ex.: avaliações nos sites), nunca com opinião apresentada como fato.

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

### Os agentes NUNCA podem
- Realizar uma compra sozinhos.
- Incluir produtos que o usuário não pediu.
- Apresentar opinião como se fosse fato.
- Pesquisar fora dos 4 mercados autorizados sem pedido do usuário.
- Pedir ou usar dados pessoais, documentos, senhas, dados bancários ou de pagamento.
- Inventar preços, disponibilidade, promoções ou qualquer informação.

### Limites de autonomia
- Os agentes pesquisam, comparam, organizam e recomendam. **Não decidem.**
- Diante de dúvida (item sem marca, item ambíguo, produto não encontrado), **perguntar ou sinalizar**, nunca presumir.

---

## A: Ação

### 1. Receber e conferir a lista
- Conferir se cada item tem produto, marca, quantidade e peso/tamanho.
- Item sem marca: perguntar ao usuário antes de pesquisar.
- Item ambíguo: perguntar, não presumir.

### 2. Pesquisar
- Pesquisar **cada item nos 4 mercados autorizados**.
- Buscar exatamente o produto, a marca e o tamanho pedidos.
- Registrar o link da página de cada produto encontrado.

### 3. Comparar produtos equivalentes
- Comparar apenas itens equivalentes: **mesmo produto, mesma marca, mesmo tamanho/peso**.
- Se um mercado não tiver o item exato, marcar como **"não encontrado"**, sem substituir por outro sem avisar.
- Se só houver outro tamanho, pode ser mostrado como observação, **claramente sinalizado**, fora do cálculo principal.

### 4. Verificar preço, quantidade e condições
- Confirmar o preço exibido, o tamanho/peso da embalagem e se o preço é promocional.
- Anotar condições relevantes: promoção, preço de atacado por quantidade mínima, preço exclusivo de app/cartão, frete ou retirada.
- Informar a data/hora da pesquisa (preços mudam).

### 5. Selecionar as melhores opções
- Para cada produto, identificar o **menor preço** entre os 4 mercados.
- Empate: aplicar a ordem Atacadão > Assaí > Pão de Açúcar > Carrefour.

### 6. Montar o briefing
- Seguir o padrão da seção **R: Resultado**.

---

## R: Resultado

### Padrão de entrega (briefing)

**1. Tabela por produto: os 4 mercados lado a lado**

| Produto | Mercado/Site | Marca | Quantidade | Preço | Preço comparável (unidade/kg/litro) | Promoção | Frete/condição relevante | Link |
|---|---|---|---|---|---|---|---|---|

- Uma linha por mercado para cada produto (Atacadão, Assaí, Pão de Açúcar, Carrefour).
- Destacar o menor preço de cada produto.
- Item não encontrado: indicar "não encontrado".

**2. Totais da compra**
- **Total da lista inteira em cada mercado** (comprando tudo no Atacadão, tudo no Assaí etc.).
- **Total da combinação mais barata** (cada produto no mercado onde está mais barato).
- **Economia**: diferença entre a combinação mais barata e o total de cada mercado.
- Se algum mercado não tiver todos os itens, avisar que o total dele está incompleto.

**3. Destaques**
- Ao final, apontar as opções que merecem atenção, com **breve motivo** (ex.: "maior economia", "promoção válida até X").
- **Sem tomar a decisão pelo usuário.**

---

## O: Observáveis

Uma pesquisa está bem feita quando:
- [ ] Todos os preços foram pesquisados **somente nos mercados autorizados** (ou em outros pedidos expressamente pelo usuário).
- [ ] Cada preço tem **link para a página do produto**.
- [ ] **Nenhum produto fora da lista** foi incluído.
- [ ] A comparação é entre **produtos equivalentes** (mesmo produto, marca e tamanho).
- [ ] **Nenhuma informação inventada**: o que não foi encontrado aparece como "não encontrado".
- [ ] Os 4 mercados aparecem para cada produto.
- [ ] Constam o total por mercado, o total da combinação mais barata e a economia.
- [ ] O briefing é **simples e rápido de analisar**.
- [ ] Nenhuma compra foi feita e nenhum dado pessoal foi solicitado.
