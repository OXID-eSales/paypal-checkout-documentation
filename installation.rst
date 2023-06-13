Installation
============

To install the :productname:`PayPal Checkout` payment module, follow different procedures depending on your OXID eShop version:

* If you have OXID eShop version 6.3.x or higher, install :productname:`PayPal Checkout` 2.3.0.
* If you have OXID eShop version 6.1.x or 6.2.x, install :productname:`PayPal Checkout` 1.3.0.

Earlier versions of OXID eShop are not supported.

Run the same Composer commands to install a patch update of :productname:`PayPal Checkout`


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


Next step: To configure :productname:`PayPal Checkout`, choose :guilabel:`Next`.

Installing PayPal Checkout for OXID eShop version 6.1.x or 6.2.x
----------------------------------------------------------------

To install :productname:`PayPal Checkout` for OXID eShop version 6.1.x or 6.2.x, install :productname:`PayPal Checkout` V. 1.3.x.

|procedure|

Follow the same procedure for installation for OXID eShop version 6.3 and higher (see :ref:`installation:Installing PayPal Checkout for OXID eShop version 6.3 and higher`).

Execute the commands as follows:

   .. code:: bash

      composer config repositories.oscpaypal composer https://paypal-module.packages.oxid-esales.com/
      composer require oxid-solution-catalysts/paypal-module ^1.3.0


Installing a Minor Update
-------------------------

If you use a deprecated version, perform a minor update, for example from :productname:`PayPal Checkout` version 2.2.1 to version 2.3.0.

   .. code:: bash

      composer require oxid-solution-catalysts/paypal-module ^2.3.0

Installing a patch update
-------------------------

If required, install a patch update, from :productname:`PayPal Checkout` version 2.1.4 to version 2.1.5, for example.


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

