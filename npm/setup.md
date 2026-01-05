# nvmをインストールしてviteの環境構築をする

## npxのインストール
1. 以下のコマンドでnvmをインストールする
    ```bash
    curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.3/install.sh | bash
    ```

2. nvmからNode.jsをインストールする
    ```bash
    nvm install --lts --latest-npm
    nvm alias default 'lts/*'
    ```

## viteのプロジェクトを作成
1. 以下のコマンドを実行し、プロジェクトを作成する
    ```bash
    npm create vite@latest
    ```