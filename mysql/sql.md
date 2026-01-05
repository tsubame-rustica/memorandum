## SQLの管理用コマンド

- ユーザーの追加
    ```sql
    CREATE USER ユーザー名
    ```

- ユーザーの確認
    ```sql
    SELECT Host, User FROM mysql.user;
    ```

- ユーザー名の変更
    ```sql
    RENAME USER old_user TO new_user;
    ```

- ユーザーのパスワード変更
    ```sql
    SET PASSWORD FOR 'ユーザー名'@'ホスト名' = 'パスワード';
    ```
    ```sql
    ALTER USER 'root'@'localhost' IDENTIFIED BY 'xxxxx';
    ```

- ユーザーの権限を変更
    - 権限の付与
        ```sql
        GRANT select, update on 権限のレベル to 'ユーザー名'@'ホスト名';
        ```

    - 権限の削除
        ```sql
        REVOKE 権限 on 権限のレベル to 'ユーザー名'@'ホスト名';
        ```
    

    - 操作の種類　
        - select
        - update
        - insert
        - delete
        - create
        - drop
        - all privileges

    - 権限のレベル
        
        - グローバルレベル - `*.*`
        - データベースレベル - `db_name.*`
        - テーブルレベル - `db_name.table_name`


- 権限の確認
    ```sql
    SHOW grants FOR 'ユーザー名'@'ホスト名';
    ```

## 別ユーザーに権限を付与するときの注意点
- `SHOW DATABASES`でデータベースが見えない時(USE文が使えない時)
```sql
GRANT SHOW DATABASES, SELECT on *.* to 'ユーザー名'@'ホスト名';
```