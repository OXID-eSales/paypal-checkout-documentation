Troubleshooting
===============

Payment methods or functions not available
------------------------------------------

It is possible that the payment methods Google Pay, Credit card, and Purchase on account or a certain function are not available as described.

This is the case if you have entered the API credentials (for example from an existing version of PayPal Checkout) :emphasis:`manually` to generate a webhook at PayPal instead of starting the registration process with the :guilabel:`Sign Up Merchant Integration` button and going through it again.

|procedure|

To ensure that all payment types and functions are available, do the following (using a Sandbox account as an example):

1. Choose :menuselection:`PayPal --> Configuration`.
#. Under :guilabel:`API credentials`, delete all credentials and choose :guilabel:`Save`.
   |br|
   The :guilabel:`Sign Up Merchant Integration (Sandbox)` button appears.
#. Choose the :guilabel:`Sign Up Merchant Integration (sandbox)`.
#. To regenerate access data and webhook, go through the registration process (onboarding) with the e-mail address of the sandbox merchant account.

For more information, in chapter :ref:`configuration:configuration`, see :ref:`configuration:API credentials: Onboarding`.

Google Pay does not work
------------------------

|procedure|

* Check whether Google Pay is active.

  For more information, see :ref:`paypal-sandbox:Checking Google Pay and Apple Pay activation`.

Switching on the debug mode
---------------------------

If, for example, you experience connection problems, or payment transactions with :productname:`PayPal Checkout` do not work as expected, contact PayPal support.

It is helpful if you already have log files when you contact PayPal support. To do this, activate the debug mode.

This will record the webhook calls sent to the OXID eShop by PayPal in the :file:`oxideshop.log` log file.

|procedure|

1. Open the :file:`source/source/config.inc.php` file.
#. Change the value of the :technicalname:`sLogLevel` parameter to :technicalname:`debug`.

   .. code::

      $this->sLogLevel = 'debug';

#. Provide the :file:`/source/log/oxideshop.log` to the PayPal support.
#. Once the problem is solved, change the value of the :technicalname:`sLogLevel` parameter back to the default :technicalname:`error` value.