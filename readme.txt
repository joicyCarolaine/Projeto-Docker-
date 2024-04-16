cd laravel-nuxt

# Subir containers
docker compose up -d

# Cria arquivo .env
docker compose exec laravel_api cp .env.example .env

# Instalar dependencias api
docker compose exec laravel_api composer install

# Executar migrações de banco de dados api 
docker compose exec laravel_api /var/www/html/artisan migrate:fresh

# Cria usuario padrão no banco de dados
docker compose exec laravel_api /var/www/html/artisan db:seed


# Parar serviços
docker compose down


# Acessar api
http://localhost:9090

# Acessar interface web
http://localhost:5000

# Referencias

## Laravel Nuxt

https://www.youtube.com/watch?v=NY9yoqoN72w&t=1004s

https://www.youtube.com/watch?v=HLPoKz9j9KY&t=325s

## Docker

https://www.youtube.com/watch?v=ScmgXebitlQ&list=PLN_FLtIvNW0mo63rPdFBgL_UP5wF5eWLT


# Atualizar 

git pull

cd laravel-nuxt

# Subir containers e atualizar as imagens
docker compose up -d --build





Pede pra ela excluir tudo e realizar o processo novamente

provavelmente a api não estava subindo pq a porta 9090 estava presa em algum container das outras vezes que deu erro

Envia pra ela fala que ainda não consegue fazer mas que vai pesquisar para fazer essas melhorias

Melhorias

Criar tela de perfil onde o usuário pode atualizar informações do cadastros
Criar rotina para recuperação de senha, (esqueci minha senha)

Criar tela administrativa para adicionar, excluir, atualizar e  listar todos os usuários (permissão somente para usuario admin)