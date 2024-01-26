Installation
============

To install the :productname:`PayPal Checkout` payment module, install different versions depending on your OXID eShop version:

* If you have OXID eShop version 6.3.x to 6.5.x, install :productname:`PayPal Checkout` 2.3.x (see :ref:`installation:Installing PayPal Checkout`).
* If you have OXID eShop version 7.x, install :productname:`PayPal Checkout` 3.3.x.
  |br|
  For more Informationen, see the corresponding module documentation under `Installing PayPal Checkout 3.3.x <https://docs.oxid-esales.com/modules/paypal-checkout/en/3.3/installation.html>`_.

* If you have OXID eShop version 6.1.x or 6.2.x, install :productname:`PayPal Checkout` 1.3.x.
  |br|
  For more Informationen, see the corresponding module documentation under `Installing PayPal Checkout 1.3.x <https://docs.oxid-esales.com/modules/paypal-checkout/en/1.3/installation.html>`_.


Earlier versions of OXID eShop are not supported.

Installing PayPal Checkout
--------------------------

For OXID eShop version 6.3 and higher, install the payment module :productname:`PayPal Checkout` version 2.3.x.

|prerequisites|

* You have installed OXID eShop version 6.3.x to 6.5.x.
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

      composer require oxid-solution-catalysts/paypal-module ^2.3.0

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

Installing a Minor Update
-------------------------

If you use a deprecated version, perform a minor update, for example from :productname:`PayPal Checkout` version 2.2.1 to version 2.3.0.

   .. code:: bash

      composer require oxid-solution-catalysts/paypal-module ^2.3.0
      composer update

Installing a patch update
-------------------------

If required, install a patch update, from :productname:`PayPal Checkout` version 2.3.0 to version 2.3.1, for example.


|procedure|

1. Execute the following command:

   .. code:: bash

      composer update

#. Confirm the prompt whether to overwrite the :file:`oxid-solution-catalysts/paypal-module` files.


.. attention::

   **Check country mappings after update to PayPal Checkout version 2.1.5**.

   With version 2.1.4 the country coverage of individual :productname:`PayPal Checkout` payment methods has been extended.

   Make sure that you can use the extended country coverage.

   Background: With :productname:`PayPal Checkout` version 2.1.5, countries are automatically assigned to payment methods during initial installation (see :ref:`configuration:Optional: Configuring the country mapping of PayPal Checkout payment methods`).

   This may cause configuration settings of your existing version to block the use of extended country mappings.

   Do the following:

   1. Choose :menuselection:`Shop Settings --> Payment Methods --> <payment method> --> Country --> Assign Countries`.
   #. To use the entire country coverage of a payment type, delete existing mappings.


.. Internal: oxdajq, status:

