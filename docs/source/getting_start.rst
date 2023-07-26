Getting start
===================

step 1: Create Database Object
^^^^^^^^^^^^^^^^^^^^^^^^^^
first create an object from dorsa_database with your sql username and password for create connection and set your database naem.
if there is not schema this schema name , code will create it automatic.

.. code-block:: python

   import dorsa_Database
   from dorsa_Database import database

   db=dataBase('__user_name__','__password__','__host__','__schema_name__')

   #-----------------------------------------------------------------

