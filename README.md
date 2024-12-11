# grafana-ch-jwt

Grafana + ClickHouse + kex for signle-sign-on / JWT integration tests. 

1. 

```
docker-compose up
```

2. 

navigate to http://localhost:8123

3. ![image](https://gist.github.com/user-attachments/assets/6451dd38-f9b8-4bbf-bda4-736628ecff0e)

4. ![image](https://gist.github.com/user-attachments/assets/9afa074a-0a70-429a-a1bf-9e1e4fda3a08)

5. type login `admin@example.com` password `admin`

6. ![image](https://gist.github.com/user-attachments/assets/bf9321e2-9c72-4a23-972c-0b21bea7f75e)

7. Click 'Add new datasource' 

8. Filter by name: type Altinity

9. URL: `http://clickhouse:8123`
10. Forward OAuth Identity: 'enable' 
11. 'Save & test'