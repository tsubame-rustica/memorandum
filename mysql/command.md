# コマンド

## 目次


## SQLの命名規則
- 日本語を避ける
- 単数形・複数形は統一する
- 略称を避ける
- スネークケースを使用する

## データベースの変更

### データベースの作成
```sql
CREATE DATABASE データベース名;
```

### 使用するデータベースの選択
```sql
USE データベース名;
```

## テーブルの変更

### テーブルの作成
```sql
CREATE TABLE テーブル名 ( カラム名 型, ・・・ );
```

### テーブル名の変更
```sql
ALTER TABLE 変更前のテーブル名 RENAME TO 変更後のテーブル名;
```

### テーブルの構造を表示
```sql
DESC テーブル名;
```

## カラムの変更

### カラムの追加
```sql
ALTER TABLE テーブル名 ADD カラム名 型;
```

### カラムの編集

- **データ型の変更**

    変更したいカラムに対して実行すると型を変更することができる
    ```sql
    ALTER TABLE テーブル名 MODIFY カラム名 型;
    ```

- **カラム名の変更**

    変更したいカラムに対して実行するとカラム名を変更することができる
    ```sql
    ALTER TABLE テーブル名 CHANGE 変更前のカラム名 変更後のカラム名 型;
    ```

### カラムの削除
```sql
ALTER TABLE テーブル名 DROP カラム名;
```


## テーブルの変更
### データの挿入
```sql
INSERT INTO table_name (column_name1, column_name2) VALUES (value1, value2);
```

### データの削除
```sql
DELETE FROM table_name WHERE column_name = value;
```

### データの変更
```sql
UPDATE table_name SET 変更するカラム = 値 WHERE 対象のデータのカラム名 = 値;
```

### データの検索
```sql
SELECT * FROM table_name;
```