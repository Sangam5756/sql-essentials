
# 🔒 What is an **Isolation Level** in Databases?

## ✅ Simple Definition:

> **Isolation level** controls **how much one transaction is allowed to see or interfere with another transaction.**

It defines **what happens** when two people (or systems) try to **read or write** to the **same data at the same time**.

---

## 🎯 Why It's Needed:

Imagine these situations:

* You're transferring money.
* Someone else is booking the same train seat.
* Two apps are reading and updating the same user profile.

👉 Without isolation, you can get **weird bugs** like:

* Reading **uncommitted changes**
* Seeing **different values** for the same row
* Getting **duplicate or missing results**

---

## 🔁 Analogy:

Think of a database as a **kitchen**.

* You (T1) are making a cake.
* Your friend (T2) is making tea.

### Isolation Level decides:

> **Can both work at once, and what happens if they touch the same ingredient (data)?**



# 🔒 MySQL Isolation Levels Explained


## 📌 1. **READ COMMITTED** – *“I’ll wait until you’re done”*

### 🧠 Meaning:

* You only see **committed changes** from other transactions.
* But you can still see **different values on re-read** (non-repeatable read).

### 🔥 Problems:

* ❌ Non-repeatable reads
* ❌ Phantom rows

### 💡 Example:

#### T1:

```sql
START TRANSACTION;
SELECT balance FROM users WHERE id = 1;
-- Output: ₹1000
-- Wait...
```

#### T2:

```sql
UPDATE users SET balance = 500 WHERE id = 1;
COMMIT;
```

#### Back to T1:

```sql
SELECT balance FROM users WHERE id = 1;
-- Output: ₹500 (value changed)
```

✅ No dirty reads
❌ Not repeatable

---


## 📌 2. **READ UNCOMMITTED** – *“I’ll take whatever you got”*

### 🧠 Meaning:

* You can see **uncommitted changes** from other transactions.

### 🔥 Problems:

* Allows **dirty reads**, **non-repeatable reads**, and **phantoms**.

### 💡 Example:

#### T1:

```sql
START TRANSACTION;
UPDATE users SET balance = 0 WHERE id = 1;
-- Not yet committed
```

#### T2 (READ UNCOMMITTED):

```sql
SELECT balance FROM users WHERE id = 1;
-- Sees balance = 0 even though not committed
```

✅ Fast, but ❌ very unsafe.

---

## 📌 3. **REPEATABLE READ** – *“Lock the snapshot for me”* (✅ MySQL’s default)

### 🧠 Meaning:

* You get a **consistent snapshot** for the entire transaction.
* You’ll **always see the same rows** when reading again.
* But **phantom rows can appear**.

### 🔥 Problems:

* ❌ Phantom reads
* ✅ Repeatable reads (no value change on second read)

### 💡 Example:

#### T1:

```sql
START TRANSACTION;
SELECT * FROM users WHERE age > 25;
-- Returns 2 rows
```

#### T2:

```sql
INSERT INTO users (name, age) VALUES ('NewGuy', 30);
COMMIT;
```

#### Back to T1:

```sql
SELECT * FROM users WHERE age > 25;
-- Still sees only 2 rows (NewGuy is hidden)
```

✅ Same rows repeat
❌ Phantoms if new rows are inserted into the range

---

## 📌 4. **SERIALIZABLE** – *“Only one of us can touch this”*

### 🧠 Meaning:

* Transactions are executed **as if they were one-by-one**.
* No dirty, no non-repeatable, and **no phantom** reads.

### 🔥 Strictest, but **slower** because it uses **locks** on reads.

### 💡 Example:

#### T1:

```sql
SET TRANSACTION ISOLATION LEVEL SERIALIZABLE;
START TRANSACTION;
SELECT * FROM users WHERE name LIKE 'A%';
```

#### T2:

```sql
INSERT INTO users (name) VALUES ('Aman');
-- ❌ BLOCKED until T1 commits
```

#### T3:

```sql
INSERT INTO users (name) VALUES ('Zara');
-- ❌ Also blocked if no index on name
```

✅ Absolute safety
❌ Lower concurrency

---

## 📊 Summary Table

| Isolation Level  | Dirty Read | Non-Repeatable Read | Phantom Read | Safe?        | MySQL Default |
| ---------------- | ---------- | ------------------- | ------------ | ------------ | ------------- |
| READ UNCOMMITTED | ✅ Yes      | ✅ Yes               | ✅ Yes        | ❌ Unsafe     | ❌ No          |
| READ COMMITTED   | ❌ No       | ✅ Yes               | ✅ Yes        | ⚠️ Medium    | ❌ No          |
| REPEATABLE READ  | ❌ No       | ❌ No                | ✅ Yes        | ✅ Good       | ✅ Yes         |
| SERIALIZABLE     | ❌ No       | ❌ No                | ❌ No         | ✅✅ Very Safe | ❌ No          |

---

## 📌 How to Set Isolation Level

```sql
SET SESSION TRANSACTION ISOLATION LEVEL REPEATABLE READ;
START TRANSACTION;
-- Do your queries
COMMIT;
```
