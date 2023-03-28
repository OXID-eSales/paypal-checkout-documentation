Installation
============

To install the :productname:`PayPal Checkout` payment module, follow different procedures depending on your OXID eShop version:

* If you have OXID eShop version 6.1.x or 6.2.x, , install :productname:`PayPal Checkout` 1.2 as described in the following.
* If you have OXID eShop version 6.3.x or higher, install `PayPal Checkout 2.2 <https://docs.oxid-esales.com/modules/paypal-checkout/en/2.2/>`_.

Versions of OXID eShop prior to version 6.1 are not supported.


Installing PayPal Checkout for OXID eShop version 6.1.x or 6.2.x
----------------------------------------------------------------

Install :productname:`PayPal Checkout` v. 1.2.

|prerequisites|

* You have installed OXID eShop 6.1.x or 6.2.x.
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
      composer require oxid-solution-catalysts/paypal-module ^1.2.0


   When the installation process is finished, the :guilabel:`PayPal Checkout for OXID` module appears in the administration area under :menuselection:`Extensions --> Modules`.

#. Activate the module.

Next step: To configure :productname:`PayPal Checkout`, choose :guilabel:`Next`.

Installing a Minor Update
-------------------------

If you use a deprecated version, perform a minor update, for example from :productname:`PayPal Checkout` version 1.1.4 to version 1.2.3.

|procedure|

Execute the following command:

.. code:: bash

   composer require oxid-solution-catalysts/paypal-module ^1.2.0



Installing a patch update
-------------------------

If required, install a patch update, from :productname:`PayPal Checkout` version 1.2.2 to version 1.2.3, for example.


|procedure|

1. Execute the following command:

   .. code:: bash

      composer update

#. Confirm the prompt whether to overwrite the :file:`oxid-solution-catalysts/paypal-module` files.


.. Internal: oxdajq, status:

