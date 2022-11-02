## Kill port

```bash
k() {
  lsof -t -i tcp:$1 | xargs kill -9
}
```

- Usage

  ```
  k 3000
  ```

## Reload oh-my-szh

```
omz reload
```

## Error message psql: Can't connect to Postgresql on port 5432

1. Step 1

   - Mac intel

     ```js
     rm /usr/local/var/postgres/postmaster.pid
     ```

   - Mac m1

     ```
     rm /opt/homebrew/var/postgres/postmaster.pid
     ```

2. Step 2

   ```
   brew services restart postgresql
   ```


