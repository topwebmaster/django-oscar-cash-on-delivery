
====================
COD for django-oscar
====================

Cash on delivery payment module for django-oscar

Installation
------------

* pip install -e git+http://github.com/pauloprea/django-oscar-cash-on-delivery#egg=cashondelivery
* add ``cashondelivery`` to ``INSTALLED_APPS``
* use cashondelivery checkout app

.. code-block:: python

    # patch checkout app where we override the payment details view
    from oscar.apps.checkout import app
    from cashondelivery.app import application as checkout_app

    app.application = checkout_app

