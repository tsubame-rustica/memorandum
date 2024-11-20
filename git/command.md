# Gitでよく使うコマンド

## 目次
- **[初期設定](#初期設定)**
-  **[branch](#branch)**
-  **[checkout](#checkout)**

## フォルダの操作
- フォルダの移動
    ```sh
    cd 移動先のフォルダのパス
    ```

- フォルダの作成
    ```sh
    mkdir 作成したいフォルダ名
    ```

## Gitコマンド  

### 初期設定
- リモートリポジトリのクローン（初回のみ）
    ```sh
    git clone リポジトリのURL
    ```

- ローカルでのリポジトリの作成（初回のみ）
    ```sh
    git init
    ```

- リモートリポジトリと接続（初回のみ）
    ```sh
    git remote add origin リポジトリのURL
    ```

### branch

- 現在のブランチの確認
    ```sh
    git branch
    ```

- リモートブランチの確認
    ```sh
    git branch -r
    ```
- リモートとローカルブランチ一覧
    ```sh
    git branch -a
    ```

- ブランチの作成
    ```sh
    git branch ブランチ名
    ```

### checkout
- ブランチの作成&切り替え
    ```sh
    git checkout -b ブランチ名
    ```

- ブランチの切り替え
    ```sh
    git checkout ブランチ名
    ```

- ファイルの変更を取り消す
    ```sh
    git checkout ファイル名
    ```