# Documentação da API de Checkout VTEX (Headless)

## Introdução

Esta documentação descreve as APIs de checkout da VTEX para implementações headless, permitindo operações essenciais de e-commerce como pagamento e finalização de pedido.

## APIs Documentadas

### 1. Attachment PaymentData

- **Método**: POST
- **URL**: `https://{{accountName}}.myvtex.com/api/checkout/pub/orderForm/{{orderFormId}}/attachments/paymentData`
- **Headers**:
  - Accept: `application/vnd.vtex.ds.v10+json`
  - Content-Type: `application/json`
- **Body**: Inclui dados de pagamento.

### 2. Create Transaction

- **Método**: POST
- **URL**: `https://{{accountName}}.myvtex.com/api/checkout/pub/orderForm/{{orderFormId}}/transaction`
- **Headers**:
  - Accept: `application/vnd.vtex.ds.v10+json`
  - Content-Type: `application/json`
  - X-VTEX-API-AppKey: `{{appKey}}`
  - X-VTEX-API-AppToken: `{{appToken}}`
- **Body**: Inclui informações da transação.

### 3. Create Payment

- **Método**: POST
- **URL**: `https://{{accountName}}.vtexpayments.com.br/api/pvt/transactions/{{transactionId}}/payments`
- **Headers**:
  - Accept: `application/vnd.vtex.ds.v10+json`
  - Content-Type: `application/json`
  - X-VTEX-API-AppKey: `{{appKey}}`
  - X-VTEX-API-AppToken: `{{appToken}}`
- **Body**: Inclui detalhes do pagamento.

### 4. Finish Payment

- **Método**: POST
- **URL**: `https://{{accountName}}.myvtex.com/api/checkout/pub/gatewayCallback/{{orderGroup}}`
- **Headers**:
  - Accept: `application/vnd.vtex.ds.v10+json`
  - Content-Type: `application/json`
- **Body**: Vazio (indicativo de finalização do pagamento).

## Variáveis da Collection

- `accountName`: Nome da conta VTEX.
- `orderFormId`: ID do formulário de pedido.
- `transactionId`: ID da transação.
- `orderGroup`: Grupo de pedido.
- `appKey`: Chave da API da VTEX.
- `appToken`: Token da API da VTEX.
- `redemptionCode`: Código de resgate do GiftCard.
- `giftCardProvider`: Provedor do GiftCard.
- `orderValue`: Valor do pedido em centavos.
- `giftCardId`: ID do GiftCard na VTEX.

## Considerações Finais

Esta documentação cobre as principais APIs de checkout da VTEX para implementações headless, fornecendo detalhes essenciais para integração e funcionamento eficaz em plataformas de e-commerce.
