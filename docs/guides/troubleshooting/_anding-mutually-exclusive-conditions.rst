Using AND to require mutually exclusive conditions
--------------------------------------------------


.. csv-table:: people
   :header: "Name", "Birthdate"
   :widths: 60, 40

   "Alice","1980-12-01"
   "Bob","1980-12-01"
   "Candice","1980-12-01"
   "Daniel","1980-12-01"



.. code-block:: sql

    SELECT * FROM people
    WHERE
        birthdate = 1972
        AND birthdate = 1980


This is a common mistake, owing to the way we imprecisely express things in everyday English, e.g.

    I want people born on 1972 *and* 1982

As a shorthand for:

    I want the people born on 1972 *and* the people born on 1982.

The better shorthand is:

    I want people born on 1972 *or* on 1982.


The fix for this is simply:

.. code-block:: sql

    SELECT * FROM people
    WHERE
        birthyear = 1972
        OR birthyear = 1980







