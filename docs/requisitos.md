# Requisitos — Vendas Detergente

Levantamento feito em conversa com meu pai, que vende os produtos, em novembro de 2026.

## Contexto

**Como funciona hoje:**
- A venda é de porta em porta: a gente bate na casa do cliente e oferece os produtos.
- Cada venda gera uma **promissória de papel** com: nome do cliente, endereço, telefone, valor da compra, data de vencimento e alguma observação (ex.: ponto de referência).
- Na volta para cobrar, ele anota "pago" na promissória e guarda. Muitas vezes, na mesma visita, já faz uma venda nova.

**Quem vende:** eu, meu pai e minha mãe, cada um com o próprio celular. Não importa saber quem fez cada venda.

**Problemas principais:**
1. Esquecer quem está devendo.
2. Perder promissória.

## Dados que o sistema guarda

- **Cliente:** nome, telefone, endereço (rua, número e bairro, sempre preenchidos) e ponto de referência (opcional)
- **Produto:** nome (detergente, sabão, amaciante, desinfetante etc.), preço
- **Venda:** cliente, data, produtos vendidos (com quantidade e preço na hora), total, observação
- **Parcela:** número, valor, vencimento, se foi paga e quando

## Regras de negócio

- **RN01:** Hoje todos os produtos custam R$20, mas o preço pode mudar (é raro). Cada venda guarda o preço da época, então vendas antigas não mudam quando o preço muda.
- **RN02:** Uma venda pode ter vários produtos, cada um com a sua quantidade.
- **RN03:** O cliente paga tudo de uma vez no vencimento. Quando o valor é alto, a compra é dividida **na hora da venda** em **no máximo 2 parcelas** (ex.: 6 produtos = R$120 → R$60 este mês + R$60 no próximo). Cada parcela tem o seu valor e vencimento.
- **RN04:** A soma das parcelas tem que ser igual ao total da venda. Os valores costumam ser iguais, mas não precisam (ex.: R$100 → R$60 + R$40).- **RN05:** Não tem juros nem multa por atraso. Ele só volta e cobra.
- **RN06:** Uma parcela está **atrasada** quando o vencimento já passou e ela não foi paga.
- **RN07:** Cliente com dívida pode comprar de novo? Não existe regra fixa. O sistema **avisa** quanto o cliente deve, e quem está vendendo decide. A venda não é bloqueada.
- **RN08:** Venda e parcela pagas não são apagadas. O histórico fica guardado (substitui guardar a promissória).
- **RN09:** Clientes com o mesmo nome são comuns, e não tem CPF. A diferença está no endereço e no ponto de referência, então a busca de clientes mostra o endereço junto do nome.
- **RN10:** Existem dois tipos de observação: a do **cliente** (ponto de referência, que não muda) e a da **venda** (ex.: "só paga depois do dia 10").
- **RN11:** As vendas podem ser registradas **sem internet** e em **celulares diferentes**. Os dados são juntados depois.
- **RN12:** A parcela é paga inteira. Receber só uma parte é muito raro, então fica fora do MVP (ver abaixo).

## O que entra no MVP

- Cadastro de clientes e produtos
- Registro de venda com produtos e parcelas
- Marcar parcela como paga
- **Lista de quem está devendo**, com as parcelas atrasadas primeiro (resolve o problema 1)
- Histórico de compras do cliente
- Aviso de dívida ao vender para um cliente que deve (RN07)

## Fora do MVP (fica para depois)

- Relatórios de vendas e recebimentos por período
- Login e autenticação
- Filtro de devedores por bairro (para montar a rota de cobrança)
- App Android offline com sincronização (repositório separado)
- Receber só uma parte de uma parcela (RN12)
- Mais de 2 parcelas por venda

## Decisões técnicas que vêm dos requisitos

- **IDs em UUID** em vez de auto incremento, por causa da RN11: o celular cria o registro sem falar com o servidor, e dois aparelhos não podem gerar o mesmo id.
- **Datas de criação e atualização** em todas as entidades, para a sincronização saber o que mudou.
- **`BigDecimal`** para valores em dinheiro.

## Dúvidas em aberto

Nenhuma no momento.
