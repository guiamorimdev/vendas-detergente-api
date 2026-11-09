# 🧴 Vendas Detergente — API

API REST para gestão de vendas de detergentes: cadastro de clientes e produtos, registro de pedidos e controle de pagamentos e parcelas, substituindo as promissórias de papel.

O projeto nasceu para ajudar meu pai no dia a dia das vendas. A API é a primeira parte. Depois vem um app Android que funciona **offline** e sincroniza com ela quando houver internet.

> 🚧 **Status:** em desenvolvimento (levantamento de requisitos e modelagem)

## 🎯 Funcionalidades planejadas

- Cadastro de clientes e produtos
- Registro de pedidos com itens (guardando o preço no momento da venda)
- Pagamentos parciais e parcelas
- Saldo devedor por cliente e lista de inadimplentes
- Relatórios de vendas e recebimentos por período
- Autenticação, com cada vendedor acessando somente os próprios dados

## 🛠️ Tecnologias

- Java 21 + Spring Boot 3
- Spring Data JPA + MySQL
- Flyway (migrations)
- Bean Validation
- JUnit 5, Mockito e Testcontainers
- Spring Security + JWT
- springdoc-openapi (Swagger)
- Docker
- Maven

## 🗺️ Roadmap

- [ ] Levantamento de requisitos (`docs/requisitos.md`)
- [ ] Modelagem das entidades e relacionamentos
- [ ] Estrutura base do projeto Spring Boot + conexão com MySQL
- [ ] Persistência com JPA e migrations Flyway
- [ ] Endpoints REST (clientes, produtos, pedidos, pagamentos)
- [ ] Regras de negócio (saldo devedor, inadimplência, relatórios)
- [ ] Testes unitários e de integração
- [ ] Documentação com Swagger
- [ ] Autenticação com Spring Security + JWT
- [ ] Docker e deploy
- [ ] App Android (Java) offline com sincronização — repositório separado

## ▶️ Como rodar

_Em breve._

## 📄 Licença

Distribuído sob a licença presente no arquivo [LICENSE](LICENSE).
