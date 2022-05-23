Installation
============

Install the payment module :productname:`PayPal Checkout` 1.0 if you have OXID eShop version 6.1.

|prerequisites|

* You have installed OXID eShop 6.1.
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

#. Confirm the queries.

|result|

When the installation process is finished, the module :guilabel:`PayPal Checkout for OXID` appears in the administration area under :menuselection:`Extensions --> Modules`.


.. todo: #tbd Add image


Next step: To configure :productname:`PayPal Checkout`, choose :guilabel:`Next`.



.. Internal: oxdajq, status:

