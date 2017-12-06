# `NOT IN` returns 0 records when set compared against contains `NULL` value

So the query:

```$xslt
SELECT name 
    FROM employees 
    WHERE id NOT IN (1, NULL)
```

will always return an empty set even if there exist employees with `id` greater than 1 and not `NULL`.

In a frequent scenario when a subquery is used:

```$xslt
SELECT name 
    FROM employees 
    WHERE id NOT IN (SELECT managerId FROM employees)
```

you have to be sure that the result of the subquery does not contain `NULL` values. If you are not, use `WHERE` clause in the subquery to filter them out.

```$xslt
SELECT name 
    FROM employees 
    WHERE id NOT IN (SELECT managerId FROM employees WHERE managerId IS NOT NULL)
```