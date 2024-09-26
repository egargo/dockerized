# :whale2: Everything Dockerized

Everything Dockerized


## Contents

- [Contents](#contents)
    - [Dependencies](#dependencies)
    - [Services](#databases)
    - [Connecting to Database](#connecting-to-database)
        - [CLI](#cli)
        - [GUI](#gui)
- [License](#license)


### Dependencies

- [Docker](https://www.docker.com/)
- [DBeaver](https://dbeaver.io/) - I recommend using DBeaver as it is the most easy to use and accessible database interface.
    - [Linux](https://flathub.org/apps/io.dbeaver.DBeaverCommunity)


### Services

| Name       | Command                         | Description              |
|------------|---------------------------------|--------------------------|
| Adminer    | `docker compose up -d adminer`  | Database management tool |
| MySQL      | `docker compose up -d mysql`    | MySQL                    |
| Keycloak   | `docker compose up -d keycloak` | Keycloak                 |


### Configuration

Create a copy of `.env.example` named `.env`, then open the `.env` and set the
required environment variables.


### Connecting to Services

#### CLI
```bash
# Default Postgres port is 5432
docker exec -it <CONTAINER> psql -h <CONTAINER_IP> -p <PORT> -U <USERNAME> <DB_NAME>

# Default MySQL port is 3306
docker exec -it <CONTAINER> mysql -u <USERNAME> -p

# Default Keycloak port is 8080
open http://localhost:8080
```

#### GUI

> [!TIP]
> To get the IP Address of the Docker containers, run the docker inspect command: `docker inspect <container_name> | grep IPAddress`, then copy and paste the container's IP address to Adminer's `Server` field.

| Database   | DBeaver Configuration                                                  |
|------------|------------------------------------------------------------------------|
| MySQL      | Host: `172.X.X.X`                                                      |
|            |       `localhost`                                                      |
|            | Database: `<MYSQL_DATABASE>?useSSL=false&allowPublicKeyRetrieval=true` |
|            | Port: `3306`                                                           |
|            | Username: `MYSQL_USER`                                                 |
|            | Password: `<MYSQL_PASSWORD>`                                           |
|            |                                                                        |
|            |                                                                        |
| Postgres   | Host: `172.X.X.X`                                                      |
|            |       `localhost`                                                      |
|            | Database: `postgres`                                                   |
|            | Port: `5432`                                                           |
|            | Username: `postgres`                                                   |
|            | Password: `<POSTGRES_PASSWORD>`                                        |
|            |                                                                        |
|            |                                                                        |
| Keycloak   | Username: `<KEYCLOAK_ADMIN_USER>`                                      |
|            | Password: `<KEYCLOAK_ADMIN_PASSWORD>`                                  |


### License

This project is provided under the [MIT License](./LICENSE).
