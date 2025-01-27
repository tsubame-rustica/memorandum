# Apacheのセットアップ
## Macの場合
1. Apacheを起動する
    ```sh
    sudo apachectl start
    ```
2. 設定ファイルを開く
    ```sh
    sudo vim /etc/apache2/httpd.conf
    ```

3. httpd.confファイルのコメントアウトされている部分を変更する
    変更前
    ```conf
    #（前略）
    # LoadModule userdir_module libexec/apache2/mod_userdir.so
    # LoadModule alias_module libexec/apache2/mod_alias.so
    #（中略）
    # User home directories
    # Include /private/etc/apache2/extra/httpd-userdir.conf
    #（後略）
    ```
    変更後
    ```conf
    #（前略）
    LoadModule userdir_module libexec/apache2/mod_userdir.so
    LoadModule alias_module libexec/apache2/mod_alias.so
    #（中略）
    # User home directories
    Include /private/etc/apache2/extra/httpd-userdir.conf
    #（後略）
    ```

4. ドキュメントルートを変更する
    変更前
    ```conf
    DocumentRoot "/Library/WebServer/Documents"
    <Directory "/Library/WebServer/Documents">
    # (中略)
    Options FollowSymLinks Multiviews
    # (中略)
    AllowOverride None
    # (中略)
    </Dirctory>
    ```
    変更後
    ```conf
    DocumentRoot "/Users/[ユーザー名]/example"
    <Directory "/Users/[ユーザー名]/example">
        Options Indexes FollowSymLinks
        AllowOverride All
        # (中略)
        # Options FollowSymLinks Multiviews
        # (中略)
        # AllowOverride None
        # (中略)
    </Dirctory>
    ```

5. Apacheを再起動する
    ```sh
    sudo apachectl restart
    ```

6. 権限を変更する
    ```sh
    chmod +x /Users/[ユーザー名]
    chmod 755 /Users/[ユーザー名]/example
    ```

7. http://localhost にアクセスして動作していることを確認する