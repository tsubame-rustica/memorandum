# Nginxサーバーの構築方法
## 概要
MySQLを用いたWebアプリケーションを公開するためのNginxの構築方法

## 使用環境
- Ubuntuサーバー

## 手順
### Nginxのインストール
- Nginxをインストールする
    ```bash
    sudo apt install nginx
    ```
    念の為、サーバーが立っているか確認する
    ```bash
    sudo systemctl status nginx
    ```
    `Active: active(running)`になっていればOK
    ```
    ● nginx.service - A high performance web server and a reverse proxy server
     Loaded: loaded (/usr/lib/systemd/system/nginx.service; enabled; preset: enabled)
     Active: active (running) since Thu 2025-05-15 09:30:26 JST; 14min ago
       Docs: man:nginx(8)
   Main PID: 370399 (nginx)
      Tasks: 7 (limit: 7012)
     Memory: 5.1M (peak: 5.8M)
        CPU: 21ms
     CGroup: /system.slice/nginx.service
             ├─370399 "nginx: master process /usr/sbin/nginx -g daemon on; master_process on;"
             ├─370400 "nginx: worker process"
             ├─370401 "nginx: worker process"
             ├─370402 "nginx: worker process"
             ├─370403 "nginx: worker process"
             ├─370404 "nginx: worker process"
             └─370405 "nginx: worker process"
    ```

### MySQLのインストール
1. すでにMySQLが入っていないか確認
    ```bash
    mysql --version
    ```

2. もし入っていなければMySQLをインストール（今回はバージョン8.0.4）
    ```bash
    sudo apt install mysql-server-8.0 -f
    ```

3. MySQLにログインする
    ```bash
    sudo mysql -u root
    ```

4. ユーザーの一覧を表示して`root`のホストを確認する
    ```mysql
    SELECT Host, User FROM mysql.user;
    ```

5. `root`のパスワードを変更し、ログインの方法もパスワード認証に変更する
    ```mysql
    ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'あなたの設定したパスワード';
    ```
    認証方法を変更したので、設定を反映させる
    ```
    FLUSH PRIVILEGES;
    ```


