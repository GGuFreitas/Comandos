
### **SQL.md** (opcional)
```markdown
# SQL - Comandos Essenciais

## Básico
```sql
SELECT * FROM tabela;
SELECT col1, col2 FROM tabela;
SELECT DISTINCT coluna FROM tabela;
SELECT * FROM tabela WHERE condição;
SELECT * FROM tabela ORDER BY coluna;
SELECT * FROM tabela LIMIT 10;



SELECT * FROM a INNER JOIN b ON a.id = b.id;
SELECT * FROM a LEFT JOIN b ON a.id = b.id;
SELECT * FROM a RIGHT JOIN b ON a.id = b.id;
SELECT * FROM a FULL OUTER JOIN b ON a.id = b.id;



SELECT COUNT(*) FROM tabela;
SELECT SUM(coluna) FROM tabela;
SELECT AVG(coluna) FROM tabela;
SELECT MAX(coluna), MIN(coluna) FROM tabela;
SELECT coluna, COUNT(*) FROM tabela GROUP BY coluna;
SELECT coluna, COUNT(*) FROM tabela GROUP BY coluna HAVING COUNT(*) > 1;


INSERT INTO tabela (col1, col2) VALUES (val1, val2);
UPDATE tabela SET coluna = valor WHERE condição;
DELETE FROM tabela WHERE condição;

CREATE INDEX idx_nome ON tabela(coluna);
DROP INDEX idx_nome;


BEGIN TRANSACTION;
-- comandos
COMMIT;
ROLLBACK;