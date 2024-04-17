---
title: Fluxo para Criar um Pedido Funerário
slug: /funeraria/fluxo-criar-pedido-funerario
---

#Passo a passo da interação do usuário com nosso sistema para preencher um form no estilo step-by-step para criação do pedido funerário.

# Passo a Passo para Criação do Pedido Funerário

---

## Overview

Este guia apresenta o fluxo de interação do usuário para preencher um formulário step-by-step para criação do pedido funerário.

## Passos

### Step 1: Buscar Cliente

- O usuário busca o cliente via CPF ou nome.
- Se encontrar, seleciona o cliente da lista pelo contrato.
- Se não encontrar, abre um modal para cadastrar o cliente (neste caso, o contrato será nulo).

### Step 2: Informar Declarante

- O usuário informa se o declarante é o mesmo que o cliente para auto preenchimento.
- Se não for o mesmo declarante:
  - O usuário busca o cliente via CPF ou nome.
  - Se encontrar, usa os dados dele para preencher os dados pessoais automaticamente.
  - Solicita informações adicionais como grau de parentesco.

### Step 3: Verificar Convênio-Seguro

- Pergunta ao usuário se será convênio-seguro.
- Se for seguro, pede o número da apólice e a nota fiscal.

### Step 4: Modal para Pesquisar Cliente na Base de Dados

- Preenche uma tabela com as colunas:
  - Nome
  - CPF
  - Titular ou dependente do contrato.
- Se a busca retornar resultados esperados, o usuário seleciona uma linha que trará os dados do cliente do falecido.
- Solicita as informações exclusivas do falecido após resolver a questão dos dados pessoais.

### Step 5: Pesquisar Produto ou Serviço

- Input para pesquisar produto ou serviço pelo nome.
- Input para selecionar translados.
- Modal para cadastrar produto.
- Preenche uma tabela com nome e valor do produto automaticamente, permitindo editar o valor.

### Step 6: Selecionar Formas de Pagamento e Convênio Funeral

- Select para escolher uma ou mais formas de pagamento.
- Select para selecionar o convênio funeral (apenas uma opção).
- Input longo para inserir observações.
<!--

## Fluxograma

![Fluxo de Criação do Pedido Funerário](./funeral_request_flowchart.png)

----->

## Payload do Pedido Funeral

## Campos do Payload do Pedido Funeral

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

```json
{
  "customer_id": "id_do_cliente",
  "contract_id": "id_do_contrato",
  "declarant_id": "id_do_declarante",
  "relationship_id": "id_do_relacionamento",
  "deceased_info": {
    "name": "Nome do falecido",
    "cpf": "CPF do falecido",
    "birthdate": "Data de nascimento do falecido",
    "date_of_death": "Data de falecimento do falecido",
    "place_of_death": "Local de falecimento do falecido",
    "burial_location": "Local de sepultamento do falecido",
    "funeral_place": "Local do velório do falecido",
    "cause_of_death": "Causa da morte do falecido",
    "religion": "Religião do falecido"
  },
  "insurance_info": {
    "is_insurance": true,
    "policy_number": "Número da apólice de seguro",
    "invoice_number": "Número da nota fiscal"
  },
  "products": [
    {
      "name": "Nome do produto/serviço",
      "price": "Preço do produto/serviço",
      "quantity": 1
    }
  ],
  "payment_options": [
    {
      "name": "Forma de pagamento",
      "amount": "Valor da forma de pagamento"
    }
  ],
  "funeral_arrangement_id": "id_do_arranjo_funerário",
  "notes": "Observações adicionais"
}
```
