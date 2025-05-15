# モディファイア

## 目次
-  [モディファイアのルール](#モディファイアのルール)
- [色の指定](#色の指定)
    - [foregroundColor](#foregroundcolor)
    - [background](#background)


## モディファイアのルール
1.  モディファイアの優先順位  
モディファイアは上に書いた方が優先される

2. モディファイアは上から実行される  
例えば、`.padding()`→`.background()`の順番で実行するのと`background()`→`.padding()`の順番で実行するのとでは挙動が異なる
    - `.padding()`→`.background()`

        ```swift
        Text("Hoge")
        .padding()
        .bacjground(.yellow)
        ```
        ![Image](https://github.com/user-attachments/assets/98818e3a-cf06-437f-b953-ab3ba5000c4e)
    ---
    - `background()`→`.padding()`

        ```swift
        Text("Hoge")
        .background(.yellow)
        .padding()
        ```
        ![Image](https://github.com/user-attachments/assets/b04ef334-12b1-423c-a6c0-57074f4eea04)

## 色の指定
### foregroundColor
文字の色を設定できる
```swift
Text("Hoge")
.foreground(.red)
```

### background
```swift
Text("Hoge")
.background(.green)
```

## 余白の指定
### padding
`.padding`でオブジェクトに余白をつけることができる。
- `.padding(50)`のように()内に数字を入れると余白の大きさを指定できる

- `.padding(.top)`のように()内に`.top`と入れると上側に余白を入れることができる（下や左右も同様に可能）

- `.padding(.top, 50)`のように(方向, 数値)で特定の方向の余白の大きさを指定できる


## 大きさや文字揃えの指定
### frame