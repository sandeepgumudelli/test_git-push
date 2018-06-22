

Table Syntax
================

* Method 1:

.. code-block:: html

    ============== ================ ======== ============
    Platform        Self Contained?  Cost     Flexibility
    ============== ================ ======== ============
    Rasberry pi       No              $40      Limitless
    Lego Mindstro   Yes             $350     Medium
    ============== ================ ======== ============



Result:

============== ================ ======== ============
Platform        Self Contained?  Cost     Flexibility
============== ================ ======== ============
Rasberry pi       No              $40      Limitless
Lego Mindstro   Yes             $350     Medium
============== ================ ======== ============

* Method 2:

.. code-block:: html

   +--------------+----------------+--------+------------+
   | Platform     | Self Contained?|  Cost  | Flexibility|
   |              |                |        |            |
   +==============+================+========+============+
   | Rasberry pi  |     No         |   $40  | Limitless  |
   +--------------+----------------+--------+------------+
   | Lego Mindstro|   Yes          |   $350 |    Medium  |
   +--------------+----------------+--------+------------+   



Result:

   +--------------+----------------+--------+------------+
   | Platform     | Self Contained?|  Cost  | Flexibility|
   |              |                |        |            |
   +==============+================+========+============+
   | Rasberry pi  |     No         |   $40  | Limitless  |
   +--------------+----------------+--------+------------+
   | Lego Mindstro|   Yes          |   $350 |    Medium  |
   +--------------+----------------+--------+------------+  

* Method 3:

.. code-block:: html

    .. list-table:: Comparison 
       :widths : 20 10 10 15 
       :header-rows: 1

    * - Platform 
        - Self-contained? 
        - Cost 
        - Flexibility 
    * - Raspberry Pi 
        - No 
        - $30 
        - Limitless 
    * - Lego Mindstorms
        - Yes 
        - $350 
        - Medium 


Result:

.. list-table:: Comparison 
   :widths : 20 10 10 15 
   :header-rows: 1

   * - Platform 
     - Self-contained? 
     - Cost 
     - Flexibility 
   * - Raspberry Pi 
     - No 
     - $30 
     - Limitless 
   * - Lego Mindstorms
     - Yes 
     - $350 
     - Medium 

* Method 4:

.. code-block:: html

    .. csv-table:: Comparison 
       :header: Platform, If-contained? , Cost, Flexibility 
       :widths: 15 10 30 30

       Raspberry pi,No,$30,Limitless 
       Lego Mindstorms, Yes, $350,Medium 

Result:

.. csv-table:: Comparison 
   :header: Platform, If-contained? , Cost, Flexibility 
   :widths: 15 10 30 30

   Raspberry pi,No,$30,Limitless 
   Lego Mindstorms, Yes, $350,Medium  