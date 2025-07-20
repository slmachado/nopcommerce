# Como iniciar o nopCommerce via Docker #

Para iniciar o nopCommerce via Docker, você já tem tudo o que precisa: Dockerfile, docker-compose.yml e arquivos alternativos para bancos de dados (mysql-docker-compose.yml, postgresql-docker-compose.yml).

Abaixo estão as instruções passo a passo para inicializar:

## ✅ 1. Escolher o banco de dados ##

Você pode escolher entre SQL Server, MySQL ou PostgreSQL:

| Banco de Dados | Arquivo de Compose              | Porta da app |
| -------------- | ------------------------------- | ------------ |
| SQL Server     | `docker-compose.yml`            | 8010         |
| MySQL          | `mysql-docker-compose.yml`      | 80           |
| PostgreSQL     | `postgresql-docker-compose.yml` | 80           |

## ✅ 2. Executar o docker-compose ##

Abra um terminal na pasta onde estão os arquivos e execute:

### Para SQL Server ###

```bash
docker-compose -f docker-compose.yml up --build
```

### Para MySQL ###

```bash
docker-compose -f mysql-docker-compose.yml up --build
```

### Para PostgreSQL ###

```bash
docker-compose -f postgresql-docker-compose.yml up --build
```

## ✅ 3. Acessar a aplicação ##

Depois que os containers estiverem em execução:

### SQL Server ###

- <http://localhost:8010>

### MySQL/PostgreSQL ###

- <http://localhost>

A interface web do nopCommerce Setup será exibida.

### ✅ 4. Configurar a loja via navegador ###

No primeiro acesso você verá um formulário para:

- Criar usuário administrador
- Definir nome da loja
- Escolher o tipo de banco de dados

⚠️ Importante: Se você estiver usando um banco diferente do padrão SQL Server, selecione “Use an existing database connection” e configure conforme abaixo:

Exemplos de string de conexão:

- SQL Server

```bash
Server=nopcommerce_database;Database=nopcommerce;User Id=sa;Password=nopCommerce_db_password;
```

- MySQL

```bash
Server=nopcommerce_database;Database=nopcommerce;Uid=root;Pwd=nopCommerce_db_password;
```

PostgreSQL

```bash
Host=nopcommerce_database;Database=nopcommerce;Username=postgres;Password=nopCommerce_db_password;
```
