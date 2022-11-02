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

