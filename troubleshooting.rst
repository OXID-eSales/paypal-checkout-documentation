Troubleshooting
===============

"Credit card" and "Purchase upon invoice" not available
-------------------------------------------------------

It is possible that the payment methods "Credit card" and "Purchase on account" are not available.

This is the case if, in order to generate a webhook at PayPal, you have entered the API credentials (for example, from an existing version of PayPal Checkout) :emphasis:`manually` instead of starting the process with the :guilabel:`Sign Up Merchant Integration` button.

|procedure|

To ensure that all payment types are available, do the following (using a Sandbox account as an example):

1. Choose :menuselection:`PayPal --> Configuration`.
#. Under :guilabel:`API credentials`, delete all credentials and select :guilabel:`Save`.
   |br|
   The :guilabel:`Sign Up Merchant Integration (Sandbox)` button appears.
#. Choose the :guilabel:`Sign Up Merchant Integration (sandbox)`.
#. Go through the registration process using the email address of your Sandbox merchant account.

For more information, see :ref:`configuration:configuration` in chapter :ref:`configuration:API credentials`.

Switching on the debug mode
---------------------------

If, for example, you experience connection problems, or payment transactions with :productname:`PayPal Checkout` do not work as expected, contact PayPal support.

It is helpful if you already have log files when you contact PayPal support. To do this, activate the debug mode.

This will record the webhook calls sent to the OXID eShop by PayPal in the :file:`oxideshop.log` log file.

|procedure|

1. Open the file :file:`source/source/config.inc.php`.
#. Change the value of the :technicalname:`sLogLevel` parameter to :technicalname:`debug`.

   .. code::

      $this->sLogLevel = 'debug';

#. Provide the :file:`/source/log/oxideshop.log` to the PayPal support.
#. Once the problem is solved, change the value of the :technicalname:`sLogLevel` parameter back to the default :technicalname:`error` value.