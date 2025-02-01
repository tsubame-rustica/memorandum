# TypeScriptの型
## 基本の型
- `boolean`: 真偽値。
- `number`: 数値。
- `string`: 文字列。
- `undefined`: 値が定義されていない状態を示す。
- `null`: 値が存在しない状態を示す。
- `bigint`: 大きな整数。
- `symbol`: 一意の値を示す。

```ts
const isReady       : boolean   = false;
const age           : int       = 20;
const name          : string    = 'Jane Doe';
const setUndefined  : undefined = undefined;
const setNull       : null      = null;
const bigNumber     : bigint    = 100n; 
const uniqueSymbol  : symbol    = Symbol("unique");
```

##　型エイリアス
既存の型を組み合わせて新しい型を作ることができる
```ts
type StringOrNumber = String | Number;
let value   = StringOrNumber;
value   = "hoge";
value   = 20;