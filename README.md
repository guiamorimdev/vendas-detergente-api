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

## 🤖 Sobre o desenvolvimento

Este é um projeto de estudo, feito para praticar e ganhar experiência em desenvolvimento backend com Java. Ele está sendo desenvolvido com a ajuda do [Claude](https://claude.ai) (IA da Anthropic), que uso como apoio para tirar dúvidas, revisar código e orientar as decisões ao longo do caminho.

## ▶️ Como rodar

_Em breve._

## 📄 Licença

Distribuído sob a licença presente no arquivo [LICENSE](LICENSE).
