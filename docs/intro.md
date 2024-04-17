---
sidebar_position: 1
---

# Bem-vindo ao Pax ERP! 🚀

O Pax ERP é uma plataforma robusta e escalável desenvolvida para atender às necessidades de gestão de funerárias de forma eficiente e moderna. Aqui está uma visão geral da nossa arquitetura e das tecnologias utilizadas:

## Tecnologias Principais

### Banco de Dados

Utilizamos o [MariaDB](https://mariadb.org/) como nosso banco de dados relacional. Ele oferece desempenho e confiabilidade para armazenar e gerenciar os dados essenciais do sistema.

### Backend

No backend, optamos por utilizar [Node.js](https://nodejs.org/) em conjunto com [TypeScript](https://www.typescriptlang.org/). Essa combinação nos proporciona uma base sólida para desenvolver aplicações robustas e escaláveis, aproveitando os benefícios do JavaScript moderno e a segurança do TypeScript.

Para interagir com o banco de dados de forma eficiente, utilizamos o [Knex.js](https://knexjs.org/) como nosso query builder.

### Frontend

No frontend, adotamos o [Vue.js](https://vuejs.org/) como framework principal para construir interfaces de usuário dinâmicas e responsivas. Além disso, utilizamos JavaScript e o gerenciador de estado [Pinia](https://pinia.esm.dev/) para garantir uma gestão eficiente dos estados da aplicação.

### Princípios de Engenharia de Software

Buscamos aplicar importantes paradigmas da engenharia de software, como [DDD (Domain-Driven Design)](https://martinfowler.com/tags/domain%20driven%20design.html) e [Clean Code](https://cleancoders.com/), para garantir uma arquitetura sólida e um código limpo e de fácil manutenção. Além disso, implementamos alguns padrões de design, como Observers, para tornar nosso sistema mais flexível e extensível.

### Escalabilidade e Hospedagem

Para garantir a escalabilidade e disponibilidade da nossa aplicação, hospedamos nossos serviços em duas provedoras de nuvem: [DigitalOcean](https://www.digitalocean.com/) e [AWS](https://aws.amazon.com/), sendo esta última nossa principal provedora.

### Testes Automatizados

Em breve iremos implementar teste automatizador para garantir a qualidade do nosso software implementando. Isso nos permite identificar e corrigir problemas rapidamente, garantindo uma experiência confiável para nossos usuários.

## Próximos Passos

Estamos sempre em busca de melhorias e inovações. Nosso próximo passo é implementar filas para gerenciar melhor o poder computacional, proporcionando uma experiência ainda mais rápida e eficiente aos nossos usuários.

Obrigado por fazer parte da jornada Pax ERP!
