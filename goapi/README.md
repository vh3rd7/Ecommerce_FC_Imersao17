# API Catalog

## Banco de dados 

mysql usando docker

executar o comando `docker compose up -d` no diretório onde se encontra o arquivo `docker-compose.yml`

executar bash do container para acessar o banco
`docker compose exec mysql bash`

acessando o mysql CLI
`mysql -uroot -p imersao17`  
password: root

script para criar tabelas 
```sql
CREATE TABLE `categories` (
  `id` varchar(36) NOT NULL,
  `name` varchar(255) NOT NULL,
  PRIMARY KEY (`id`)
);

CREATE TABLE `products` (
  `id` varchar(36) NOT NULL,
  `name` varchar(255) NOT NULL,
  `description` varchar(255) NOT NULL,
  `price` decimal(10,2) NOT NULL,
  `category_id` varchar(36) NOT NULL,
  `image_url` varchar(255) NOT NULL,
  PRIMARY KEY (`id`),
  KEY `fk_products_categories_idx` (`category_id`)
);
```

comando para listar tabelas
`SHOW TABLES;`

arquivo para testar api
`test.http`

## Executando a API

```bash
cd cmd/catalog/
go run main.go
```
