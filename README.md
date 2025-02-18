# felix-portfolio

## Получение сертификатов

Запустите Docker Compose для создания контейнеров и получения SSL сертификатов.

```sh
docker-compose up -d

docker-compose run --rm certbot certonly --webroot --webroot-path=/usr/share/nginx/html -d example.com
```

## Перезапуск Nginx

После получения сертификатов перезапустите контейнер Nginx для применения конфигурации.

```sh
docker-compose restart nginx
```
