Installation
============

To install the payment module :productname:`PayPal Checkout`, follow different procedures to supprt either OXID eShop version 6.1 or OXID eShop version 6.2 and higher.

Earlier versions of OXID eShop prior to version 6.1 are not supported.


Installing PayPal Checkout for OXID eShop version 6.2 and higher
----------------------------------------------------------------

Install the payment module :productname:`PayPal Checkout` for OXID eShop version 6.2 and higher.

|prerequisites|

* You have installed OXID eShop 6.2 or higher.
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

      composer config repositories.oscpaypal composer https://paypal-module.packages.oxid-esales.com/
      composer require oxid-solution-catalysts/paypal-module ^2.0.0
      composer install

#. Optional: To activate the module, run the following command.
   |br|
   Alternatively: Activate the module manually during configuration (see :ref:`configuration:Activating PayPal Checkout`).

   .. code:: bash

      ./vendor/bin/oe-console oe:module:activate osc_paypal

|result|

When the installation process is finished, the module :guilabel:`PayPal Checkout for OXID` appears in the administration area under :menuselection:`Extensions --> Modules` (:ref:`oxdajq01`).

.. _oxdajq01:

.. figure:: /media/screenshots/oxdajq01.png
   :alt: PayPal Checkout for OXID installed successfully

   Figure: PayPal Checkout for OXID installed successfully


Next step: To configure :productname:`PayPal Checkout`, choose :guilabel:`Next`.

Installing PayPal Checkout for OXID eShop version 6.1
-----------------------------------------------------

To install :productname:`PayPal Checkout` for OXID eShop version 6.1, install :productname:`PayPal Checkout` V. 1.0.

|procedure|

Follow the same procedure for installation for OXID eShop version 6.2 and higher (see :ref:`installation:Installing PayPal Checkout for OXID eShop version 6.2 and higher`).

Execute the commands as follows:

   .. code:: bash

      composer config repositories.oscpaypal composer https://paypal-module.packages.oxid-esales.com/
      composer require oxid-solution-catalysts/paypal-module ^1.0.0
      composer install

.. Internal: oxdajq, status:

