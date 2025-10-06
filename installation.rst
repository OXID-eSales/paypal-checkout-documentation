Installation
============

To install the :productname:`PayPal Checkout` payment module, follow different procedures depending on your OXID eShop version:

* If you have OXID eShop version 6.3.x to 6.5.x, install :productname:`PayPal Checkout` 2.2.x as described in the following.
* If you have OXID eShop version 7.x, install  `PayPal Checkout 3.x <https://docs.oxid-esales.com/modules/paypal-checkout/en/3.3/>`_.
* If you have OXID eShop version 6.1.x or 6.2.x, install `PayPal Checkout 1.x <https://docs.oxid-esales.com/modules/paypal-checkout/en/1.2/>`_.

Versions of OXID eShop prior to version 6.1 are not supported.

Installing PayPal Checkout for OXID eShop version 6.3 and higher
----------------------------------------------------------------

Install the payment module :productname:`PayPal Checkout` for OXID eShop version 6.3 and higher.

|prerequisites|

* You have installed OXID eShop 6.3 or higher.
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
      composer require oxid-solution-catalysts/paypal-module ^2.2.0

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

   Figure: PayPal Checkout for OXID installed and activated


Next step: To configure :productname:`PayPal Checkout`, choose :guilabel:`Next`.

Installing a patch update
-------------------------

If required, install a patch update, from :productname:`PayPal Checkout` version 2.2.0 to version 2.2.1, for example.

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

