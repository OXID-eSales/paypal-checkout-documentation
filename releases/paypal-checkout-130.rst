PayPal Checkout V. 1.3
======================

Release date: 24-05-2023

New or changed functions
------------------------

* Offer your customers the new SEPA Direct Debit payment method for bank transfers in Germany.

  For the checkout step Shipping & Payment Method, you can use it to configure the corresponding SEPA Direct Debit button (:ref:`oxdajr02`, item 3).

* If you were previously unable to offer your customers payment by credit card, use PayPal's fallback solution.

  For more information, see :ref:`Checking the activation for special payment types <activation-creditcard>`.

* Prove that you have shipped ordered goods by sending a tracking code.

  The tracking code makes it easier for PayPal to settle your claim in case of disputes with customers.

  For more information, see :ref:`operation:Marking an item as shipped`.

* Don't worry about the configuration of your payment methods during a minor update, for example, from PayPal Checkout V. 2.2 to V. 2.3: Your configuration will be preserved, you will not need to reconfigure payment types after an update.

* Delete orders that have not been completed, either automatically or manually.

  For more information, see :ref:`configuration:Configuring the handling of incomplete orders`.

Corrections
-----------

For fixes, see the changelog (GitHub) at https://github.com/OXID-eSales/paypal-module/blob/v1.3.0/CHANGELOG.md.


Update
------

To use the features and fixes of :productname:`PayPal Checkout` V. 1.3, make an update.

For more information, see

* :ref:`installation:Installing a minor update`
* :ref:`installation:Installing a patch update`
