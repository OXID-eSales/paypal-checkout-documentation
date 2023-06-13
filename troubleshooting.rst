Troubleshooting
===============

"Credit card" and "Purchase upon invoice" not available
-------------------------------------------------------

It is possible that the payment methods "Credit card" and "Purchase on account" are not available.

This is the case if, in order to generate a webhook at PayPal, you have entered the API credentials (for example, from an existing version of PayPal Checkout) :emphasis:`manually` instead of starting the process with the :guilabel:`Sign Up Merchant Integration` button.

**Remedy**

To ensure that all payment types are available, do the following (using a Sandbox account as an example):

1. Choose :menuselection:`PayPal --> Configuration`.
#. Under :guilabel:`API credentials`, delete all credentials and select :guilabel:`Save`.
   |br|
   The :guilabel:`Sign Up Merchant Integration (Sandbox)` button appears.
#. Choose the :guilabel:`Sign Up Merchant Integration (sandbox)`.
#. Go through the registration process using the email address of your Sandbox merchant account.

For more information, see :ref:`configuration:configuration` in chapter :ref:`configuration:API credentials`.

.. todo: Inhalt aus Hinweis in Konfig erg.:
        Wenn die Webhooks des Moduls geprüft werden müssen, dann bietet es sich an, den Parameter $this->sLogLevel in der Datei config.inc.php auf den Wert debug zu setzen.
        Auf diese Weise werden die an den Shop gesendeten Webhook Calls von PayPal im Log oxideshop.log aufgezeichnet.