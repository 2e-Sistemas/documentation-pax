---
title: Endpoint para Criação de Pedido Funerário
slug: /funeraria/endpoint-criar-pedido-funerario
---

# Endpoint para Criação de Pedido Funerário

---

## Visão Geral

Este guia descreve como criar um endpoint para permitir a criação de pedidos funerários em nosso sistema. O endpoint receberá os dados necessários no formato JSON e retornará uma resposta indicando o sucesso ou falha da operação. No final desse guia teremos duas interfaces.

:::danger
**Atenção desenvolvedor:** vários itens nesse documento foram gerados por I.A, por enquanto para maior produtividade e rapidez da equipe esse guia é apenas um ponta pé inicial, facilita seu trabalho mas mudanças podem ser necessárias!
:::

## Especificações do Endpoint

- **Rota:** `/funeral/funeral-request/create`
- **Método HTTP:** POST
- **Tipo de Conteúdo:** JSON

## Payload da Requisição

O payload da requisição deve conter as seguintes informações:

```json
{
  "customer_id": "string",
  "contract_id": "string",
  "declarant_id": "string",
  "relationship_id": "string",
  "deceased_info": {
    "name": "string",
    "cpf": "string",
    "birthdate": "string (formato: YYYY-MM-DD)",
    "date_of_death": "string (formato: YYYY-MM-DD)",
    "place_of_death": "string",
    "burial_location": "string",
    "funeral_place": "string",
    "cause_of_death": "string",
    "religion": "string"
  },
  "insurance_info": {
    "is_insurance": "boolean",
    "policy_number": "string",
    "invoice_number": "string"
  },
  "products": [
    {
      "name": "string",
      "price": "number",
      "quantity": "number"
    }
  ],
  "payment_options": [
    {
      "name": "string",
      "amount": "number"
    }
  ],
  "funeral_arrangement_id": "string",
  "notes": "string"
}
```

Resposta da Requisição
A resposta da requisição pode conter os seguintes campos:

- Success: Indica se a operação foi bem-sucedida.
- Message: Mensagem indicando o resultado da operação.
- Data: Dados adicionais, se necessário.

Exemplo de resposta de sucesso:

```json
{
  "success": true,
  "message": "Pedido funeral criado com sucesso.",
  "data": funeralRequest
}
```

Exemplo de resposta de erro:

```json
{
  "success": false,
  "message": "Erro ao criar pedido funeral: dados para o desenvolvedor",
  "error": "Será printado na tela do cliente, especificar o máximo possível"
}
```

## Interface ICreateFuneralRequest

```typescript
interface ICreateFuneralRequest {
  customer_id: string
  contract_id: string
  declarant_id: string
  relationship_id: string
  deceased_info: {
    name: string
    cpf: string
    birthdate: string // Format: YYYY-MM-DD
    date_of_death: string // Format: YYYY-MM-DD
    place_of_death: string
    burial_location: string
    funeral_place: string
    cause_of_death: string
    religion: string
  }
  insurance_info: {
    is_insurance: boolean
    policy_number: string
    invoice_number: string
  }
  products: {
    name: string
    price: number
    quantity: number
  }[]
  payment_options: {
    name: string
    amount: number
  }[]
  funeral_arrangement_id: string
  notes: string
}
```

## Interface IFuneralRequest

```typescript
interface IFuneralRequest {
  id: string
  deceased_customer_id: string
  customer_id: string
  contract_id: string
  declarant_id: string
  declarant_relationship_id: string
  amount: number
  burial_location_id: string
  insurance_policy_number: string
  funeral_arrangements_id: string
  active: boolean
  deleted: boolean
  tenant_id: string
  updated_at: Date
  created_at: Date
  teste: string
}
```

## req.body

| Campo                  | Obrigatório | Tipo   | Descrição                                             |
| ---------------------- | ----------- | ------ | ----------------------------------------------------- |
| customer_id            | Sim         | String | ID do cliente associado ao pedido funeral.            |
| contract_id            | Sim         | String | ID do contrato relacionado ao pedido funeral.         |
| declarant_id           | Sim         | String | ID do declarante associado ao pedido funeral.         |
| relationship_id        | Sim         | String | ID do relacionamento entre o declarante e o falecido. |
| deceased_info          | Sim         | Objeto | Informações sobre o falecido.                         |
| insurance_info         | Não         | Objeto | Informações sobre o seguro, se aplicável.             |
| products               | Sim         | Array  | Lista de produtos/serviços no pedido funeral.         |
| payment_options        | Não         | Array  | Opções de pagamento para o pedido funeral.            |
| funeral_arrangement_id | Não         | String | ID do arranjo funerário, se aplicável.                |
| notes                  | Não         | String | Observações adicionais sobre o pedido funeral.        |

Espero que este guia seja útil para implementar com sucesso o endpoint para criação de pedidos funerários em nosso sistema!
