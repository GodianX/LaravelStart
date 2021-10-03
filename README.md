# LaravelStart

### System requirements

- Docker 

### Installation

- `cp .env.example .env`
- `docker-compose up -d --build`
- `docker exec -it laravel_php bash`
- `cd ../laravelStart/`
- `composer install`

### Start
- `docker-compose up -d`

### Stop
- `docker-compose down`

### Laravel commands use here
- `docker exec -it laravel_php bash`
- `cd ../laravelStart/`

### Web

- `http://127.0.0.1:1080/`


### Postgres

- host: `localhost`
- user: `laravel`
- password: `laravel`
- database: `postgres`
- port: `15432`
