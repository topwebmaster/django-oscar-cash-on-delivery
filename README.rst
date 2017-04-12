
====================
COD for django-oscar
====================

Cash on delivery payment module for django-oscar

Installation
------------

* Install: `pip install -e git+https://github.com/winzard/django-oscar-cash-on-delivery#egg=cashondelivery`
* Add ``cashondelivery`` to ``INSTALLED_APPS``
* Add ``cashondelivery`` urls to project urls:

.. code-block:: python

    from cashondelivery.dashboard.app import application as cashon
    
    url(r'^dashboard/cash-on/', include(cashon.urls)),


* Fork django-oscar checkout app and use PaymentDetailsView from sandbox/checkout/views.py:

.. code-block:: python

    # your checkout/app.py
    from oscar.apps.checkout import app
    from .views import PaymentDetailsView

    class CheckoutApplication(app.CheckoutApplication):
        payment_details_view = PaymentDetailsView


    application = CheckoutApplication()


