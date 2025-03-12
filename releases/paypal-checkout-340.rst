PayPal Checkout V. 3.4
======================

Release date: `2025-02-06 <https://github.com/OXID-eSales/paypal-module/blob/v3.4.0/CHANGELOG.md>`_

Overview of new or changed functions
------------------------------------

We have

* added the Google Pay and Apple Pay payment methods: :ref:`releases/paypal-checkout-340:Google Pay and Apple Pay`
* added the PayPal Vaulting function: :ref:`releases/paypal-checkout-340:PayPal Vaulting`
* removed two payment methods: :ref:`releases/paypal-checkout-340:Changed payment methods`
* added the Configuring of pseudo shipping costs for PayPal Express: :ref:`releases/paypal-checkout-340:Configuring pseudo shipping costs for PayPal Express`

Google Pay and Apple Pay
------------------------

With Apple Pay and Google Pay, enable payment transactions worldwide and in 25 currencies.

For more information on coverage, see

* :ref:`introduction:Market coverage by payment method`
* :ref:`introduction:Currency coverage by payment method`

|procedure|

1. Install or update :productname:`PayPal Checkout`.
#. Go through the registration process (onboarding) again (also for an update).

   For more information, see :ref:`configuration:API credentials: Onboarding`.

#. Verify that the Apple Pay and Google Pay payment methods have been activated (:ref:`oxdajr05rn`, item 5).

   .. _oxdajr05rn:

   .. figure:: /media/screenshots/oxdajr05.png
      :alt: Client ID/password and webhook ID generated
      :width: 650
      :class: with-shadow

      Fig.: Client ID/password and webhook ID generated

   If no activation has taken place, contact PayPal support.

#. Activate Apple Pay with your Sandbox account.

   For more information, see :ref:`configuration:Activating the Apple Pay payment method`.

   Google Pay is activated by default. You only need a Google account and a credit card.

#. Configure the Apple Pay and Google Pay country assignment.

   For more information, see :ref:`configuration:Optional: Configuring the country mapping of PayPal Checkout payment methods`.

#. To configure the Apple Pay and Google Pay payment methods, choose

   * :menuselection:`Shop Settings --> Payment Methods --> Apple Pay`
   * :menuselection:`Shop Settings --> Payment Methods --> Google Pay`

#. Activate Apple Pay and Google Pay for live operation after testing.

   For more information, see

   * Apple Pay: `Go live <https://developer.paypal.com/docs/checkout/apm/apple-pay/#link-golive>`_
   * :ref:`configuration:Unlocking PayPal Checkout`


PayPal Vaulting
---------------

With PayPal Vaulting, enable a seamless checkout process for returning customers and increase your conversion rate.

Background
^^^^^^^^^^

PayPal Vaulting means: Your customers store their payment information securely in the Braintree vault to reuse it for future transactions.

PayPal Vaulting automatically creates a PayPal billing agreement. This allows you to charge the account in the future without your customers having to re-authenticate with PayPal or select a payment method from their wallet.

Main benefits and uses:

* Storage for future purchases: customers do not have to re-enter their payment information with each purchase, speeding up the checkout process and increasing ease of use.
* Versatility: Supports the selection or addition of shipping addresses and payment methods in the PayPal account, as well as two-factor authentication in multiple countries.
* Improved customer experience on return: Customers who have saved their PayPal Wallet in the vault can pay faster for future purchases and, if desired, change their payment method.

For more information on PayPal Vaulting, under :ref:`configuration:Configuration` see the section on :ref:`configuration:Deactivating PayPal Vaulting`.

Activating PayPal Vaulting retrospectively
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

If you already use :productname:`PayPal Checkout`, activate PayPal Vaulting afterwards:

|procedure|

1. Update to :productname:`PayPal Checkout` 3.4.0.

   For more information, see :ref:`installation:Installing a minor update`.

#. Go through the registration process (onboarding) again.

   After a successful technical check, the availability of PayPal Vaulting is confirmed in the :guilabel:`Activation for special payment methods has taken place` area (:ref:`oxdajr05`, item 4).

   For more information on going through the registration process (onboarding), see :ref:`configuration:API credentials: Onboarding`.

|result|

PayPal Vaulting is activated by default (:ref:`oxdajr14`, Pos. 1).

Deactivate it if required. For more information, see :ref:`configuration:Deactivating PayPal Vaulting`.

Changed payment methods
-----------------------

With :productname:`PayPal Checkout` 3.4, the following payment methods are :emphasis:`not` supported anymore:

* Sofort
* MyBank

For more information about supported payment methods, see :ref:`introduction:Payment methods in PayPal Checkout`.

Configuring pseudo shipping costs for PayPal Express
----------------------------------------------------

To enable payments with PayPal Express, use so-called pseudo shipping costs to ensure that the value of the shopping cart corresponds approximately to the value that is collected from the customer's PayPal account at checkout.

For more information, see :ref:`configuration:Adjusting pseudo shipping costs for PayPal Express`.


Installation
------------

To use :productname:`PayPal Checkout` V. 3.4, install it in your :productname:`OXID eShop` 7.x.

For more information, see :ref:`installation:Installation`.


Update
------

To use the functions and corrections of :productname:`PayPal Checkout` V. 3.4, update.

For more information, see :ref:`installation:Installing a minor update`.

.. todo: reaktivierenmit 241
    * :ref:`installation:Install patch update`