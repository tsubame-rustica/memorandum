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
    - テーブル内の権限
        ```sql
        GRANT select, update on db_name.*to 'ユーザー名'@'ホスト名';
        ```

- 権限の確認
    ```sql
    SHOW grants FOR 'ユーザー名'@'ホスト名';
    ```