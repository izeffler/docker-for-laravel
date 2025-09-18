CRÉDITOS: https://github.com/Pansiere

DOCKER-FOR-LARAVEL

ESSE PROJETO DOCKER FACILITA O BUILD DA SUA APLICAÇÃO EM AMBIENTE LOCAL, COM ESSE DOCKER EM EXECUÇÃO O SEU VITE É EXECUTADO EM BACKGROUND, TIRANDO A NECESSIDADE DE EXECUTAR `npm run dev`

PASSO A PASSO DE COMO USAR O DOCKER

- CLONE O REPOSITÓRIO E COPIE SEUS ARQUIVOS PARA A RAIZ DO SEU PROJETO LARAVEL

```shell
git clone git@github.com:izeffler/docker-for-laravel.git
```

- NO .ENV DO SEU PROJETO LARAVEL, CONFIGURE O DATABASE DESSA FORMA

```php
DB_CONNECTION=mysql
DB_HOST=mysql
DB_PORT=3306
DB_DATABASE=SEU_DB_AQUI
DB_USERNAME=root
DB_PASSWORD=password
```

- BUILDAR DOCKER

```
docker compose up -d --build
```

- URLS DE ACESSO

```
localhost -> acessa sua aplicação na web
localhost:8080 -> acessa seu phpMyAdmin (login automático e direto)
```

- ACESSO DOS CONTAINERS

```shell
docker exec -it php bash # comando para acessar o container do php
docker exec -i mysql -uroot -ppassword # comando para executar comandos mysql dentro do container mysql

```
