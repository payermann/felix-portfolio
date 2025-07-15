# felix-portfolio

## Получение сертификатов

Запустите Docker Compose для создания контейнеров и получения SSL сертификатов.

```sh
docker-compose up -d

docker-compose run --rm certbot certonly --webroot --webroot-path=/var/www/certbot -d felix-portfolio.de
```

## Перезапуск Nginx

После получения сертификатов перезапустите контейнер Nginx для применения конфигурации.

```sh
docker-compose restart nginx
```

## Первоначальная настройка

```sh
docker build -t certbot-init -f Dockerfile.certbot-init .

docker run --rm -p 80:80 -v "$(pwd)/letsencrypt:/etc/letsencrypt" -v "$(pwd)/certbot:/var/www/certbot" certbot-init
```
тем самым будут созданы папки с сертификатами, и потом их можно будет использовать в основном docker-compose
