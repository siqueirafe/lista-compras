# Compras / Mercado

este agente vai fazer as minhas compras conforme necessidade. Eu mando a lista com o que preciso para casa (alimentos, bebidas, limpeza, higiene pessoal e produtos para casa) e ele pesquisa os preços no Atacadão, no Assaí, no Pão de Açúcar, no Carrefour, no Sam's Club e no Nagumo. Com o briefing eu vejo onde cada produto está mais barato e quanto economizo, e a decisão final de compra é sempre minha.

## Como funciona

Eu mando a lista de compras com cada item separado em produto, marca, quantidade e peso/tamanho. Se algum item vier sem marca, o agente me pergunta antes de pesquisar. Se eu disser que não tenho preferência, ele escolhe a marca com melhor equilíbrio entre qualidade e preço.

Ele pesquisa cada item nos mercados que eu autorizei, sempre no tamanho exato que pedi. Primeiro ele procura um mercado só que tenha tudo, para eu não dividir a compra; depois olha o preço. Se der empate, vale o menor total e depois a ordem: Atacadão, Assaí, Pão de Açúcar, Carrefour e, por último, Sam's Club e Nagumo. Se faltar marca, tipo ou estoque de algum item, ele me mostra as opções e eu escolho.

Com a lista aprovada, ele monta o carrinho no mercado escolhido e para antes do pagamento. Se o site pedir login, ele me chama. Se pedir CEP, usa o que eu informar, sem guardar em arquivo.

No briefing eu vejo em 5 segundos o mercado, os itens, o valor e o status: PODE COMPRAR ou REVISAR ANTES DE COMPRAR. No final ele destaca o que merece minha atenção, sem decidir por mim. Quem entra no carrinho e paga sou eu.
O briefing fica publicado em [A URL DO GITHUB PAGES, DEPOIS DE LIGAR].

- `COMPRAS.md`: as regras das minhas compras (mercados, critérios, limites e formato do briefing).
- `CLAUDE.md`: a memória do projeto, lida pelo Claude Code ao abrir a pasta.
- `.claude/agents/`: o time (pesquisador, verificador, comprador e consolidador).
- `.claude/skills/compras/`: a Skill que chama os agentes na ordem.
- `pesquisas/`: uma pasta por compra, com a lista, a pesquisa, a verificação, o carrinho e a validação.

## O que este agente nunca faz

- Confirmar pedido ou pagar.
- Fazer login no meu lugar.
- Trocar produto sem eu escolher.
- Incluir produto que eu não pedi.
- Opinião como fato.
- Inventar preço, promoção ou qualquer informação.
- Pesquisar em outro mercado sem eu pedir.
- Pedir meus dados pessoais, senhas ou dados de pagamento.
