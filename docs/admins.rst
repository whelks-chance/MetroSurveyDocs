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

