# API de Autenticação com Spring Security e JWT 🔐

Esta API foi desenvolvida em Java 21 com Spring Boot, implementando autenticação e autorização usando Spring Security e JWT (JSON Web Token). O objetivo é fornecer uma solução simples e segura para controle de acesso em aplicações web.

## 📋 Funcionalidades

* Registro de novos usuários.
* Login com autenticação via JWT.
* Proteção de rotas utilizando Spring Security.
* Renovação de token JWT.
* Validação de permissões com base em roles.

## 🚀 Tecnologias

* Java 21: Linguagem de programação utilizada.
* Spring Boot: Framework para construção da API.
* Spring Security: Gerenciamento de autenticação e autorização.
* JWT: Para geração e validação de tokens.
* Maven: Gerenciador de dependências.
* Banco de Dados: H2/MySQL/PostgreSQL (dependendo do ambiente).

### 🛠️ Pré-requisitos

Antes de começar, você precisará ter instalado em sua máquina:

* JDK 21

## 🎲 Rodando o Projeto

Clonando o repositorio
```
git clone https://github.com/bfrjunior/projeto-login-auth-api.git
```
Acesse o diretório do projeto
```
cd projeto-login-auth-api
```
Configure as variáveis de ambiente (caso necessário):

Configurações de banco de dados e JWT podem ser definidas no arquivo application.properties.
Execute a aplicação.
A API estará disponível em http://localhost:8080

## 🔑 Endpoints Principais
Registro de Usuário:

* URL: /api/register
* Método: POST
* Corpo da requisição: JSON com os dados do usuário (nome, email, senha).

Login:

* URL: /api/login
* Método: POST
* Corpo da requisição: JSON com email e senha.
* Resposta: Token JWT.

Acesso a Rotas Protegidas:

* URL: /api/protected-route
* Método: GET
* Requer o token JWT no cabeçalho: Authorization: Bearer {token}

## 🔐 Configuração de Segurança
A segurança da aplicação é gerenciada por um filtro personalizado, que verifica a validade do token JWT e autentica o usuário. A classe SecurityFilter realiza o seguinte processo:

* Recupera o token JWT do cabeçalho Authorization.
* Valida o token e identifica o usuário.
* Autentica o usuário no contexto de segurança do Spring.