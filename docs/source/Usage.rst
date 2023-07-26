Usage
==============================

Introduction
^^^^^^^^^^^^^^^^^^
In the Bible, we have given brief explanations along with example codes

Create Schema
^^^^^^^^^^^^^^^^^^^^^^^^^^^
this function used to create schema, 
when you create your connection if your schema there was not , code will auto create a schema

.. code-block:: python

   import dorsa_Database
   from dorsa_Database import dataBase

   db = dataBase('__user_name','__password','__localhost','__schema_name__')

   db.create_schema('__schema_name__')



Creaete Table
^^^^^^^^^^^^^^^^^^^^^^^^^^^
if want to create only use below function or , use add column that automatic create table
If you repeat it again, there will be no problem.

.. code-block:: python

   import dorsa_Database
   from dorsa_Database import dataBase

   db = dataBase('__user_name','__password','__localhost','__schema_name__')

   db.create_table('__table_name__') 


Get all Schemas
^^^^^^^^^^^^^^^^^^^^^^^^^^^
if want to create only use below function or , use add column that automatic create table

.. code-block:: python

   import dorsa_Database
   from dorsa_Database import dataBase

   db = dataBase('__user_name','__password','__localhost','__schema_name__')

   schemas=db.get_all_schemas()

   print(schemas)
   ['test','test2','test3']

Delete Table
^^^^^^^^^^^^^^^^^^^^^^^^^^^
Use this function to delete the table from the database

.. code-block:: python

   import dorsa_Database
   from dorsa_Database import dataBase

   db = dataBase('__user_name','__password','__localhost','__schema_name__')

   db.delete_table('__table_name__')



Add Column
^^^^^^^^^^^^^^^^^^^^^^^^^^^
Use this function to add a column to the table you want and enter the required items including: length - type - default, etc.
If you repeat it again, there will be no problem.

.. code-block:: python

   import dorsa_Database
   from dorsa_Database import dataBase

   db = dataBase('__user_name','__password','__localhost','__schema_name__')

   db.add_column(table_name='__table_name__',col_name='__column_name__',type='VARCHAR or INT or etc',len=0,Null=NOT_NULL)



Get Content of table
^^^^^^^^^^^^^^^^^^^^^^^^^^^
   Retrieves all content from the specified table.

      Args:
         table_name (str): The name of the table from which to retrieve the content.
         limit (bool): Optional. If True, limits the number of records returned by limit_size.
               Default is False.
         limit_size (int): Optional. The maximum number of records to retrieve if limit is True.
               Default is 20.
         offset (int): Optional. The number of records to skip before retrieving the content.
               Default is 0.
         reverse_order (bool): Optional. If True, retrieves the content in reverse order.
               Default is False.
         column_order (str): Optional. The name of the column used for sorting the content.
               Default is 'id'.

      Returns:
         list: A list of dictionaries representing the content. Each dictionary contains
               the field names as keys and corresponding field values as values.

.. code-block:: python

   import dorsa_Database
   from dorsa_Database import dataBase

   db = dataBase('__user_name','__password','__localhost','__schema_name__')

   content = db.delete_table('__table_name__')




Get Column Name
^^^^^^^^^^^^^^^^^^^^^^^^^^^
   Retrieves the column names of the specified table.

   Args:
      table_name (str): The name of the table from which to retrieve column names.
      without_auto_increment (bool): Optional. If True, excludes the auto-increment column(s)
            from the returned list of column names. Default is False.

   Returns:
      list: A list of column names as strings.
.. code-block:: python

   import dorsa_Database
   from dorsa_Database import dataBase

   db = dataBase('__user_name','__password','__localhost','__schema_name__')

   db.get_col_name('__table_name__')


Add Record
^^^^^^^^^^^^^^^^^^^^^^^^^^^
   this function is used to add a new record to table

   Inputs:
      table_name : name of table
      data: data that want to add to the database
   
   Returns: Flag of doing query
   
.. code-block:: python

   import dorsa_Database
   from dorsa_Database import dataBase

   db = dataBase('__user_name','__password','__localhost','__schema_name__')

   db.add_column(table_name='__table_name__',col_name='__column_name__',type='VARCHAR or INT or etc',len=0,Null=NOT_NULL)


Add Record with dictionary
^^^^^^^^^^^^^^^^^^^^^^^^^^^
   Add a new record to the specified database table using a dictionary of column-value pairs.

   Parameters:
      table_name (str): The name of the table where the record will be added.
      data (dict): A dictionary containing column names as keys and their corresponding values
                  for the new record to be inserted into the table.

   Returns:
      None

   This method takes the input `data` dictionary, extracts the values corresponding to the columns
   of the specified `table_name`, and then adds a new record to the table using the `add_record` method.

   The `add_record` method is assumed to be defined elsewhere and is responsible for executing the
   actual database insertion operation.
 
.. code-block:: python

   import dorsa_Database
   from dorsa_Database import dataBase

   db = dataBase('__user_name','__password','__localhost','__schema_name__')
   data = {'first_name':'milad','email':'m.moltaji','last_name':'moltaji'}

   db.add_record_dict('__table_name__',data)


Update Record
^^^^^^^^^^^^^^^^^^^^^^^^^^^
   this function used to update a row with input parms

      Inputs:
            table_name (str): name of that table we want to change data
            col_name (str): column name of table
            value (str): new vlaue
            id_name (str): name of column for selecting the row 
            id_value (str): Row specifier
      
      Returns: Flag of doing query
   
.. code-block:: python

   import dorsa_Database
   from dorsa_Database import dataBase

   db = dataBase('__user_name','__password','__localhost','__schema_name__')

   db.update_record(table_name='__table_name__',col_name='__column_name__',value='__new_value__',id_name='__name_of_column__',id_value='__name_of_row__')



Update Record with Dictionay
^^^^^^^^^^^^^^^^^^^^^^^^^^^
   like update record just with a dictionay for multi updates
   
.. code-block:: python

   import dorsa_Database
   from dorsa_Database import dataBase

   db = dataBase('__user_name','__password','__localhost','__schema_name__')

   edit_data = {'first_name':'amir','email':'amir.malek'}

   db.update_record_dict(table_name='__table_name__',data=edit_data,id_name='__name_of_column__',id_value='__name_of_row__')


Remove Record
^^^^^^^^^^^^^^^^^^^^^^^^^^^
   for remove of specifc row with column name and its value
   
.. code-block:: python

   import dorsa_Database
   from dorsa_Database import dataBase

   db = dataBase('__user_name','__password','__localhost','__schema_name__')

   edit_data = {'first_name':'amir','email':'amir.malek'}

   db.remove_record(table_name='__table_name__',col_name='__column_name__',value='__value_of_row__')


search Record
^^^^^^^^^^^^^^^^^^^^^^^^^^^
   Searches the specified table for records matching the given column name and value.

   Args:
      table_name (str): The name of the table to search.
      col_name (str): The name of the column to match against.
      value (Any): The value to search for. It will be converted to a string for comparison.

   Returns:
      list: A list of dictionaries representing the matching records. Each dictionary contains
            the field names as keys and corresponding field values as values.

.. code-block:: python

   import dorsa_Database
   from dorsa_Database import dataBase

   db = dataBase('__user_name','__password','__localhost','__schema_name__')

   search=db.search(table_name='__table_name__',col_name='__column_name__',value='__value_of_you_want__')