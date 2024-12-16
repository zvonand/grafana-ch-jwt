## grafana-ch-jwt

Grafana + ClickHouse + kex for signle-sign-on / JWT integration tests. 

#### For now, user shall be pre-defined in clickhouse.

As dex is using some strange `sub` values and they cannot be changed, username looks weird in this demo. For other identity providers situation may be different.

### How to run

1. 

```
docker compose up
```

2. In your web browser, go to `http://localhost:3000`

3. Click "Sign in with 0Auth" on the login page: ![Screenshot from 2024-12-16 15-40-30](https://github.com/user-attachments/assets/3b22779d-39d7-4eba-9bb3-5fbba7b672a4)

4. Use the following credentials and press `Login` :![Screenshot from 2024-12-16 15-40-42](https://github.com/user-attachments/assets/0663295b-7f7f-4d93-ac0e-a4dc65c8d098)
   * e-mail: `admin@example.com`
   * password: `admin`

5. Go to "Connections" -> "Data Sources" tab (in the left vertical menu), press "add data source" and search for **Altinity plugin for ClickHouse** ![Screenshot from 2024-12-16 15-41-05](https://github.com/user-attachments/assets/fe2ce8d1-ea4a-488b-9cc7-c44c270de5b0)


6. In this view ![Screenshot from 2024-12-16 15-52-02](https://github.com/user-attachments/assets/e2f3ebf9-c88b-460d-934c-f1bf045d511b)
   * Enter URL `http://clickhouse:8123`
   * Toggle "Forward OAuth Identity" switch

7. Click "Save & Test" at the bottom of this page: ![Screenshot from 2024-12-16 15-54-48](https://github.com/user-attachments/assets/b6612aab-a632-4097-b43c-55188a6a73be)

8. Go to "Explore" tab: ![Screenshot from 2024-12-16 15-56-05](https://github.com/user-attachments/assets/ddf1fbe4-3341-41df-b935-00cc064ffb74)

9. In this view: ![Screenshot from 2024-12-16 15-57-17](https://github.com/user-attachments/assets/5fbeac22-8a20-432e-b779-b07c459bf15e)
    * Switch to "SQL Editor" mode
    * Switch "Format As" to "table"
    * Enter the query: `select currentUser()`
    * Press "Run Query", the username shall be `ChFhZG1pbkBleGFtcGxlLmNvbRIFbG9jYWw` 
