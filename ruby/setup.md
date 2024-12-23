# Rubyの環境構築

参考にした記事：https://qiita.com/kodai_0122/items/56168eaec28eb7b1b93b

## バージョン管理ツールのインストール
1. パスを通す(bashの場合は`~/.bashrc`)

    ```sh
    echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.zshrc
    ```

2. `eval init -`コマンドの設定(bashの場合は`~/.bash_profile`)

    ```sh
    echo 'eval "$(rbenv init -)"' >> ~/.zshrc
    ```

3. 変更を反映する
    ```sh
    source ~/.zshrc
    ```

4. `rbenv`をインストールする
    ```sh
    brew install rbenv ruby-build
    ```

## Rubyのインストール
1. `rbenv`からインストール可能なバージョンを調べる
    ```sh
    rbenv install --list
    ```

2. 例として`3.3.6`をインストール
    ```sh
    rbenv install 3.3.6
    ```

3. バージョンの確認
    ```sh
    rbenv versions
    ```

## 作業ディレクトリでの環境構築
1. 任意の作業フォルダを作成し開く
    ```sh
    mkdir -p ~/ruby/example
    ```
    ```sh
    cd ~/ruby/example
    ```

2. rubyのバージョンを適用する
    ```sh
    rbenv local 3.3.6
    ```
    ```sh
    rbenv rehash
    ```

3. 念の為バージョンを確認する
    ```sh
    ruby -v
    ```
    ```sh
    rbenv versions
    ```
    このようになっていれば適用できている
    ```sh
    # system
    # * 3.3.6 (set by /Users/ユーザー名//ruby/example/.ruby-version)
    ```

4. bundlerがインストールされているか確認
    ```sh
    bundler -v
    ```
    `not found`が出たら
    ```sh
    gem bundler install
    ```


## PostgreSQLとRailsのインストール
1. PostgreSQLをインストールする
    ```sh
    brew install postgresql

2. PostgreSQLを起動する
    ```sh
    brew service start postgresql
    ```

3. Railsのインストール
    - 最新のバージョンをインストール
        ```sh
        gem install rails
        ```
    - バージョンを指定する場合
        ```sh
        gem install rails -v バージョン
        ```

4. Railsがインストールできているか確認する
    ```sh
    rails -v
    ```
    `sudo gem install rails`を実行してねと表示された場合
    ```
    Rails is not currently installed on this system. To get the latest version, simply type:

    $ sudo gem install rails

    You can then rerun your "rails" command.
    ```
    ### `sudo gem install rails`は実行しない
    一度ターミナルを終了して再度開いてから`rails -v`を実行する

5. Railsアプリの骨格を作成
    ```sh
    rails _バージョン_ new . -d postgresql --skip-bundle
    ```
    - `-d` - デフォルトのデータベースを設定（今回はPostgreSQL）
    - `--skip-bundle` - `gem`のインストールを後回しにする

6. `Gemile`を開いて以下を変更する
    ```sh
    # 変更前
    gem 'rails', '~> 8.0.1'
    
    # 変更後
    gem 'rails', '8.0.1'
    ```

7. 各種`gem`をインストール
    ```sh
    bundle install --path vendor/bundle
    ```

8. railsを立ち上げる
    ```sh
    rails s
    ```

##  `rails s`で`ActiveRecord::NoDatabaseError`が発生した場合
- データベースを作成する
    ```sh
    rails db:create
    ```