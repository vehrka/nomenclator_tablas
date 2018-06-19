Nomenclator de tablas
=====================

Nombres de las tablas
---------------------

**Identificador del tipo de tabla:**

   +-----+----------------+
   | t\_ | tabla          |
   +-----+----------------+
   | m\_ | maestra        |
   +-----+----------------+
   | a\_ | auxiliar       |
   +-----+----------------+
   | g\_ | geographica    |
   +-----+----------------+
   | r\_ | relación (N-N) |
   +-----+----------------+
   | v\_ | vista          |
   +-----+----------------+

Se puede extender también a otros elementos


   +------+--------------------------+
   | i\_  | índice                   |
   +------+--------------------------+
   | pk\_ | nombre de clave primaria |
   +------+--------------------------+


**Nombre de tabla:**

* Corto, conciso, definitorio y en plural

* Preferentemente en inglés

.. code::

   t_teams

* Elegir nombres únicos en el tablespace

* Resumir en 3 carácter es que sean únicos en el tablespace

.. code::

   tea

Nombres de los campos
---------------------

* Empieza siempre con los 3 *Carácteres resumen* de la tabla
  y a continuación un guión bajo "_"

de esa forma siempre serán únicos en las consultas.

.. code::

   tea\_

El resto del nombre se forma así

* Si  es:

  + Clave primaria:

.. code::

    p + nombre tabla

.

  + Clave foránea:

.. code::

    f + nombre tabla

Rest del nombre nombres:

  + Corto, conciso, definitorio
  + Preferentemente en inglés


Ejemplo tabla
-------------

.. code::

    t_teams
    -------------------
    tea_pteams
    tea_fcities
    tea_fregions
    tea_fcomps
    tea_name
    tea_ticker


Ejemplo maestra
---------------

.. code::

    m_comps
    -------------------
    com_pcomps
    com_name

Ejemplo SQL
-----------


.. code:: SQL

    SELECT tea_pteams, tea_ticker, tea_name, com_name
    FROM t_teams, t_comps
    WHERE tea_fcomps = com_pcomps;

