---
title: Tabelas Principais
slug: /funeraria/tabelas
---

# Tabelas principais referentes aos módulo de funerária

Atenção, desenvolvedor 👀! Este não é um diagrama definitivo, mas sim um documento construído em colaboração contínua. Seu principal objetivo é aumentar a produtividade na criação de novos endpoints e na manutenção do sistema, tanto em fase de desenvolvimento quanto em fase de produção. 🚀

### Tabela `funeral_requests` (Pedidos Funerários)

| Campo                     | Descrição                                                                    |
| ------------------------- | ---------------------------------------------------------------------------- |
| id                        | Identificador único do pedido funerário.                                     |
| deceased_customer_id      | ID do cliente falecido associado ao pedido.                                  |
| customer_id               | ID do cliente responsável pelo pedido.                                       |
| contract_id               | ID do contrato relacionado ao pedido.                                        |
| declarant_id              | ID do declarante (referenciando a tabela `customers`).                       |
| declarant_relationship_id | ID do relacionamento do declarante (referenciando a tabela `relationships`). |
| amount                    | Valor do pedido.                                                             |
| burial_location_id        | ID do local de sepultamento.                                                 |
| insurance_policy_number   | Número da apólice de seguro.                                                 |
| funeral_arrangements_id   | ID dos arranjos funerários.                                                  |
| active                    | Indicador de ativo.                                                          |
| deleted                   | Indicador de excluído.                                                       |

### Tabela `deceased_customers` (Clientes Falecidos)

| Campo             | Descrição                                |
| ----------------- | ---------------------------------------- |
| id                | Identificador único do cliente falecido. |
| customer_id       | ID do cliente associado.                 |
| death_date        | Data do falecimento.                     |
| place_of_death    | Local do falecimento.                    |
| burial_time       | Horário do sepultamento.                 |
| burial_place      | Local do sepultamento.                   |
| funeral_place     | Local do velório.                        |
| age_at_death      | Idade do falecido.                       |
| cause_of_death    | Causa da morte.                          |
| religion_deceased | Religião do falecido.                    |
| active            | Indicador de ativo.                      |
| delete            | Indicador de excluído.                   |

### Tabela `products` (Produtos)

| Campo  | Descrição                              |
| ------ | -------------------------------------- |
| id     | Identificador único do produto.        |
| old_id | ID antigo do produto.                  |
| name   | Nome do produto.                       |
| price  | Preço do produto.                      |
| stock  | Estoque do produto.                    |
| etc... | Outros campos relacionados ao produto. |

### Tabela `funeral_request_items` (Itens do Pedido Funerário)

| Campo              | Descrição                   |
| ------------------ | --------------------------- |
| funeral_request_id | ID do pedido funerário.     |
| product_id         | ID do produto.              |
| price              | Preço do produto no pedido. |

### Tabela `burial_locations` (Locais de Sepultamento)

| Campo   | Descrição                                     |
| ------- | --------------------------------------------- |
| id      | Identificador único do local de sepultamento. |
| etapa   | Etapa do local.                               |
| quadra  | Quadra do local.                              |
| alameda | Alameda do local.                             |
| jazigo  | Jazigo do local.                              |
| gaveta  | Gaveta do local.                              |
| bloco   | Bloco do local.                               |
| galeria | Galeria do local.                             |
| active  | Indicador de ativo.                           |
| deleted | Indicador de excluído.                        |

### Tabela `funeral_arrangements` (Arranjos Funerários)

| Campo   | Descrição                                 |
| ------- | ----------------------------------------- |
| id      | Identificador único do arranjo funerário. |
| name    | Nome do arranjo.                          |
| active  | Indicador de ativo.                       |
| deleted | Indicador de excluído.                    |
