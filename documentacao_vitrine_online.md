---
title: Documentação da Vitrine Online para Loja de Roupas
---

# 1. Objetivo do Projeto

Criar uma vitrine online para uma loja de roupas, que permita exibir
produtos com informações detalhadas, sem funcionalidades de e-commerce
(não haverá carrinho ou checkout). O foco é apresentação visual e
interação com IA para personalização.

# 2. Funcionalidades Principais

## 2.1. Área Pública (Vitrine)

\- Exibição de produtos com:

• Nome\
• Avaliação (estrelas ou nota)\
• Valor e formas de pagamento (ex.: cartão, PIX)\
• Tamanhos disponíveis\
• Informações do produto:\
- Material\
- Tipo (ex.: camiseta, calça)\
- Estampa (Lisa ou estampada)

\- Visualização detalhada do produto:

• Galeria de imagens\
• Descrição completa

\- Função IA para cliente:

• Upload de foto do corpo inteiro → aplicação veste a roupa escolhida na
foto do cliente.

## 2.2. Área Administrativa

\- Gestão de clientes:

• Cadastro, edição, exclusão\
• Histórico de interações

\- Gestão de produtos:

• Cadastro com IA:\
- Remoção automática do fundo da foto (padronização)\
- Aplicação da roupa em modelo virtual\
• Edição e exclusão

\- Gestão de promoções:

• Criar, editar e remover promoções\
• Definir período e produtos aplicáveis

# 3. Requisitos Técnicos

\- Backend: PHP com framework Laravel\
- Banco de Dados: MySQL\
- Frontend: Bootstrap + jQuery\
- Layout: Seguir padrão visual do site https://www.divinafitness.com.br/

# 4. Integração com IA

\- Ferramenta: Freepik API (docs.freepik.com)

\- Principais funções:

• Cadastro de produto:\
- Remover fundo da imagem e padronizar\
- Vestir modelo virtual com a roupa cadastrada\
• Personalização para cliente:\
- Aplicar roupa escolhida na foto enviada pelo cliente (corpo inteiro)

# 5. Estrutura das Telas

5.1. Vitrine:

• Página inicial com categorias\
• Página de produto com detalhes e botão "Provar Virtualmente"\
• Upload de foto para prova virtual

5.2. Admin:

• Dashboard com métricas básicas\
• CRUD para clientes, produtos e promoções\
• Tela de upload com integração IA (Freepik)

# 6. Fluxo de Cadastro de Produto

1\. Admin faz upload das fotos.\
2. IA remove fundo e padroniza.\
3. IA aplica roupa em modelo virtual.\
4. Admin completa informações (nome, preço, tamanhos, material, tipo,
estampa).\
5. Produto é publicado na vitrine.

# 7. Segurança

\- Autenticação via Laravel Auth para área administrativa.\
- Proteção contra upload malicioso (validação de arquivos).\
- HTTPS obrigatório.

# 8. Escalabilidade

\- Estrutura modular para futura integração com e-commerce.\
- API REST para integração com outros sistemas.
