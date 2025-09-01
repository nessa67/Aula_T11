# 📦 Sistema de Controle de Estoque

Sistema simples em **PHP** para gestão de materiais, controle de solicitações e administração de usuários, desenvolvido para um ambiente escolar.

---

## 📖 Visão Geral
Este projeto foi criado para a **Escola Técnica de Enfermagem**, com o objetivo de digitalizar e otimizar o controle de materiais de laboratório.

- Professores e funcionários (**Requisitantes**) podem solicitar materiais.
- A administração (**Administradores**) gerencia o estoque, aprova solicitações e mantém um registro completo.

---

## 🚀 Funcionalidades Principais

### Painel do Administrador
- **Dashboard**: visão geral com estatísticas (solicitações pendentes, itens com estoque baixo).
- **Gerenciar Materiais**: adicionar, editar e visualizar materiais (CRUD).
- **Gerenciar Usuários**: adicionar, editar e desativar usuários (CRUD).
- **Gerenciar Solicitações**: visualizar todas, aprovar/recusar, marcar como **entregue** ou **devolvido**.
- **Relatórios**: exportar a lista de materiais em **CSV**.

### Painel do Requisitante
- **Criar Solicitação**: formulário dinâmico para múltiplos materiais com verificação de estoque em tempo real.
- **Histórico de Solicitações**: acompanhar o status de todas as solicitações feitas.

### Funcionalidades Gerais
- **Sistema de Login Seguro**: autenticação por perfis, senhas **hasheadas**.
- **Controle de Acesso**: cada perfil só acessa o que tem permissão.
- **Log de Auditoria**: registro de ações importantes do sistema.
- **Design Responsivo**: interface adaptável a desktop e dispositivos móveis.

---

## 🛠️ Tecnologias Utilizadas
- **Back-end**: PHP
- **Banco de Dados**: MySQL / MariaDB
- **Front-end**: HTML, CSS, JavaScript (puro)
- **Servidor**: Apache (ou similar)

---

## 📋 Pré-requisitos
Tenha um ambiente de servidor local instalado, como:
- **XAMPP** — https://www.apachefriends.org/
- **WAMP** — https://www.wampserver.com/
- **Laragon** — https://laragon.org/

Também é útil um cliente de banco de dados, como **phpMyAdmin** (vem no XAMPP) ou **HeidiSQL**.

---

## ⚙️ Instalação e Configuração (Passo a Passo)

### 1) Baixar e Extrair o Projeto
- Clique em **Code → Download ZIP** no GitHub para baixar o projeto.
- Extraia o arquivo `.zip` no seu computador.

### 2) Mover para o Servidor Web
- Mova a pasta extraída (ex.: `sistema_estoque-main`) para o diretório raiz do seu servidor web.
  - No **XAMPP** (Windows): `C:/xampp/htdocs/`
- *(Recomendado)* Renomeie a pasta para `sistema_estoque`.

### 3) Configurar o Banco de Dados
1. Inicie **Apache** e **MySQL** no seu painel (ex.: *XAMPP Control Panel*).
2. Acesse: `http://localhost/phpmyadmin`.
3. Crie um novo banco de dados chamado **`escola_enfermagem_estoque`** com **collation** `utf8mb4_general_ci`.
4. Acesse a aba **SQL** do banco criado.
5. Abra o arquivo **`Criar_Base.txt`** do projeto, copie todo o conteúdo.
6. Cole o conteúdo na aba **SQL** e clique em **Executar**.
7. Isso criará todas as tabelas, relacionamentos e o **usuário administrador padrão**.

### 4) Configurar a Conexão com o Banco
Abra o arquivo **`config.php`** na raiz do projeto e ajuste conforme seu ambiente:

```php
define('DB_HOST', 'localhost');
define('DB_PORT', '3306'); // ⚠️ verifique a porta do seu MySQL
define('DB_USER', 'root');
define('DB_PASS', ''); // geralmente vazio no XAMPP
define('DB_NAME', 'escola_enfermagem_estoque');
```

> **Dica:** Caso utilize outra porta do MySQL (por exemplo, `3307`), atualize `DB_PORT` para refletir essa mudança.

### 5) Acessar o Sistema
Abra seu navegador e acesse:
- **http://localhost/sistema_estoque/**

---

## 👥 Como Usar

### Login do Administrador (padrão)
- **E-mail:** `admin@escola.com`
- **Senha:** `admin123`

> **Importante:** Altere a senha do administrador após o primeiro acesso.

### Testar o Fluxo do Requisitante
1. Faça login como **Administrador**.
2. Vá em **Gerenciar Usuários** e crie um novo usuário com o perfil **Requisitante**.
3. Faça **logout** e entre com as credenciais do novo usuário.
4. Crie uma solicitação, acompanhe o status no **Histórico**.

---
