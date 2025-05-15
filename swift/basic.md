# Swiftの基本
## SwiftUIの基本
### Stackについて
stackは文字をグループ化するときに使える
- VStack  
Vertical Stackの略で縦方向に要素を並べる

- HStack  
Horizonal Stackの略で横方向に要素を並べる

- ZStack  
要素を重ねて並べる(Z軸上に並べる)


### Buttonについて
```swift
Button (action: {
    // ボタンを押すとここが呼ばれる
}) {
    Text("button")
}
```

### 画像の表示
- 自身でAssetにD&Dした画像を表示する場合
    ```swift
    Image("ファイル名")
    ```

- システムのアイコンを使う場合
    ```swift
    Image(systemName: "car")
    ```

### List
```swift
List {
    Text("Apple")
    Text("Orange")
    Text("Banana")
}
```

### TextField
`TextField`を使用する場合には`＠State`で変数を宣言する必要がある
```swift
struct ContentView: View {
    @State var inputText = ""

    var body : some View {
        TextField("ここに文字列を入力します", text : $inputText)
    }
}
```
![image](https://github.com/user-attachments/assets/abefe1fd-3395-4256-b089-17b04bf624f4)


### Toggle
```swift
struct ContentView: View {
    @State var isOn = false

    var body : some View {
        Toggle("Toggle", isOn: $isOn)
    }
}
```
![image](https://github.com/user-attachments/assets/0fc99a35-d29f-4e89-9eb1-706bdb4ec240)