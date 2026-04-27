📝 Murilo-Blog - Blog Engine

Este é um sistema de gerenciamento de blog completo, desenvolvido em Python com o framework Flask. O projeto conta com autenticação de usuários, níveis de acesso (Admin), sistema de comentários com integração de avatars e um editor de texto rico para as postagens.

🚀 Funcionalidades

Autenticação Completa: Cadastro e login de usuários com senhas criptografadas via Werkzeug.

Controle de Acesso (RBAC): Decorador personalizado para restringir criação, edição e exclusão de posts apenas ao administrador (ID 1).

Sistema de Comentários: Usuários logados podem comentar em postagens.

Relacionamentos SQL: Banco de dados relacional com integridade garantida via cascade delete (ao excluir um post, os comentários associados são removidos automaticamente).

Editor Rich Text: Integração com CKEditor para formatação de posts.

Avatares Dinâmicos: Uso do Flask-Gravatar para exibir fotos de perfil baseadas no e-mail do usuário.

Configuração via Ambiente: Totalmente configurado via variáveis de ambiente (.env).

🛠️ Tecnologias Utilizadas

Linguagem: Python 3.8+

Framework Web: Flask

Banco de Dados: SQLAlchemy (SQLite por padrão)

Frontend: Flask-Bootstrap5 e Jinja2

Formulários: Flask-WTF

📋 Pré-requisitos

Antes de começar, você precisará ter o Python instalado em sua máquina.

Bash

# Clone o repositório
git clone https://github.com/murilo-suhett/Murilo-Blog.git

# Entre na pasta
cd Murilo-Blog

# Crie um ambiente virtual
python -m venv .venv

# Ative o ambiente
# No Linux/Mac:
source .venv/bin/activate
# No Windows:
.venv\Scripts\activate

# Instale as dependências
pip install -r requirements.txt
⚙️ Configuração (Variáveis de Ambiente)
Crie um arquivo .env na raiz do projeto e adicione as seguintes chaves:

Plaintext

FLASK_KEY=sua_chave_secreta_aqui
DATABASE_URL=sqlite:///posts.db
FLASK_DEBUG=1
🏃 Como rodar a aplicação
Com o ambiente virtual ativo e o .env configurado, execute:

Bash

python main.py
O servidor iniciará em http://127.0.0.1:5002.

Nota sobre Admin: O primeiro usuário cadastrado no sistema (ID 1) terá permissões de administrador para gerenciar postagens.

🏗️ Estrutura do Banco de Dados
O banco de dados possui três tabelas principais relacionadas:

Users: Armazena informações dos usuários.

BlogPosts: Conteúdo das postagens (relacionado ao autor).

Comments: Comentários vinculados tanto a um autor quanto a um post específico.
