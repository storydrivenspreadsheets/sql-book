**************
SQL Styleguide
**************

Goals
=====

Minimize errors to the programmer
Minimize errors to the reader

Remember that you will always spend more time writing code than reading it.

Main concerns
=============

- Capitalization of keywords
- Line length
- Explicitness

    + INNER JOIN not JOIN
    + AS for aliasing
    + ASC, DESC
    + One table for FROM
    + Avoid *



Visual layout and characteristics
=================================


- Capitalization
- Indentation
- Line length
- double-quote identifiers


Reference conventions
=====================

- Always use AS for aliasing
- Be explicit about sorting order
- Include table prefixes
- Be explicit about column selection (avoid ``*``)

Do not include non aggregate columns in an aggregation
------------------------------------------------------


Bad:

.. code-block:: sql

    SELECT name, sex, COUNT(*)
      FROM people
  GROUP BY sex;


Good:

.. code-block:: sql

        SELECT sex, COUNT(*)
          FROM people
      GROUP BY sex;





Naming conventions
==================

- snakecase when possible
- avoid words that look like keywords
- plural for table names
- singular for column names


Values
======

- ISO time format


Query structure
===============

- Use CTE for nested queries
- Put JOIN specific conditions in the ON clause, not WHERE


Boolean
=======

- BETWEEN for ranges instead of AND
- IN instead of OR


