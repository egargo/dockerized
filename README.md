# :whale2: Everything Dockerized

Everything Dockerized


## Contents

- [Contents](#contents)
    - [Databases](#databases)
    - [Connecting to Database](#connecting-to-database)
- [License](#license)


### Databases

| Name                      | Command                                       |
|---------------------------|-----------------------------------------------|
| Adminer                   | `docker compose up -d adminer`                |
| MySQL                     | `docker compose up -d mysql`                  |
| PostgreSQL                | `docker compose up -d postgres`               |


### Configuration

Create a copy of `.env.example` named `.env`, then open the `.env` and set the
required environment variables.


### Connecting to Database

- Adminer
    - MySQL
        ```
        System: MySQL
        Server: ${docker inspect egargo.mysql | grep IPAddress}
        ```
    - PostgreSQL
        ```
        System: PostgreSQL
        Server: ${docker inspect egargo.postgres | grep IPAddress}
        ```

- DBeaver
    - MySQL
        ```
        Host: localhost?allowPublicKeyRetrieval=true&useSSL=false
        ```
    - PostgreSQL
        ```
        Host: localhost
        ```


### License

This project is provided under the [MIT License](./LICENSE).
