# karnakDocker

This repository shows an example docker-compose to launch Karnak with all his dependencies.

Currently Karnak needs:
* Postgres DataBase
* Mainzelliste

# Launch Karnak

Karnak has been tested with:

* [docker](https://docs.docker.com/install/) version: **19.03**
* [docker-compose](https://docs.docker.com/compose/install/) version: **1.22**

## docker-compose commands

* start a docker-compose: `docker-compose up`
* stop a docker-compose: `docker-compose down`
* stop and remove volume of a docker-compose: `docker-compose down -v`
* logs a docker-compose: `docker-compose logs -f`

## Karnak's secrets

Before to start karnak you must create a folder secrets on the root of the project and create the following secrets:

* karnak_hmac_key
* karnak_postgres_password
* mainzelliste_api_key
* mainzelliste_postgres_password
* mainzelliste_pid_k1
* mainzelliste_pid_k2
* mainzelliste_pid_k3

or you can generate the secret with the script `start.sh`. (No guarantee that it works on your machine)

## Karnak's environment variables

To configure and analyze the docker environment variables used by karnak, please refer this links.
* [docker hub postgres](https://hub.docker.com/_/postgres)
* [docker hub mainzelliste](https://hub.docker.com/r/osirixfoundation/karnak-mainzelliste)

`DB_USER`

User of the karnak database (optional, default is `karnak`).

`DB_USER_FILE`

User of the karnak database via file input (alternative to `DB_USER`).

`DB_PASSWORD`

Password of the karnak database (optional, default is `karnak`).

`DB_PASSWORD_FILE`

Password of the karnak database via file input (alternative to `DB_PASSWORD`).

`DB_NAME`

Name of the karnak database (optional, default is `karnak`).

`DB_NAME_FILE`

Name of the karnak database via file input (alternative to `DB_NAME`).

`DB_HOST`

Hostname/IP Address of the PostgreSQL host. (optional, default is `localhost`).

`DB_PORT`

Port of the PostgreSQL host (optional, default is `5432`)

`MAINZELLISTE_HOSTNAME`

Hostname/IP Address of the Mainzelliste host. (optional, default is `localhost`).

`MAINZELLISTE_HTTP_PORT`

Port of the Mainzelliste host. (optional, default is `8080`).

`MAINZELLISTE_ID_TYPES`

Type of pseudonym to be created and sent.

`MAINZELLISTE_API_KEY`

The api key used to connect to Mainzelliste host (optional, default is `undefined`)

`KARNAK_HMAC_KEY`

The key used for the HMAC. This HMAC will be used for all the hash created by karnak

`KARNAK_HMAC_KEY_FILE`

The key used for the HMAC via file input. (alternative to `KARNAK_HMAC_KEY`).
