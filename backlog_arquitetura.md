---
title: Projeto Vitrine Online - Backlog, Plano de Desenvolvimento e
  Arquitetura
---

# 1. Backlog Técnico

Abaixo estão os épicos e histórias de usuário para o projeto da vitrine
online:

## Épicos:

\- Exibição de produtos na vitrine

\- Prova virtual com IA

\- Gestão administrativa (clientes, produtos, promoções)

\- Integração com IA para cadastro de produtos

## Histórias de Usuário:

Como cliente, quero visualizar produtos com detalhes para escolher
melhor.

Como cliente, quero enviar minha foto e ver a roupa aplicada para
simular a compra.

Como administrador, quero cadastrar produtos com remoção automática de
fundo.

Como administrador, quero gerenciar promoções para aumentar vendas.

# 2. Plano de Desenvolvimento

O plano está dividido em sprints para melhor organização:

## Sprint 1:

\- Configuração do ambiente (Laravel, MySQL)

\- Criação da estrutura do banco de dados

\- Desenvolvimento da área pública básica (listagem de produtos)

## Sprint 2:

\- Implementação da área administrativa (CRUD de produtos e clientes)

\- Integração inicial com IA para remoção de fundo

## Sprint 3:

\- Implementação da prova virtual para clientes

\- Ajustes de layout conforme padrão do site Divina Fitness

## Sprint 4:

\- Segurança (Laravel Auth, HTTPS)

\- Testes e otimizações finais

# 3. Arquitetura do Sistema

A arquitetura do sistema é composta pelos seguintes componentes:

\- Frontend: Bootstrap + jQuery

\- Backend: PHP (Laravel)

\- Banco de Dados: MySQL

\- Serviços de IA: Freepik API para remoção de fundo e prova virtual

\- Segurança: Autenticação Laravel Auth, HTTPS obrigatório

## Diagrama da Arquitetura

Abaixo está o diagrama visual da arquitetura do sistema:

![](media/image1.png){width="5.0in" height="3.3333333333333335in"}
