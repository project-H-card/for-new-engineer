### 1. **データベース作成**
```sql
-- 新しいデータベースを作成
CREATE DATABASE sample_db;

-- 使用するデータベースを選択
USE sample_db;
```

---

### 2. **テーブル作成**
```sql
-- ユーザー情報を格納するテーブルを作成
CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(50) NOT NULL,
    email VARCHAR(100) UNIQUE NOT NULL,
    age INT,
    created_at DATETIME DEFAULT CURRENT_TIMESTAMP
);

-- 商品情報を格納するテーブルを作成
CREATE TABLE products (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(50) NOT NULL,
    price DECIMAL(10, 2) NOT NULL,
    stock INT DEFAULT 0,
    created_at DATETIME DEFAULT CURRENT_TIMESTAMP
);
```

---

### 3. **データの挿入**
```sql
-- ユーザー情報を挿入
INSERT INTO users (name, email, age) VALUES
('Alice', 'alice@example.com', 25),
('Bob', 'bob@example.com', 30),
('Charlie', 'charlie@example.com', 35);

-- 商品情報を挿入
INSERT INTO products (name, price, stock) VALUES
('Laptop', 999.99, 10),
('Mouse', 19.99, 50),
('Keyboard', 49.99, 30);
```

---

### 4. **データの取得**
```sql
-- 全てのユーザー情報を取得
SELECT * FROM users;

-- 商品情報の中で在庫が10以上のものを取得
SELECT * FROM products WHERE stock >= 10;

-- ユーザーの名前とメールアドレスだけを取得
SELECT name, email FROM users;
```

---

### 5. **データの更新**
```sql
-- Bobの年齢を35歳に更新
UPDATE users SET age = 35 WHERE name = 'Bob';

-- 在庫を追加
UPDATE products SET stock = stock + 10 WHERE name = 'Mouse';
```

---

### 6. **データの削除**
```sql
-- Aliceのユーザー情報を削除
DELETE FROM users WHERE name = 'Alice';

-- 在庫が0の商品の情報を削除
DELETE FROM products WHERE stock = 0;
```

---

### 7. **集計とソート**
```sql
-- 平均年齢を計算
SELECT AVG(age) AS average_age FROM users;

-- 在庫数の多い順に商品情報を取得
SELECT * FROM products ORDER BY stock DESC;
```

---

### 8. **テーブルの結合**
```sql
-- ユーザーが購入した商品の履歴を格納するテーブルを作成
CREATE TABLE purchases (
    id INT AUTO_INCREMENT PRIMARY KEY,
    user_id INT,
    product_id INT,
    quantity INT,
    purchased_at DATETIME DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (user_id) REFERENCES users(id),
    FOREIGN KEY (product_id) REFERENCES products(id)
);

-- 購入データを挿入
INSERT INTO purchases (user_id, product_id, quantity) VALUES
(1, 1, 1), -- AliceがLaptopを1つ購入
(2, 2, 2), -- BobがMouseを2つ購入
(3, 3, 1); -- CharlieがKeyboardを1つ購入

-- 購入履歴を取得
SELECT users.name AS user_name, products.name AS product_name, purchases.quantity
FROM purchases
JOIN users ON purchases.user_id = users.id
JOIN products ON purchases.product_id = products.id;
```

---

### 9. **その他の操作**
```sql
-- ユーザーが購入した商品の総数を集計
SELECT users.name AS user_name, SUM(purchases.quantity) AS total_purchased
FROM purchases
JOIN users ON purchases.user_id = users.id
GROUP BY users.name;

-- 商品ごとの購入数を計算
SELECT products.name AS product_name, SUM(purchases.quantity) AS total_sold
FROM purchases
JOIN products ON purchases.product_id = products.id
GROUP BY products.name;
```

---

### 10. **テーブルの削除**
```sql
-- テーブルを削除する場合
DROP TABLE purchases;
DROP TABLE users;
DROP TABLE products;

-- データベースを削除する場合
DROP DATABASE sample_db;
```