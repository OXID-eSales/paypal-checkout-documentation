Installation
============

To install the :productname:`PayPal Checkout` payment module, install different versions depending on your OXID eShop version:

* If you have OXID eShop version 7.x, install :productname:`PayPal Checkout` 3.3.x (see :ref:`installation:Installing PayPal Checkout`).
* If you have OXID eShop version 6.3.x to 6.5.x, install :productname:`PayPal Checkout` 2.x.x.
  |br|
  For more information, see the corresponding module documentation under `Installing PayPal Checkout 2.3.x <https://docs.oxid-esales.com/modules/paypal-checkout/en/2.3/installation.html>`_.
* If you have OXID eShop version 6.1.x or 6.2.x, install :productname:`PayPal Checkout` 1.x.x.
  |br|
  For more Informationen, see the corresponding module documentation under `Installing PayPal Checkout 1.3.x <https://docs.oxid-esales.com/modules/paypal-checkout/en/1.3/installation.html>`_.

Earlier versions of OXID eShop are not supported.

Installing PayPal Checkout
--------------------------

For OXID eShop version 7.x, install the payment module :productname:`PayPal Checkout` version 3.3.x.

|prerequisites|

* You have installed OXID eShop version 7.x.
* You have configured `https`.

   a. In the :file:`<root directory of the eShop>/source` directory, open the :file:`config.inc.php` file.
   b. Make sure that `https` is set for the base URL (:technicalname:`shopURL` parameter).
      |br|
      Example:

      .. code::

         $this->sShopURL = 'https://www.example.org';

|procedure|

1. Open a shell and change to the root directory of the eShop (where the file :file:`composer.json` is located).
   |br|
   Example:

   .. code:: bash

      cd /var/www/oxideshop

#. Execute the following commands:

   .. code:: bash

      composer require oxid-solution-catalysts/paypal-module ^3.3.0

#. Optional: To activate the module, run the following command.
   |br|
   Alternatively: Activate the module manually during configuration (see :ref:`configuration:Activating PayPal Checkout manually`).

   .. code:: bash

      ./vendor/bin/oe-console oe:module:activate osc_paypal

|result|

When the installation process is finished, the module :guilabel:`PayPal Checkout for OXID` appears in the administration area under :menuselection:`Extensions --> Modules` (:ref:`oxdajq01`).

.. _oxdajq01:

.. figure:: /media/screenshots/oxdajq01.png
   :alt: PayPal Checkout for OXID installed and activated
   :width: 650
   :class: with-shadow

   Fig.: PayPal Checkout for OXID installed successfully

.. Internal: oxdajq, status:

