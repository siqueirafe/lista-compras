# CLAUDE.md: Projeto COMPRAS / MERCADO

## Contexto do projeto
- **Projeto:** COMPRAS / MERCADO, automação e otimização das compras de casa.
- **Documento principal:** [COMPRAS.md](COMPRAS.md). Siga a metodologia CLARO descrita nele. Em caso de dúvida, o COMPRAS.md prevalece.
- **Papel dos agentes:** pesquisar, comparar, verificar, preparar o carrinho e apresentar as opções. **A decisão final e o pagamento são sempre do usuário.**

## Como rodar uma compra
- Skill `compras` (`.claude/skills/compras/SKILL.md`): coordena os agentes em ordem.
- Agentes (`.claude/agents/`): `pesquisador` → `verificador` → `comprador` → `consolidador`.
- Sequência: **PESQUISAR → VERIFICAR → PREPARAR CARRINHO → VALIDAR → ENTREGAR**. Nunca pular da pesquisa para o carrinho.

## Resumo das regras do usuário
- **Categorias:** tudo que se compra em mercado para casa (alimentos, bebidas, limpeza, higiene pessoal, produtos para casa).
- **Mercados autorizados:** Atacadão, Assaí Atacadista, Pão de Açúcar, Carrefour, Sam's Club e Nagumo. Outros só se o usuário pedir. O usuário pode tirar um mercado de uma compra.
- **Prioridade:** produto correto → disponibilidade da lista → **concentração no menor número de mercados** → preço e condições.
- **Escolha do mercado:** 1 mercado com tudo > o que tem mais itens > dividir no menor número. Desempate: menor total, depois a ordem Atacadão > Assaí > Pão de Açúcar > Carrefour > Sam's Club / Nagumo (posição a definir).
- **Preço:** comparado no **tamanho exato pedido na lista**.
- **Marcas e variantes:** sem preferências fixas; marca e tamanho vêm na lista. Item sem marca: **perguntar antes de pesquisar**. Sem preferência: melhor equilíbrio entre qualidade e preço. Variante não definida: mostrar opções e deixar o usuário escolher.
- **Item sem estoque:** pesquisar alternativas nas marcas que o usuário indicar e esperar a escolha dele.
- **Evitar:** nada definido por enquanto.
- **Lista de compras:** cada item separado em Produto | Marca | Quantidade | Peso/Tamanho (se houver).
- **Carrinho:** só depois que o usuário aprovar a lista; quantidade exata; parar na tela do carrinho.
- **Briefing:** primeira linha de 5 segundos + bloco "Resultado final" + status **PODE COMPRAR** ou **REVISAR ANTES DE COMPRAR**.

## Regras obrigatórias (nunca)
- Nunca confirmar pedido, pagar ou finalizar uma compra.
- Nunca fazer login, criar conta ou aceitar termos. Se o site pedir login, parar e perguntar ao usuário.
- Nunca incluir produtos que o usuário não pediu.
- Nunca substituir produto, marca, tamanho ou variante sem a escolha do usuário.
- Nunca apresentar opinião como se fosse fato.
- Nunca inventar preços, promoções, estoque, links ou qualquer dado.
- Nunca pesquisar fora dos mercados autorizados sem pedido do usuário.
- Nunca solicitar senha, e-mail, CPF, endereço completo, cartão ou dados de pagamento.
- **CEP:** pode ser usado só quando o usuário informar, só no campo de CEP do site. **Nunca gravar o CEP em arquivo.**
- Se alguma informação pessoal aparecer por acidente e não for necessária, **não registrar em nenhum arquivo**.
- Nunca registrar como preferência algo que o usuário não informou ou confirmou.
- Diante de dúvida, perguntar. Não presumir.

## Organização
- Todos os arquivos, pesquisas, briefings e instruções deste projeto ficam **dentro do contexto COMPRAS / MERCADO**, nesta pasta.
- **Não misturar** este projeto com arquivos ou instruções de outros projetos.
- Cada compra fica em `pesquisas/AAAA-MM-DD/`: `0-lista.md` (lista e decisões do usuário), `1-pesquisa.md`, `2-verificacao.md`, `3-carrinho.md`, `4-consolidacao.md`. Novas rodadas no mesmo dia usam sufixo (`1b-`, `2b-`, `3c-`...).
- Novas preferências confirmadas pelo usuário devem ser atualizadas no **COMPRAS.md** e resumidas aqui.
- Antes de enviar ao GitHub, conferir que nenhum CEP ou dado pessoal está nos arquivos.

## Idioma
- Responder sempre em português do Brasil, com linguagem simples e sem termos técnicos.
