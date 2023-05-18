# [Backstage](https://backstage.io)

This is your newly scaffolded Backstage App, Good Luck!

To start the app, run:

```sh
yarn install
yarn dev
```

To configure the app to persist the catalog to a Postgres database, use the following instructions:

Install Postgres:

```
sudo apt-get install postgresql
```

Configure user and password:

```
sudo -u postgres psql
ALTER USER postgres PASSWORD 'secret';
```

Install PostgreSQL client:

```
yarn add --cwd packages/backend pg
```

Update database configuration in app-config.yaml file:

```
backend:
  database:
    client: pg
    connection:
      host: ${POSTGRES_HOST}
      port: ${POSTGRES_PORT}
      user: ${POSTGRES_USER}
      password: ${POSTGRES_PASSWORD}
```

To use the persisted catalog functionality, make sure to set the environment variables above on the running machine.


Change I did in the UI -> renames "APIs" menu item to "Browse APIs".

Node.JS template contains Github Action which is triggered on pull requests. It contains no quality gate steps yet. Exact steps can be defined by the user depending on the project.