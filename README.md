# Compras / Mercado

este agente vai fazer as minhas compras conforme necessidade. Eu mando a lista com o que preciso para casa (alimentos, bebidas, limpeza, higiene pessoal e produtos para casa) e ele pesquisa os preços no Atacadão, no Assaí, no Pão de Açúcar e no Carrefour. Com o briefing eu vejo onde cada produto está mais barato e quanto economizo, e a decisão final de compra é sempre minha.

## Como funciona

Eu mando a lista de compras com cada item separado em produto, marca, quantidade e peso/tamanho. Se algum item vier sem marca, o agente me pergunta antes de pesquisar. Se eu disser que não tenho preferência, ele escolhe a marca com melhor equilíbrio entre qualidade e preço.

Ele pesquisa cada item nos 4 mercados, sempre no tamanho exato que pedi, e compara pelo menor preço. Se der empate, vale a ordem: Atacadão, Assaí, Pão de Açúcar e Carrefour.

No briefing eu recebo cada produto com os 4 mercados lado a lado, o total da compra em cada mercado, o total se eu comprar cada item onde está mais barato e quanto economizo. No final ele destaca o que merece minha atenção, sem decidir por mim.
O briefing fica publicado em [A URL DO GITHUB PAGES, DEPOIS DE LIGAR].

- `COMPRAS.md`: as regras das minhas compras (mercados, critérios, limites e formato do briefing).
- `CLAUDE.md`: a memória do projeto, lida pelo Claude Code ao abrir a pasta.

## O que este agente nunca faz

- Comprar sozinho.
- Incluir produto que eu não pedi.
- Opinião como fato.
- Inventar preço, promoção ou qualquer informação.
- Pesquisar em outro mercado sem eu pedir.
- Pedir meus dados pessoais, senhas ou dados de pagamento.
