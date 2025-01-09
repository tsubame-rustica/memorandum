# Pyenvをインストールしてvenvにより仮想環境を構築する方法

## pyenvのインストール方法
### Linuxの場合
1. リポジトリをクローンする
    ```bash
    git clone https://github.com/pyenv/pyenv.git ~/.pyenv
    ```

2. 環境変数を設定する

    - bash
        ```sh
        echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.bashrc
        echo 'command -v pyenv >/dev/null || export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.bashrc
        echo 'eval "$(pyenv init -)"' >> ~/.bashrc
        ```
        ```sh
        echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.profile
        echo 'command -v pyenv >/dev/null || export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.profile
        echo 'eval "$(pyenv init -)"' >> ~/.profile
        ```

        - zsh
        ```sh
        echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.zshrc
        echo 'command -v pyenv >/dev/null || export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.zshrc
        echo 'eval "$(pyenv init -)"' >> ~/.zshrc
        ```

3. シェルを再起動する
    ```sh
    exec "$SHELL"
    ```

4. Pythonビルドのための依存関係をインストールする
    ```sh
    sudo apt update
    sudo apt install -y build-essential libssl-dev zlib1g-dev libbz2-dev libreadline-dev libsqlite3-dev curl libncursesw5-dev xz-utils tk-dev libxml2-dev libxmlsec1-dev libffi-dev liblzma-dev
    ```

5. pyenvで任意のバージョンをインストールする
    ```sh
    pyenv instsll [任意のバージョン]
    ```
    以下のコマンドでインストールしたバージョンを確認できる
    ```sh
    pyenv versions
    ```

6. pythonのデフォルトのバージョンを変更する
    ```sh
    pyenv global [任意のバージョン]
    ```
    ローカルのバージョンのみ変更する場合
    ```sh
    pyenv local [任意のバージョン]
    ```

### Macの場合


## venvによる仮想環境の構築
1. 仮想環境を構築したいディレクトリに移動する

2. 以下のコマンドで構築
    ```sh
    python -m venv [仮想環境名]
    ```

3. アクティベートする
    ```sh
    . /[仮想環境名]/bin/activate
    ```

4. 仮想環境を修了する
    ```sh
    deactivate
    ```