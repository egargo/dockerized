# :whale2: Everything Dockerized

Everything Dockerized


## Contents

- [Contents](#contents)
    - [Dependencies](#dependencies)
    - [Databases](#databases)
    - [Connecting to Database](#connecting-to-database)
        - [CLI](#cli)
        - [GUI](#gui)
- [License](#license)


### Dependencies

- [Docker](https://www.docker.com/)
- [DBeaver](https://dbeaver.io/) - I recommend using DBeaver as it is the most easy to use and accessible database interface.
    - [Linux](https://flathub.org/apps/io.dbeaver.DBeaverCommunity)


### Databases

| Name       | Command                         | Description              |
|------------|---------------------------------|--------------------------|
| Adminer    | `docker compose up -d adminer`  | Database management tool |
| MySQL      | `docker compose up -d mysql`    | MySQL                    |


### Configuration

Create a copy of `.env.example` named `.env`, then open the `.env` and set the
required environment variables.


### Connecting to Database

#### CLI
```bash
# Default Postgres port is 5432
docker exec -it <CONTAINER> psql -h <CONTAINER_IP> -p <PORT> -U <USERNAME> <DB_NAME>

# Default MySQL port is 3306
docker exec -it <CONTAINER> mysql -u <USERNAME> -p
```

#### GUI

> [!TIP]
> To get the IP Address of the Docker containers, run the docker inspect command: `docker inspect <container_name> | grep IPAddress`, then copy and paste the container's IP address to Adminer's `Server` field.

| Database   | DBeaver Configuration                                           |
|------------|-----------------------------------------------------------------|
| MySQL      | Host: `172.X.X.X`                                               |
|            |       `localhost`                                               |
|            | Database: `<db_name>?useSSL=false&allowPublicKeyRetrieval=true` |
|            | Port: `3306`                                                    |
|            | Username: `postgres`                                            |
|            | Password: `<passwor>`                                           |
|            |                                                                 |
|            |                                                                 |
| Postgres   | Host: `172.X.X.X`                                               |
|            |       `localhost`                                               |
|            | Database: `<db_name>`                                           |
|            | Port: `5432`                                                    |
|            | Username: `root`                                                |
|            | Password: `<password>`                                          |


### License

This project is provided under the [MIT License](./LICENSE).
