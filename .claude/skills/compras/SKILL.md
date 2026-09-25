---
name: compras
description: Coordena o fluxo completo de compras da casa, acionando os agentes na ordem correta para pesquisar os produtos solicitados nos mercados autorizados, identificar onde é possível concentrar a maior quantidade de itens, validar a seleção, preparar o carrinho e entregar tudo pronto para revisão e pagamento pelo usuário. Use quando o usuário solicitar uma pesquisa de compras, enviar uma lista de produtos ou pedir para preparar uma compra.
---

# Skill compras: orquestradora do robô de compras da casa

Projeto: **COMPRAS / MERCADO**. Esta Skill coordena os agentes de `.claude/agents/` em uma sequência fixa. Ela não pesquisa nem compra por conta própria: aciona cada agente, confere a entrega e só então passa para a etapa seguinte.

## Sequência obrigatória

**PESQUISAR → VERIFICAR → PREPARAR CARRINHO → VALIDAR → ENTREGAR PARA O USUÁRIO**

| Etapa | Agente | Arquivo gerado |
|---|---|---|
| 1 | `pesquisador` | `pesquisas/AAAA-MM-DD/1-pesquisa.md` |
| 2 | `verificador` | `pesquisas/AAAA-MM-DD/2-verificacao.md` |
| 3 | `comprador` | `pesquisas/AAAA-MM-DD/3-carrinho.md` |
| 4 | `consolidador` (guarda / validação final) | `pesquisas/AAAA-MM-DD/4-consolidacao.md` |

- Uma etapa por vez. A próxima só começa quando a anterior entregou o arquivo dela.
- **Nunca pule da pesquisa direto para o carrinho.**
- Se uma etapa falhar ou ficar incompleta, pare e avise o usuário. Não siga adiante com dados pela metade.

## Antes de começar
1. Leia `CLAUDE.md` e `COMPRAS.md`. `COMPRAS.md` é a regra principal.
2. Receba a lista de compras do usuário. Cada item deve ter **produto, marca, quantidade e peso/tamanho**.
3. Item **sem marca**: pergunte ao usuário antes de pesquisar (regra do COMPRAS.md). Item ambíguo: pergunte.
4. Crie a pasta do dia `pesquisas/AAAA-MM-DD/` e salve nela a lista recebida.
5. Ao acionar cada agente, informe a data, a pasta do dia e as regras desta Skill que se aplicam àquela etapa.

## Prioridade operacional (definida pelo usuário)
1. **Produto correto.**
2. **Disponibilidade da lista.**
3. **Concentração no menor número de mercados.**
4. **Preço e condições**, conforme as preferências do COMPRAS.md.

Sempre que possível, priorize **um único mercado com todos os produtos**.

---

## ETAPA 1: PESQUISADOR
Acione o agente `pesquisador` com a lista de compras.

Ele pesquisa cada produto **somente nos mercados autorizados no COMPRAS.md**: Atacadão, Assaí Atacadista, Pão de Açúcar e Carrefour. Para cada item, em cada mercado, deve procurar:
- produto correto;
- marca solicitada, quando houver;
- quantidade, peso, volume ou tamanho;
- preço;
- preço por unidade/kg/litro, quando fizer sentido;
- promoções relevantes;
- disponibilidade;
- mercado/site;
- link direto do produto.

Ele deve cobrir **todos os itens em todos os mercados**, para que o Verificador descubra qual mercado atende a maior parte ou toda a lista.
Qualquer produto diferente do pedido deve ser **sinalizado como diferença**, nunca escolhido no lugar do produto pedido.

**Conferência antes de seguir:** `1-pesquisa.md` existe, tem todos os itens da lista e tem link ou "não encontrado"/"não confirmado" em cada mercado.

## ETAPA 2: VERIFICADOR
Só depois da Etapa 1, acione o agente `verificador`.

**Função principal:** descobrir qual mercado atende a lista da forma mais completa possível:
1. **1ª prioridade:** um único mercado autorizado com **100% dos produtos**.
2. **2ª prioridade:** se nenhum tiver tudo, o mercado com **a maior quantidade de itens** da lista.
3. **3ª prioridade:** só quando necessário, dividir os itens restantes entre outros mercados autorizados, usando **o menor número possível de mercados**.

Objetivo: evitar compra fragmentada sem necessidade. Se dois mercados empatarem na quantidade de itens, desempate pelo menor total da compra e, persistindo o empate, pela ordem do COMPRAS.md (Atacadão > Assaí > Pão de Açúcar > Carrefour).

