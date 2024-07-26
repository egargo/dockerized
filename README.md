# :whale2: Everything Dockerized

Everything Dockerized


## Contents

- [Contents](#contents)
    - [Databases](#databases)
    - [Connecting to Database](#connecting-to-database)
- [License](#license)


### Databases

| Name       | Command                         | Description              |
|------------|---------------------------------|--------------------------|
| Adminer    | `docker compose up -d adminer`  | Database management tool |
| MySQL      | `docker compose up -d mysql`    | MySQL                    |
| PostgreSQL | `docker compose up -d postgres` | PostgreSQL               |


### Configuration

Create a copy of `.env.example` named `.env`, then open the `.env` and set the
required environment variables.


### Connecting to Database

> [!TIP]
> To get the IP Address of the Docker containers, run the docker inspect command: `docker inspect <container_name> | grep IPAddress`, then copy and paste the container's IP address to Adminer's `Server` field.

Open [Adminer](http://localhost:8080/) and follow the configuration below.

| Database   | Adminer Configuration |
|------------|-----------------------|
| MySQL      | System: MySQL         |
|            | Server: 172.X.X.X     |
|            |                       |
|            |                       |
| PostgreSQL | System: PostgreSQL    |
|            | Server: 172.X.X.X     |
|            |                       |
|            |                       |


### License

This project is provided under the [MIT License](./LICENSE).
