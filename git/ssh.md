# GitHubとssh接続できるようにする
GitHub上とローカルでやり取りをするためには公開鍵の登録が必要です

※githubアカウントは作成済みの前提

## 接続手順
### Windowsの場合
#### Powershell側
1.  [windows]キーを押して「powershell」と検索して開く  
    **秘密鍵は公開しないようにしてください**

2.  以下のコマンドを実行する
    ```ps
    cd ~/.ssh
    ```
    もし`no such file or directory: ~/.ssh`が出たら
    ```ps
    mkdir ~/.ssh
    ```
    を実行してもう一度`cd ~/.ssh`を実行する

3.  1を実行し、.sshが開けたら`ssh-keygen`を実行する

4.  3回ほどEnterキーを押すと実行が完了する。

5.  `clip < ~/.ssh/id_ed25519.pub`を実行すると公開鍵の内容がクリップボードにコピーできる。

### Macの場合
#### Terminal側

1.  [command] + [space]キーを押し「terminal」と検索して開く

2.  以下のコマンドを実行する
    ```ps
    cd ~/.ssh
    ```
    もし`no such file or directory: ~/.ssh`が出たら
    ```ps
    mkdir ~/.ssh
    ```
    を実行してもう一度`cd ~/.ssh`を実行する

3.  1を実行し、.sshが開けたら`ssh-keygen`を実行する

4.  3回ほどEnterキーを押すと実行が完了する。

5.  `pbcopy < ~/.ssh/id_ed25519.pub`を実行すると公開鍵の内容がクリップボードにコピーできる。
---

### 共通
#### GitHub側
1.  [GitHub](https://github.com)にログイン

2.  右上のアイコンをクリック→"Setting"（または設定）をクリック

3.  左側の"SSH and GPG key"（またはSSHおよびGPGキー）をクリック

4.  画像の赤枠部分の"New SSH key"をクリック  <img width="700" alt="New SSH key button" src="https://github.com/tsubame-rustica/Frontend/assets/120567038/7ea99dfc-0d5e-4430-8ffc-a3ea25bc7e93">

5. "Title"にはわかりやすい名前を入力し、"Key"には先ほどコピーした公開鍵をペーストします

6.  入力したら"Add SSH key"を押す

#### Powershell(Windows)またはTerminal(Mac)
1.  powershellの画面に戻って`ssh -T git@github.com`を実行します

2.  ```Hi (アカウント名)! You've successfully authenticated, but GitHub does not provide shell access.```が返ってくればSSh接続ができています。エラーが返ってきたときはどこかが間違っているということなのでもう一度正しいかどうか見直してみてください。