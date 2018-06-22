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

   tea_

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

.. code::

   tea_ticket


Ejemplo tabla
-------------

.. code::

    equipos     ->  t_teams
    -----------     ------------
    id          ->  tea_pteams
    cod_ine     ->  tea_fcities
    provincia   ->  tea_fregions
    competicion ->  tea_fcomps
    nombre      ->  tea_name
    id_equipo   ->  tea_ticker


Ejemplo maestra
---------------

.. code::

    competiciones  ->  m_comps
    -------------      ----------
    id             ->  com_pcomps
    nombre         ->  com_name

Ejemplo SQL
-----------

.. code:: SQL

    SELECT equipos.id, id_equipos, equipos.nombre, competiciones.nombre
    FROM equios, competiciones
    WHERE competicion = competiciones.id;

.. code:: SQL

    SELECT tea_pteams, tea_ticker, tea_name, com_name
    FROM t_teams, t_comps
    WHERE tea_fcomps = com_pcomps;

Ejemplo N-N
-----------

.. code::

    r_teams_comps
    ---------------
    rtc_pteamscomps
    rtc_fteams
    rtc_fcomps

