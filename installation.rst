Installation
============

Install the payment module :productname:`PayPal Checkout` for OXID eShop version 6.2 and higher.


.. include:: /_static/reuse/paypal-checkout-migration.rst


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
      composer require oxid-solution-catalysts/paypal-module ^1.0.0
      composer install
      ./vendor/bin/oe-console oe:module:install-configuration source/modules/osc/paypal
      ./vendor/bin/oe-console oe:module:apply-configuration

#. Optional: To activate the module, run the following command.
   |br|
   Alternatively: activate the module manually during configuration (see :ref:`configuration:Activating PayPal Checkout`).

   .. code:: bash

      ./vendor/bin/oe-console oe:module:activate osc_paypal

#. Confirm the queries.

|result|

When the installation process is finished, the module :guilabel:`OSC :: PayPal - Online Payment Service` appears in the administration area under :menuselection:`Extensions --> Modules`.


.. todo: #tbd Add image


Next step: To configure :productname:`PayPal Checkout`, choose :guilabel:`Next`.



.. Internal: oxdajq, status:

