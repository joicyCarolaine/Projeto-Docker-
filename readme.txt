## Subir containers
docker compose up -d 


# Verificar se todos os containers estão up
docker ps -a

# Verificar se as images subiram
docker images -a

# Cria arquivo .env
docker compose exec laravel_api cp .env.example .env

# Instalar dependencias api
docker compose exec laravel_api composer install

# Executar migrações de banco de dados api 
docker compose exec laravel_api /var/www/html/artisan migrate:fresh

# Cria usuario padrão no banco de dados
docker compose exec laravel_api /var/www/html/artisan db:seed

# Atualizar

docker compose down

git pull

cd Projeto-Docker-

docker compose up -d --build


# Acessar api
http://localhost:9090

# Acessar interface web
http://localhost:5000

# Referencias Utilizadas

## Laravel Nuxt

https://www.youtube.com/watch?v=NY9yoqoN72w&t=1004s

https://www.youtube.com/watch?v=HLPoKz9j9KY&t=325s

## Docker

https://www.youtube.com/watch?v=ScmgXebitlQ&list=PLN_FLtIvNW0mo63rPdFBgL_UP5wF5eWLT



