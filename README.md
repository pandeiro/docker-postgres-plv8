postgres-plv8
=============

Docker image for running **PLV8 1.4** on **Postgres 9 (9.3.5)**.

Based on the [official Postgres image](http://registry.hub.docker.com/_/postgres/).

Forked from [clkao/docker-postgres-plv8](https://github.com/clkao/docker-postgres-plv8) due
to [missing functionality](https://github.com/docker-library/postgres/issues/41) in official postgres:9.4 image.



## Usage

Start a postgres server container with persistent storage and give it a name:

    % docker run -d -v /tmp/data:/var/lib/postgresql/data --name some-postgres pandeiro/postgres-plv8:9.4

Start client container that links to the server container above as the "postgres" alias:

    % docker run --link some-postgres:postgres --rm -ti pandeiro/postgres-plv8:9.4 bash -c 'psql -U postgres -h $POSTGRES_PORT_5432_TCP_ADDR'
