Ceramic Resources Management - Infra

Este repositório contém a Infraestrutura como Código (IaC) para orquestrar o sistema Ceramic.
Utiliza Docker Compose e Caddy para gerenciar Backend, Frontend e Banco de Dados com HTTPS automático.

Estrutura de Pastas Necessária

Para que este setup funcione, sua estrutura de diretórios na máquina host (Dev ou VPS) deve ser:

/pasta-raiz/
├── ceramic-resources-management/          (Repo Backend)
├── ceramic-resources-management-frontend/ (Repo Frontend)
└── ceramic-resources-management-infra/    (Este Repo)
    ├── docker-compose.yml
    ├── Caddyfile
    └── .env


Como Rodar

Clone os 3 repositórios para a mesma pasta pai.

Entre na pasta de infra:

cd ceramic-resources-management-infra


Crie o arquivo de variáveis:

cp .env.example .env


Edite o .env:

Dev: Mantenha SITE_ADDRESS=localhost.

Prod: Mude para SITE_ADDRESS=seudominio.com.br.

Suba o ambiente:

docker compose up -d


Acessando

Web: https://localhost (ou seu domínio)

API: https://localhost/api/... (redireciona internamente para o backend)

Logs: docker compose logs -f