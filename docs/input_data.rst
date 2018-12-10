Input Data
==========

Excel File Upload
-----------------

The Attributes & Levels input file follows a detailed specification.

Two worksheets must be present, names ``Attributes&Levels (2)`` and ``Design Matrix``

Attributes&Levels (2)
---------------------

Row 1 is blank, and is not read by the importer. This row can be used for any human readable titles

Row 2, Column A must say ``Level``. The rest of this row are the titles of each attribute, lower case, without spaces, one per column. ie "Average Fuel" may become "fuelav".

Row 3 defines the type of attribute each column is describing. This will tell the system how to use each value in the table. Valid entries are ``option``, ``option_nolabel``, ``multiplier``.

Row 4 begins the available choices for each attribute. The ``Level`` column is a number for the option, zero indexed.

* If the column is of type ``option``, each row is simply the human readable text which will be presented to the user.

* If the column is of type ``text``, each row is simply the human readable text which will be presented to the user.

* If the column is of type ``option_nolabel``, this is a number (integer, float) which will be presented to the user.

* If the column is of type ``multiplier``, this is a number (integer, float) which will be multiplied by some user entered data as the participant completes the survey.

.. note::

    For example, if "1.2" is entered as one level, and 0.8 as another level, and a survey question asks "What is your current monthly phone bill?". This figure will be multiplied by 1.2 and 0.8 and presented to the user in the resultant table. If the user inputs £10, the table will show options £8 and £12.

* If the column is of type ``addition``, this is a number (integer, float) which will be added to, or subtracted from, some user entered data as the participant completes the survey.

* If the column is of type ``geographic``, this is a place name, and will be used for presenting on a map in some user interfaces.

* If the column is of type ``boolean``, this will be used for True/ False questions. A ``0`` in this cell will return the unicode character of a cross ``&#10060; or U+274C`` |unicode_cross|. Anything other than a ``0`` will return the unicode for a tick/ check mark ``&#10004; or U+2714`` |unicode_tick|.


.. |unicode_cross| unicode:: U+274C .. unicode cross
.. |unicode_tick| unicode:: U+2714 .. unicode tick




Design matrix 2
---------------

Choice situation, Block numbers, attributes and the multipliers for each situation.

