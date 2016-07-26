
====================
COD for django-oscar
====================

Cash on delivery payment module for django-oscar

Installation
------------

* Install: `pip install -e git+http://github.com/pauloprea/django-oscar-cash-on-delivery#egg=cashondelivery`
* Add ``cashondelivery`` to ``INSTALLED_APPS``
* Add `cashondelivery` urls to project urls:

.. code-block:: python
	from cashondelivery.dashboard.app import application as cashon

	url(r'^dashboard/cash-on/', include(cashon.urls)),


* Use cashondelivery checkout app

.. code-block:: python

    # patch checkout app where we override the payment details view
    from oscar.apps.checkout import app
    from cashondelivery.app import application as checkout_app

    app.application = checkout_app

