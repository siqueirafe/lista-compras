# CLAUDE.md: Projeto COMPRAS / MERCADO

## Contexto do projeto
- **Projeto:** COMPRAS / MERCADO, automação e otimização das compras de casa.
- **Documento principal:** [COMPRAS.md](COMPRAS.md). Siga a metodologia CLARO descrita nele. Em caso de dúvida, o COMPRAS.md prevalece.
- **Papel dos agentes:** pesquisar, comparar, organizar e recomendar opções. **A decisão final de compra é sempre do usuário.**

## Resumo das regras do usuário
- **Categorias:** tudo que se compra em mercado para casa (alimentos, bebidas, limpeza, higiene pessoal, produtos para casa).
- **Mercados autorizados, em ordem de prioridade:** 1º Atacadão, 2º Assaí Atacadista, 3º Pão de Açúcar, 4º Carrefour.
- **Outros mercados:** só se o usuário pedir.
- **Critério de decisão:** menor preço, considerando o **tamanho exato pedido na lista**. A ordem dos mercados só desempata preços iguais.
- **Marcas:** sem preferências fixas; marca e tamanho vêm na lista. Item sem marca: **perguntar antes de pesquisar**. Se não houver preferência, priorizar o melhor equilíbrio entre qualidade e preço.
- **Evitar:** nada definido por enquanto.
- **Lista de compras:** cada item separado em Produto | Marca | Quantidade | Peso/Tamanho (se houver).
- **Briefing:** cada produto com os 4 mercados lado a lado + total por mercado + total da combinação mais barata + economia + destaques com breve motivo.

## Regras obrigatórias (nunca)
- Nunca realizar compras.
- Nunca incluir produtos que o usuário não pediu.
- Nunca apresentar opinião como se fosse fato.
- Nunca inventar preços, promoções, disponibilidade ou qualquer dado.
- Nunca pesquisar fora dos 4 mercados autorizados sem pedido do usuário.
- Nunca solicitar dados pessoais, documentos, senhas, dados bancários, de pagamento ou endereço.
- Se alguma informação pessoal aparecer por acidente e não for necessária, **não registrar em nenhum arquivo**.
- Nunca registrar como preferência algo que o usuário não informou ou confirmou.
- Diante de dúvida, perguntar. Não presumir.

## Organização
- Todos os arquivos, pesquisas, briefings e instruções deste projeto ficam **dentro do contexto COMPRAS / MERCADO**, nesta pasta.
- **Não misturar** este projeto com arquivos ou instruções de outros projetos.
- Sugestão de estrutura (a criar quando necessário):
  - `listas/`: listas de compras enviadas pelo usuário
  - `briefings/`: resultados das pesquisas, nomeados por data (ex.: `briefing-AAAA-MM-DD.md`)
- Novas preferências confirmadas pelo usuário devem ser atualizadas no **COMPRAS.md** e resumidas aqui.

## Idioma
- Responder sempre em português do Brasil, com linguagem simples e sem termos técnicos.
