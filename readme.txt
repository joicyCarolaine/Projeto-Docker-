Este repositório contém uma aplicação Laravel e Nuxt.js, que são executadas em contêineres Docker. Siga as instruções abaixo para configurar e executar a aplicação localmente.


Subir Containers
Comando:

Bash
docker compose up -d
Use o código com cuidado.
Explicação:

Este comando inicia todos os containers definidos no arquivo docker-compose.yml. A flag -d indica que os containers devem ser executados em segundo plano.

Criar Arquivo .env
Comando:

Bash
docker compose exec laravel_api cp .env.example .env
Use o código com cuidado.
Explicação:

Este comando copia o arquivo .env.example para o diretório de trabalho do container laravel_api. O arquivo .env.example contém variáveis de ambiente de exemplo que precisam ser configuradas antes de iniciar o aplicativo Laravel.

Instalar Dependências da API
Comando:

Bash
docker compose exec laravel_api composer install
Use o código com cuidado.
Explicação:

Este comando instala todas as dependências do PHP necessárias para o aplicativo Laravel.

Executar Migrações de Banco de Dados da API
Comando:

Bash
docker compose exec laravel_api /var/www/html/artisan migrate:fresh
Use o código com cuidado.
Explicação:

Este comando executa as migrações do banco de dados do Laravel, criando as tabelas necessárias para o aplicativo. A flag --fresh garante que as tabelas sejam recriadas do zero, mesmo que já existam.

Criar Usuário Padrão no Banco de Dados
Comando:

Bash
docker compose exec laravel_api /var/www/html/artisan db:seed
Use o código com cuidado.
Explicação:

Este comando executa os seeds do banco de dados do Laravel, populando as tabelas com dados de exemplo. Um desses seeds provavelmente cria um usuário padrão para o aplicativo.

Parar Serviços
Comando:

Bash
docker compose down
Use o código com cuidado.
Explicação:

Este comando para todos os containers definidos no arquivo docker-compose.yml.

Acessar API
URL:

http://localhost:9090
Explicação:

A API está disponível na porta 9090 do seu localhost. Você pode usar qualquer ferramenta HTTP para testar a API, como Postman ou curl.

Acessar Interface Web
URL:

http://localhost:5000
Explicação:

A interface web está disponível na porta 5000 do seu localhost. Esta é a interface do aplicativo Nuxt.js que renderiza a aplicação front-end.

Referências
Laravel Nuxt:

Vídeo 1: Configurando o Laravel com Docker e Nuxt.js: https://www.youtube.com/watch?v=NY9yoqoN72w&t=1004s
Vídeo 2: Implementando Autenticação no Laravel com Nuxt.js: https://www.youtube.com/watch?v=HLPoKz9j9KY&t=325s
Docker:

Playlist Docker do Zero ao Heroi: https://www.youtube.com/watch?v=ScmgXebitlQ&list=PLN_FLtIvNW0mo63rPdFBgL_UP5wF5eWLT
Atualizar
Comandos:

Bash
git pull

cd laravel-nuxt

docker compose up -d --build
Use o código com cuidado.
