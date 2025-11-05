# ColPali Inspection Reports

Dataset for exploring ColPali visual document search with SQL Server 2025.

## Contents

- 40 inspection report PDFs (80 pages total)
- SQL Server 2025 database backup with ColPali embeddings
- 78,280 vectors (1,030 patches per page, 128 dimensions each)

## Database

The SemanticVisionDB database contains two tables with VECTOR(128) columns:

**PageEmbeddings** - Stores embeddings for each document patch
**QueryEmbeddings** - Stores embeddings for query text

Queries use VECTOR_DISTANCE with cosine similarity to find similar pages.

## Setup

Requires SQL Server 2025 RC1 or later.

Restore the database:

```sql
RESTORE DATABASE SemanticVisionDB
FROM DISK = 'path\to\database\SemanticVisionDB.bak'
WITH MOVE 'SemanticVisionDB' TO 'path\to\SemanticVisionDB.mdf',
     MOVE 'SemanticVisionDB_log' TO 'path\to\SemanticVisionDB_log.ldf';
```

## Files

```
pdfs/          40 inspection report PDFs
database/      SemanticVisionDB.bak (40 MB)
```

## Contact

Joe Sack Consulting LLC
https://github.com/MrJoeSack
