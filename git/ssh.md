# GitHubとssh接続できるようにする
GitHub上とローカルでやり取りをするためには公開鍵の登録が必要です  
**秘密鍵は公開しないようにしてください**

※githubアカウントは作成済みの前提

gitのインストール   
https://git-scm.com/downloads

[インストール手順](https://qiita.com/T-H9703EnAc/items/4fbe6593d42f9a844b1c)

## 接続手順
### Windowsの場合
#### Powershell側
1.  [windows]キーを押して「powershell」と検索して開く  

2.  以下のコマンドを実行する
    ```sh
    cd ~/.ssh
    ```
    もし`no such file or directory: ~/.ssh`が出たら
    ```sh
    mkdir ~/.ssh
    ```
    を実行してもう一度`cd ~/.ssh`を実行する

3.  1を実行し、.sshが開けたら`ssh-keygen`を実行する
    ```sh
    ssh-keygen
    ```
    ここではGitHubで推奨されているed25519方式で鍵を作成する

4.  3回ほどEnterキーを押すと実行が完了する。

5.  以下のコマンドを実行すると公開鍵の内容がクリップボードにコピーできる。
    ```sh
    Get-Content ~/.ssh/id_ed25519.pub | clip
    ```

### Macの場合
#### Terminal側

1.  [command] + [space]キーを押し「terminal」と検索して開く

2.  以下のコマンドを実行する
    ```sh
    cd ~/.ssh
    ```
    もし`no such file or directory: ~/.ssh`が出たら
    ```sh
    mkdir ~/.ssh
    ```
    を実行してもう一度`cd ~/.ssh`を実行する

3.  1を実行し、.sshが開けたら`ssh-keygen`を実行する
    ```sh
    ssh-keygen
    ```
    ここではGitHubで推奨されているed25519方式で鍵を作成する

4.  3回ほどEnterキーを押すと実行が完了する。

5.  以下のコマンドを実行すると公開鍵の内容がクリップボードにコピーできる。
    ```sh
    pbcopy < ~/.ssh/id_ed25519.pub
    ```

---

### 共通
#### GitHub側
1.  [GitHub](https://github.com)にログイン

2.  右上のアイコンをクリック→"Setting"（または設定）をクリック

3.  左側の"SSH and GPG key"（またはSSHおよびGPGキー）をクリック

4.  画像の赤枠部分の"New SSH key"をクリック  
![New SSH key button](https://github.com/tsubame-rustica/Frontend/assets/120567038/7ea99dfc-0d5e-4430-8ffc-a3ea25bc7e93)

5. "Title"にはわかりやすい名前を入力し、"Key"には先ほどコピーした公開鍵をペーストします

6.  入力したら"Add SSH key"を押す

#### Powershell(Windows)またはTerminal(Mac)
-   powershell(Terminal)の画面に戻って情報を登録する
    ```sh
    git config --global user.name "Your Name"
    ```
    ```sh
    git config --global user.email "you@example.com"
    ```
