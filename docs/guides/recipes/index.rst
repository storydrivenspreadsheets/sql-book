*******
Recipes
*******



Joins
=====

- Find all values in one table without corresponding value in another.


Rollups and aggregations
========================

SELECT top N from each category
-------------------------------

.. code-block:: sql

    SELECT
        id, sex, name, age
    FROM
        people
    WHERE
        people.id IN (
            SELECT id
            FROM people AS px
            WHERE px.id = people.id
            ORDER BY result DESC
            LIMIT 3)
    ORDER BY
        sex ASC,
        age DESC;
