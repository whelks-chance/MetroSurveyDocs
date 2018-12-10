Admins
======

Admin instructions

Installation
------------

The MetroSurvey platform is a Django based system, and is built using version 2, python3.5

Installation is standard for python projects, using venv and pip.

Check out the code from GitHub, copy to a convienent installation directory, and run::

    pip install -r requirements.txt

Run the migrations using::

    python manage.py migrate

Test the webserver runs by using::

    python manage.py runserver

And the output similar to::

    Performing system checks...

    System check identified no issues (0 silenced).

    December 05, 2018 - 15:14:56
    Django version 2.0.4, using settings 'MetroSurvey.settings'
    Starting development server at http://127.0.0.1:8000/
    Quit the server with CONTROL-C.

Shows the server is running on the default port of ``8000``

Add the data
------------

Django admin is used to manage each survey, so first we need an administrator user to log in with::

    python manage.py createsuperuser

and complete the inputs requested.

Via a web browser, navigate to the admin page at ``/admin``. Log in using the credentials just created.

At the ``SURVEY UPLOAD`` widget on this page

.. figure:: _static/IcoCivilSocietyCol.png
    :align: center


Get the info from the admin page
--------------------------------

Add the stuff to Qualtrics
--------------------------

Test it works
-------------

The Attributes & Levels input file follows a detailed specification.

Two worksheets must be present, names ``Attributes&Levels (2)`` and ``Design Matrix``

Attributes&Levels (2)
---------------------

Row 1 is blank, and is not read by the importer. This row can be used for any human readable titles

Row 2, Column A must say ``Level``. The rest of this row are the titles of each attribute, lower case, without spaces, one per column. ie "Average Fuel" may become "fuelav".

Row 3 defines the type of attribute each column is describing. This will tell the system how to use each value in the table. Valid entries are ``option``, ``option_nolabel``, ``multiplier``.

Row 4 begins the available choices for each attribute. The ``Level`` column is a number for the option, zero indexed.

If the column is of type ``option``, each row is simply the human readable text which will be presented to the user.

If the column is of type ``text``, each row is simply the human readable text which will be presented to the user.

If the column is of type ``option_nolabel``, this is a number (integer, float) which will be presented to the user.

If the column is of type ``multiplier``, this is a number (integer, float) which will be multiplied by some user entered data as the participant completes the survey.

For example, if "1.2" is entered as one level, and 0.8 as another level, and a survey question asks "What is your current monthly phone bill?" this figure will be multiplied by 1.5 and presented to the user in the resultant table. If the user inputs £10, the table will show options £8 and £12.

If the column is of type ``addition``, this is a number (integer, float) which will be added to, or subtracted from, some user entered data as the participant completes the survey.


If the column is of type ``geographic``, this is a place name, and will be used for presenting on a map in some user interfaces.

If the column is of type ``boolean``, this will be used for True/ False questions. A ``0`` in this cell will return the unicode character of a cross ``&#10060;``. Anything other than a ``0`` will return the unicode for a tick/ check mark ``&#10004;``.
