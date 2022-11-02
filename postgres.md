## Postgres

- Default
  - database: postgres
  - role: postgres
  
- Usage
  - Login with role postgres
    ```
    sudo -i -u postgres
    ```
    ```
    psql
    ```
    or shortway
    ```
    sudo -u postgres psql
    ```

- create new role

```
    CREATE ROLE ubuntu superuser;
```

- update role

```
ALTER ROLE ubuntu with LOGIN;
```

- list database
```
\l
```

- list all role
```
\du
```

- access the database through the local
```
psql --host=api-github-coffee.crtno9dzwyk4.us-west-2.rds.amazonaws.com --port=5432 --username=aminhp93 --password --dbname=api
```

- grant permission to role
```
psql api -c "GRANT ALL ON ALL TABLES IN SCHEMA public to aminhp93;"
```
```
psql api -c "GRANT ALL ON ALL SEQUENCES IN SCHEMA public to aminhp93;"
```
```
psql api -c "GRANT ALL ON ALL FUNCTIONS IN SCHEMA public to aminhp93;"

```

