## 🗺️ PHASE 14 - SQL & Databases for AI Engineers

> **Goal:** Query data confidently and design databases that support AI systems.

### 14.1 Core SQL

- `SELECT`, `FROM`, `WHERE`, `ORDER BY`, `LIMIT`, `DISTINCT`
- `AND`, `OR`, `NOT`, `IN`, `BETWEEN`, `LIKE`, `IS NULL`
- `INNER JOIN`, `LEFT JOIN`, `RIGHT JOIN`, `FULL OUTER JOIN`, `SELF JOIN`
- `GROUP BY`, `HAVING`
- Aggregate functions: `COUNT`, `SUM`, `AVG`, `MIN`, `MAX`

### 14.2 Advanced SQL

- CTEs (Common Table Expressions) - `WITH` clauses
- Window functions: `ROW_NUMBER()`, `RANK()`, `DENSE_RANK()`, `LAG()`, `LEAD()`
- `PARTITION BY` vs `GROUP BY`
- `SUM() OVER`, `AVG() OVER` - running totals
- Recursive CTEs - hierarchical data
- Subqueries: correlated vs non-correlated
- `CASE WHEN` conditional logic
- `COALESCE` for NULL handling

### 14.3 AI-Specific SQL Patterns

- Feature engineering queries (ratios, rolling averages)
- Pivoting data for ML features
- Sampling: `ORDER BY RANDOM() LIMIT n`
- JSON columns (`JSON_EXTRACT`, `->` in Postgres)
- **pgvector** - vector similarity search in PostgreSQL
  - `<->` cosine distance operator
  - `<#>` negative inner product
  - `<=>` L2 distance
  - Creating vector indexes (HNSW, IVFFlat)

### 14.4 Database Design for AI Applications

- Schema design for conversation history
- Schema for prompt versions and results
- Schema for token usage tracking
- Schema for user preferences/memory
- Indexing for AI workloads

### 14.5 NoSQL for AI

- **Redis** - session state, caching, rate limiting, pub/sub for streaming
- **MongoDB** - flexible document storage for AI outputs
- **DynamoDB** - serverless, high-throughput
- When to use SQL vs NoSQL for AI applications

---

### 📦 Phase 14 Projects

**🟢 Easy: AI Usage Analytics Dashboard**
- Design and query a database tracking AI API usage
- Build queries: cost per user, top features, error rates
- Stack: PostgreSQL, Python, Metabase/Grafana

**🟡 Medium: pgvector Semantic Search**
- Implement semantic search using pgvector in PostgreSQL
- Store embeddings alongside metadata
- Build efficient HNSW index
- Stack: PostgreSQL + pgvector, FastAPI, OpenAI Embeddings

**🔴 Hard: Complete Database Architecture for AI Platform**
- Design full schema for a multi-tenant AI platform
- Includes: users, conversations, tokens, embeddings, prompt versions, A/B tests
- Implement migrations, indexes, partitioning
- Stack: PostgreSQL, pgvector, Redis, Alembic (migrations)

---

