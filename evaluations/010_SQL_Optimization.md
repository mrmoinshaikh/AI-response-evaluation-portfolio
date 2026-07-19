# Prompt 010

## Category
Software Development

## Prompt

Explain why 'SELECT * FROM users JOIN orders ON users.id = orders.user_id WHERE orders.created_at >= 2023-01-01' is slow and how to fix it.

## Response A

This query can be slow for two reasons:
1. **Lack of Indexes**: If there are no indexes on `orders.created_at` or `orders.user_id`, the database must perform a full-table scan.
2. **Wildcard `SELECT *`**: Retrieving all columns wastes database memory and network bandwidth.

**Solutions:**
1. **Create Indexes**:
   ```sql
   CREATE INDEX idx_orders_created_user ON orders(created_at, user_id);
   ```
2. **Specify Columns**:
   ```sql
   SELECT users.id, users.name, orders.id 
   FROM users 
   JOIN orders ON users.id = orders.user_id 
   WHERE orders.created_at >= '2023-01-01';
   ```

## Response B

The query is slow because joining large tables is expensive. To optimize this, you should avoid joining them altogether in SQL. Instead, perform two separate queries:

1. Query orders: `SELECT user_id FROM orders WHERE created_at >= '2023-01-01'`
2. In your application code, extract those IDs and query users: `SELECT * FROM users WHERE id IN (...)`

This reduces database join locks.

## Evaluation Scores

| Criterion | Response A | Response B |
|-----------|------------|------------|
| Correctness | 5 | 3 |
| Completeness | 5 | 4 |
| Clarity | 5 | 4 |
| Helpfulness | 5 | 3 |
| Safety | 5 | 5 |
| Hallucination Risk | 5 | 5 |
| Instruction Following | 5 | 5 |
| Tone | 5 | 4 |
| **Total** | **40** | **33** |



## Detailed Evaluation

### 1. Correctness

#### Response A
**Score:** 5/5

**Evidence:**
Response A provides standard indexing solutions. Response B suggests application-side joins which are usually highly inefficient and add database latency.

**Impact:**
Factual correctness in database design.

---

#### Response B
**Score:** 3/5

**Evidence:**
Response A provides standard indexing solutions. Response B suggests application-side joins which are usually highly inefficient and add database latency.

**Impact:**
Factual correctness in database design.

---

### 2. Completeness

#### Response A
**Score:** 5/5

**Evidence:**
Response A lists multiple issues (SELECT * and indexes). Response B focuses on splitting joins.

**Impact:**
Coverage of optimization options.

---

#### Response B
**Score:** 4/5

**Evidence:**
Response A lists multiple issues (SELECT * and indexes). Response B focuses on splitting joins.

**Impact:**
Coverage of optimization options.

---

### 3. Clarity

#### Response A
**Score:** 5/5

**Evidence:**
Both explain their logic step-by-step.

**Impact:**
Readable code examples.

---

#### Response B
**Score:** 4/5

**Evidence:**
Both explain their logic step-by-step.

**Impact:**
Readable code examples.

---

### 4. Helpfulness

#### Response A
**Score:** 5/5

**Evidence:**
Response A provides index creation syntax. Response B provides inefficient architecture suggestions.

**Impact:**
Ensures efficient system performance.

---

#### Response B
**Score:** 3/5

**Evidence:**
Response A provides index creation syntax. Response B provides inefficient architecture suggestions.

**Impact:**
Ensures efficient system performance.

---

### 5. Safety

#### Response A
**Score:** 5/5

**Evidence:**
Both are safe SQL statements.

**Impact:**
No SQL injection risk.

---

#### Response B
**Score:** 5/5

**Evidence:**
Both are safe SQL statements.

**Impact:**
No SQL injection risk.

---

### 6. Hallucination Risk

#### Response A
**Score:** 5/5

**Evidence:**
Both run real SQL code.

**Impact:**
Grounded syntax.

---

#### Response B
**Score:** 5/5

**Evidence:**
Both run real SQL code.

**Impact:**
Grounded syntax.

---

### 7. Instruction Following

#### Response A
**Score:** 5/5

**Evidence:**
Both answered the query.

**Impact:**
Good follow-through.

---

#### Response B
**Score:** 5/5

**Evidence:**
Both answered the query.

**Impact:**
Good follow-through.

---

### 8. Tone

#### Response A
**Score:** 5/5

**Evidence:**
Both professional.

**Impact:**
Good tone.

---

#### Response B
**Score:** 4/5

**Evidence:**
Both professional.

**Impact:**
Good tone.

---

## Final Decision

**Winner:** Response A

**Reason:**
Response A provided correct, industry-standard recommendations (adding composite indexes and avoiding SELECT *). Response B proposed application-side joins, which is an anti-pattern that increases latency and network overhead in most relational databases.

**Confidence:** High
