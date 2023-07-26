Getting start
===================

step 1: Create Database Object
^^^^^^^^^^^^^^^^^^^^^^^^^^
You can manage cameras using Collector class . Use ``get_all_cameras`` function to get all connected cameras.
for more information see chapter :doc:`manageـdeviceـbyـCollector`

.. code-block:: python

   import dorsa_Database
   from dorsa_Database import database

   db=dataBase('__user_name__','__password__','__host__','__schema_name__')

   #-----------------------------------------------------------------
   #get all avialble cameras 
   all_cameras = collector.get_all_cameras(camera_class=None)

