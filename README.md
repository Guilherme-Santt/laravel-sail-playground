# 🐳 Laravel Sail Playground

Este projeto é um laboratório focado em **Laravel Sail**, utilizando o Docker para isolar o ambiente de desenvolvimento sem a necessidade de instalar PHP, MySQL ou servidores localmente.

## 🚀 Como este ambiente foi configurado

O projeto foi criado do zero utilizando a estrutura do Laravel Sail. Abaixo estão os passos principais para replicar este setup:

### 1. Inicialização do Ambiente
O comando inicial utilizado para gerar a estrutura sem PHP local:
    curl -s "[https://laravel.build/nome-do-projeto](https://laravel.build/nome-do-projeto)"

### 2. Comandos de Gerenciamento (Sail)
Para interagir com o Docker de forma simplificada, utilizamos o binário do Sail:

    Subir containers: ./vendor/bin/sail up -d

    Parar containers: ./vendor/bin/sail stop

    Executar Artisan: ./vendor/bin/sail artisan [comando]

    Gerenciar Banco de Dados: ./vendor/bin/sail artisan migrate
    
### 3. Ajustes de Conflitos (Portas)

Caso você já tenha um MySQL rodando na máquina local (porta 3306), este projeto foi configurado no arquivo .env para usar uma porta alternativa no host:
    FORWARD_DB_PORT=33060
Isso permite que o MySQL do Docker coexista com o MySQL local.

🧪 Testes Automatizados no Docker

O Sail facilita a execução de testes dentro do container, garantindo que o ambiente de teste seja idêntico ao de produção.
    ./vendor/bin/sail test

🏗️ Serviços Inclusos (docker-compose.yml)

Este setup do Sail levanta automaticamente:

    PHP 8.x (Servidor Web)

    MySQL (Banco de dados)

    Redis (Cache)

    Mailpit (Testes de E-mail)

    Meilisearch (Busca)

    Selenium (Testes de Browser)
    
