Este repositório contém uma aplicação Laravel e Nuxt.js, que são executadas em contêineres Docker. Siga as instruções abaixo para configurar e executar a aplicação localmente.

Subir Containers
Execute o seguinte comando para iniciar os contêineres Docker em segundo plano:

bash
Copy code
docker-compose up -d
Criar arquivo .env
Depois que os contêineres estiverem em execução, você precisa criar um arquivo .env para a aplicação Laravel. Você pode fazer isso executando o seguinte comando:

bash
Copy code
docker-compose exec laravel_api cp .env.example .env
Instalar Dependências da API
Instale as dependências da API Laravel executando o seguinte comando:

bash
Copy code
docker-compose exec laravel_api composer install
Executar Migrações do Banco de Dados da API
Para executar as migrações do banco de dados da API Laravel, use o seguinte comando:

bash
Copy code
docker-compose exec laravel_api /var/www/html/artisan migrate:fresh
Criar Usuário Padrão no Banco de Dados
Após executar as migrações, crie um usuário padrão no banco de dados com o seguinte comando:

bash
Copy code
docker-compose exec laravel_api /var/www/html/artisan db:seed
Parar Serviços
Quando terminar de usar a aplicação, você pode parar os contêineres Docker com o seguinte comando:

bash
Copy code
docker-compose down
Acessar API e Interface Web
Depois de iniciar os contêineres, você poderá acessar a API em:

http://localhost:9090
E a interface web em:

http://localhost:5000
Referências
Laravel Nuxt:

Vídeo 1
Vídeo 2
Docker:

Playlist no YouTube
Atualizar
Para manter sua cópia do repositório atualizada com as últimas alterações, siga estes passos:

bash
Copy code
git pull
cd laravel-nuxt
docker-compose up -d --build
