# 🔥 ACID Properties in DBMS (One-by-One)

ACID stands for:

> **A**tomicity
> **C**onsistency
> **I**solation
> **D**urability



## ✅ 1. **Atomicity** — *"All or Nothing"*

### 💡 Meaning:

* A transaction must be **fully completed** or **not executed at all**.
* If any part of the transaction fails, the whole thing is **rolled back**.

### 📦 Real-Life Example:

> Sending money from your bank account to a friend:
>
> * Debit ₹100 from you ✅
> * Credit ₹100 to friend ✅
>   ❌ If the second part fails, your ₹100 should **not be deducted**!

### 🔧 SQL Example:

```sql
START TRANSACTION;

UPDATE accounts SET balance = balance - 100 WHERE id = 1;
-- Suppose this next query fails
UPDATE accounts SET balance = balance + 100 WHERE id = 999; -- wrong ID

ROLLBACK;
```

✅ Since one step failed, the whole transaction is undone — **that’s Atomicity**.

---

### ✅ 2. **Consistency** — *"Data must be valid before and after"*

### 💡 Meaning:

* The database must always move from **one valid state to another**.
* No rule or constraint should be violated after a transaction.

### 📦 Real-Life Example:

> A table has a constraint that **balance cannot go negative**.
> A transaction must **never violate** that, no matter what.

### 🔧 SQL Example:

```sql
-- Constraint exists: CHECK (balance >= 0)
START TRANSACTION;

UPDATE accounts SET balance = balance - 10000 WHERE id = 1; -- may break rule

-- If it breaks the CHECK constraint, it fails automatically
COMMIT;
```

✅ Database engine prevents invalid data — **that’s Consistency**.

---

### ✅ 3. **Isolation** — *"Transactions don’t mess with each other"*

### 💡 Meaning:

* Transactions run **independently**, like they are alone in the system.
* Changes made in one transaction are **not visible** to others until committed.

### 📦 Real-Life Example:

> You're booking a movie ticket at the same time as your friend — both should **not get the same seat**.

### 🔧 SQL Simulation:

#### 🧪 T1:

```sql
SET TRANSACTION ISOLATION LEVEL REPEATABLE READ;
START TRANSACTION;

SELECT * FROM seats WHERE id = 1;
-- Shows available
```

#### 🧪 T2:

```sql
UPDATE seats SET status = 'booked' WHERE id = 1;
COMMIT;
```

#### 🔁 Back to T1:

```sql
SELECT * FROM seats WHERE id = 1;
-- Still sees "available" because of repeatable read
```

✅ That’s **Isolation** — protects your transaction's view.

> Want to go deeper? We already simulated **READ COMMITTED**, **REPEATABLE READ**, and **SERIALIZABLE** earlier.

---

### ✅ 4. **Durability** — *"Once committed = forever"*

### 💡 Meaning:

* Once a transaction is committed, its data is **permanently saved** — even if the server crashes right after.

### 📦 Real-Life Example:

> You made a payment. Even if the server crashes right after, your transaction should be safe.

### 🔧 SQL Example:

```sql
START TRANSACTION;

INSERT INTO orders (user_id, amount) VALUES (1, 499);
COMMIT;
```

✅ After `COMMIT`, the row is saved to disk (via transaction logs) and won’t be lost.

---

## 📚 Final Summary Table:

| Property        | Ensures...                    | Example Keyword                         |
| --------------- | ----------------------------- | --------------------------------------- |
| **Atomicity**   | All steps succeed or all fail | `ROLLBACK`                              |
| **Consistency** | Data always follows rules     | Constraints like `CHECK`, `FOREIGN KEY` |
| **Isolation**   | Transactions don’t interfere  | `ISOLATION LEVEL`                       |
| **Durability**  | Committed data is never lost  | `COMMIT`                                |


