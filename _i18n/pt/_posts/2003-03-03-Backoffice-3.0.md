---
layout: tutorial
title:  "Backoffice API 3.0 Cielo"
description: O objetivo deste documento é orientar o lojista sobre como acessar Backoffice da API Cielo Ecommerce. Descrevendo as funcionalidades, os métodos a serem utilizados, listando informações necessárias e provendo exemplos.
search: true
categories: tutorial
tags:
  - API Cielo
toc_footers:
  - <a href='/Webservice-3.0/'>Integração API Cielo eCommerce</a>
  - <a href='/Checkout-FAQ/'>Perguntas Frequentes</a>
---

# Backoffice API Cielo

O objetivo deste documento é orientar o lojista sobre como acessar Backoffice da API Cielo Ecommerce. Descrevendo as funcionalidades, os métodos a serem utilizados, listando informações necessárias e provendo exemplos.

## Visão Geral

O Backoffice da API Cielo Ecommerce permite que o lojista possa acessar 4 menus com diferentes funcionalidades:

1. **Área do desenvolvedor Cielo** – Onde desenvolvedores podem acessar informações como manuais de integração, FAQs e suporte
2. **Pesquisa de transações** – Busca todas as transações executadas pela loja e exibe como captura ou cancelar transações
3. **Extrato de cobrança** – Detalha os valores cobradas pela a Cielo por cada função utilizada na API Cielo Ecommerce.
4. **Configuração da recorrência** – Alterar quantidades de tentativas de execução de recorrências em caso de cartão negado.

## Acessando o Backoffice

Para acessar o Backoffice, é necessário que o lojista realize login no Site Cielo, inserindo sua Afiliação (Nº de estabelecimento) e Usuário:

![Acessando o Backoffice]({{ site.baseurl_root }}/images/i0.png)

![Acessando o Backoffice]({{ site.baseurl_root }}/images/i1.png)

Em seguida é necessário incluir sua Senha:

![Acessando o Backoffice]({{ site.baseurl_root }}/images/i2.png)

Na área de “Vendas Online” basta clicar em Webservice 3.0

![Acessando o Backoffice]({{ site.baseurl_root }}/images/i3.png)

Você será direcionado para o Backoffice:

![Acessando o Backoffice]({{ site.baseurl_root }}/images/i4.png)

Nesta área você pode acessar as outras funcionalidades do Backoffice

## Acessando a área do Desenvolvedor

Clique no link destacado abaixo:

![Desenvolvedor]({{ site.baseurl_root }}/images/i45.png)

Você será redirecionado para <https://www.cielo.com.br/desenvolvedores/>

# Pesquisando e editando transações

## Pesquisar Transações

Ao acessar a opção abaixo:

![Pesquisa de transações]({{ site.baseurl_root }}/images/i5.png)

Você será direcionado a tela de pesquisa de transações:

![Pesquisa de transações]({{ site.baseurl_root }}/images/i6.png)

Essa tela permite buscar todas as transações realizadas com sucesso na API Cielo Ecommerce e realizar a captura ou cancelamento de transações.

Sobre os Filtros:

|Filtros|Descrição|
|-------|---------|
|Tid| Identificador da transação Cielo. Retornado via response e disponivel no site Cielo|
|EC| Número da Afiliação Cielo|
|Payment Id| Identificador da transação e-commerce|
|Número do Pedido| Número do pedido enviado pelo lojista|
|NSU| Identificação da autorização. Enviado via response|
|Código de Erro| Código retornado caso uma transação gere um erro.|
|Status da Transação|**Cancelado** - Transação cancelada pelo lojista<br>**Estornado** - Transações canceladas com menos de 24 horas<br>**Não Autorizado** - Transações negadas pelo Autorizador Cielo<br>**Não Pago** - Transações autorizadas, mas não capturadas<br>**Pago** - Transações capturadas<br>|
|Tipos de meio de pagamento | Grupo de meios de pagamento como Boletos ou cartão de crédito. Não diferencia |bandeira ou banco.|
|Meios de pagamento| Meio de pagamento especifico usado na transação (EX: Boleto Bradesco)|
|Análise de Fraude| Qual o status de antifraude da transação no momento da pesquisa|

Os filtros podem ser combinados para realizar uma pesquisa personalizada.

## Capturando ou Cancelando Transações

Ao realizar uma pesquisa, é possível realizar a captura ou cancelamento de transações. Ao identificar a transação que deseje cancelar ou capturar:

![capturando transações]({{ site.baseurl_root }}/images/i7.png)

![capturando transações]({{ site.baseurl_root }}/images/i8.png)

Basta realizar o cancelamento ou a Captura (O botão apresentado depende do status da transação no momento de exibição.

![capturando transações]({{ site.baseurl_root }}/images/i9.png)

Confirme o valor a ser capturado ou cancelado.
**OBS:** Alterar o valor no menu acima, define o comportamento do Cancelamento/Captura Parcial.

## Capturando ou cancelando Transações em bloco.

Ao realizar uma pesquisa, é possível realizar a captura ou cancelamento de transações em bloco. Basta selecionar quais serão modificadas e clique em “Opções”:

![bloco de transações]({{ site.baseurl_root }}/images/i10.png)

Selecione a opção desejada:

![bloco de transações]({{ site.baseurl_root }}/images/i11.png)

Ao selecionar a opção desejada, você será direcionado a uma tela onde poderá ser definido o valor da captura/cancelamento.

![bloco de transações]({{ site.baseurl_root }}/images/i12.png)

# Utilizando o Extrato

O Extrato de cobrança permite visualizar o valor a ser cobrado pela utilização das funcionalidades da API Cielo Ecommerce. Basta selecionar o mês e ano que se deseja exibir.

![extrato]({{ site.baseurl_root }}/images/i13.png)

Para maiores informações a respeito dos serviços cobrados, entre em contato com nossa equipe de suporte:

* +55 4002-9700 – Capitais e Regiões Metropolitanas
* +55 0800-570-1700 – Demais Localidades
* +55 11 2860-1348 – Internacionais
  * Opção 1 – Suporte técnico;
  * Opção 2 – Credenciamento eCommerce.
* Email: cieloeCommerce@cielo.com.br

# Configurando a Recorrência

A área de configuração da recorrência permite modificar o número e o intervalo das tentativas de transações. Essas tentativas ocorrem quando uma transação (dentro de uma recorrência) é negada. A API Cielo Ecommerce possui a inteligência para identificar esse cenário, e executar uma nova transação.

Acesse a tela de configuração e use o link “**Tipo de pagamento**”:

![Recorrência]({{ site.baseurl_root }}/images/i14.png)

Você será direcionado para a tela de configuração:

![Recorrência]({{ site.baseurl_root }}/images/i15.png)

Nessa tela é possível alterar:

* **Quantidades de tentativas:** Número de vezes a API vai realizar uma nova transação em caso de não autorização dentro de uma recorrência. Limitada a 4 tentativas
* **Intervalo de tentativas:** Espaço de tempo entre a execução de cada nova tentativa de autorização de uma transação dentro de uma recorrência. Limitado a 4 dias entre cada tentativa.
