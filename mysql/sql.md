## SQLの管理用コマンド

- ユーザーの追加
    ```sql
    CREATE USER ユーザー名
    ```

- ユーザーの確認
    ```sql
    SELECT Host, User FROM mysql.user;
    ```

- ユーザーのパスワード変更
    ```sql
    SET PASSWORD FOR 'ユーザー名'@'ホスト名' = 'パスワード';
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