Além disso, ele confere:
- se os produtos correspondem ao solicitado;
- disponibilidade;
- preços;
- links;
- quantidade/tamanho;
- substituições;
- confiabilidade dos sites (VALIDADO / ATENÇÃO / NÃO PROSSEGUIR);
- divergências importantes.

**Nunca autorize automaticamente** substituição de produto, marca, tamanho ou quantidade fora das preferências do COMPRAS.md.

Entrega: **recomendação estruturada de onde comprar cada produto**:

| Código | Produto | Mercado recomendado | Motivo | Classificação |
|---|---|---|---|---|

**Ponto de parada:** se houver item em ATENÇÃO, substituição sugerida ou qualquer decisão pendente, **pare e pergunte ao usuário** antes da Etapa 3. Itens em NÃO PROSSEGUIR nunca vão para o carrinho.

## ETAPA 3: COMPRADOR
Só depois da Etapa 2 concluída e das decisões pendentes respondidas, acione o agente `comprador`, informando os mercados selecionados e os itens validados.

Ele acessa o(s) mercado(s) selecionado(s) e adiciona ao carrinho **exatamente** os produtos validados. Antes de adicionar cada um, confere de novo:

**Produto + Marca + Quantidade/Tamanho + Preço**

Pode navegar, pesquisar, selecionar e adicionar itens ao carrinho conforme necessário. Ao terminar, confere se:
- todos os produtos disponíveis foram adicionados;
- as quantidades estão corretas;
- não há produtos extras;
- não houve substituição não autorizada;
- os preços do carrinho não divergem de forma relevante da pesquisa.

Deixa o carrinho preparado **até o limite permitido pelo site**, para o usuário entrar, revisar, informar os dados necessários e pagar.
- **Nunca** confirma o pedido nem efetua pagamento.
- Se o site pedir login, **para e pede ao usuário** que entre na conta pelo navegador. Nunca digita senha nem dados pessoais ou de pagamento.
- Se o site permitir compartilhar ou preservar o carrinho por link, entrega o link.
- Se não permitir, **não inventa link**: informa a limitação e explica como o usuário acessa o carrinho (ex.: "entre no site do Atacadão com sua conta e abra o carrinho").

## ETAPA 4: GUARDA / VALIDAÇÃO FINAL
Depois da Etapa 3, acione o agente `consolidador`.

Ele compara **Lista original → Pesquisa → Verificação → Carrinho final** e confere se tudo está consistente.

Tabela final:

| Produto | Marca | Quantidade | Mercado | Preço | Status | Link |
|---|---|---|---|---|---|---|

Depois da tabela:
- quantidade de produtos solicitados;
- quantidade encontrada;
- quantidade adicionada ao carrinho;
- itens não encontrados;
- itens que precisam da decisão do usuário;
- quantidade de mercados utilizados;
- valor estimado de cada carrinho;
- valor total estimado da compra.

Status final: **apenas um** dos dois abaixo. Nesta Skill, eles substituem o "PODE COMPRAR / NÃO COMPRE AINDA" do agente:
- **PODE COMPRAR**: o carrinho corresponde à lista e não há pendências relevantes. **Não é autorização para pagamento.**
- **REVISAR ANTES DE COMPRAR**: há divergência, produto faltante, substituição, diferença relevante de preço ou outro ponto que precisa da decisão do usuário.

---

## Regras gerais
- Respeitar sempre `CLAUDE.md` e `COMPRAS.md`.
- Nunca incluir produtos que não estejam na lista.
- Nunca aceitar substituições fora das regras do `COMPRAS.md` sem decisão do usuário.
- Nunca inventar preço, disponibilidade, promoção, link ou informação.
- Nunca solicitar ou utilizar senha, cartão, código de segurança ou credenciais de pagamento.
- Nunca finalizar ou pagar uma compra.
- Manter o código de cada item (`I01`, `I02`, ...) em todas as etapas, para rastrear do começo ao fim.
- **A decisão final e o pagamento são sempre do usuário.**

## Resultado final para o usuário
Curto e objetivo, para decidir em segundos se entra no carrinho:

```
Mercado(s) escolhido(s): ...
Itens encontrados: X de Y solicitados
Valor estimado da compra: R$ ...
Itens pendentes: ... (ou "nenhum")
Status: PODE COMPRAR | REVISAR ANTES DE COMPRAR
Link do carrinho: ... (só se o site realmente oferecer; senão, como acessar)
```

O detalhe completo fica em `pesquisas/AAAA-MM-DD/`. Não repita o relatório longo na resposta.
