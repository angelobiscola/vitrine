# Documentação Técnica - Projeto Vitrine Online

## 1. Modelo de Banco de Dados (ER - Entidade Relacionamento)

O banco de dados da aplicação Vitrine Online foi modelado para suportar
a gestão de produtos, clientes, promoções e histórico de interações. A
seguir está a estrutura conceitual das principais tabelas e seus
relacionamentos.

Tabelas Principais:\
\
1. produtos\
- id (PK)\
- nome (VARCHAR 150)\
- descricao (TEXT)\
- preco (DECIMAL 10,2)\
- tamanhos (JSON)\
- material (VARCHAR 100)\
- tipo (VARCHAR 100)\
- estampa (VARCHAR 50)\
- avaliacao (FLOAT)\
- imagens (JSON)\
- criado_em (TIMESTAMP)\
- atualizado_em (TIMESTAMP)\
\
2. clientes\
- id (PK)\
- nome (VARCHAR 150)\
- email (VARCHAR 150)\
- telefone (VARCHAR 20)\
- foto (VARCHAR 255)\
- criado_em (TIMESTAMP)\
\
3. promocoes\
- id (PK)\
- titulo (VARCHAR 150)\
- descricao (TEXT)\
- desconto_percentual (INT)\
- data_inicio (DATE)\
- data_fim (DATE)\
- produtos_aplicaveis (JSON)\
- criado_em (TIMESTAMP)\
\
4. interacoes\
- id (PK)\
- cliente_id (FK → clientes.id)\
- produto_id (FK → produtos.id)\
- tipo_interacao (ENUM: \'visualizacao\', \'prova_virtual\',
\'favorito\')\
- data (TIMESTAMP)\
\
5. usuarios_admin\
- id (PK)\
- nome (VARCHAR 150)\
- email (VARCHAR 150)\
- senha (HASH)\
- criado_em (TIMESTAMP)

## 2. API REST - Endpoints e Estrutura

A API segue o padrão RESTful, implementada em Laravel. Todas as rotas da
área administrativa são protegidas por autenticação (Laravel Auth).

Endpoints Públicos (Vitrine):\
GET /api/produtos → Lista todos os produtos disponíveis.\
GET /api/produtos/{id} → Retorna detalhes de um produto específico.\
POST /api/prova-virtual → Recebe a foto do cliente e aplica a roupa
selecionada (integração IA).\
\
Endpoints Administrativos:\
POST /api/login → Autenticação do administrador.\
POST /api/produtos → Cadastra um novo produto (com integração IA de
remoção de fundo).\
PUT /api/produtos/{id} → Atualiza informações de um produto.\
DELETE /api/produtos/{id} → Remove um produto.\
GET /api/clientes → Lista todos os clientes cadastrados.\
POST /api/promocoes → Cria uma nova promoção.\
PUT /api/promocoes/{id} → Atualiza uma promoção.\
DELETE /api/promocoes/{id} → Exclui uma promoção.

## 3. Integração com IA - Freepik API

A integração com a API da Freepik será utilizada para processar imagens
(remoção de fundo e simulação de prova virtual).

Fluxo de Cadastro de Produto (com IA):\
1. Admin envia imagem do produto (POST /api/produtos).\
2. O backend faz requisição à Freepik API para remover o fundo e
padronizar a imagem.\
3. A imagem processada é salva no servidor e associada ao produto no
banco de dados.\
4. O produto é exibido na vitrine.\
\
Fluxo de Prova Virtual:\
1. Cliente faz upload de uma foto do corpo inteiro (POST
/api/prova-virtual).\
2. O backend envia a imagem para a Freepik API junto com a roupa
escolhida.\
3. A IA retorna uma nova imagem com a roupa aplicada ao corpo do
cliente.\
4. O sistema exibe a simulação na interface da vitrine.\
\
Configuração Técnica:\
- Endpoint base: https://api.freepik.com/v1/\
- Autenticação: Bearer Token (chave fornecida pela conta Freepik)\
- Métodos principais:\
• POST /image/remove-background\
• POST /image/virtual-tryon\
- Tipo de upload: multipart/form-data\
- Resposta esperada: JSON com URL da imagem processada.

## 4. Requisitos de Ambiente e Deploy

\- Linguagem: PHP 8.1+\
- Framework: Laravel 10+\
- Banco de Dados: MySQL 8.0\
- Frontend: Bootstrap 5 + jQuery\
- Servidor Web: Apache ou Nginx\
- HTTPS obrigatório (Let\'s Encrypt recomendado)\
- Extensões PHP necessárias: fileinfo, curl, mbstring, json, openssl.\
- Armazenamento de imagens: /storage/app/public/produtos
