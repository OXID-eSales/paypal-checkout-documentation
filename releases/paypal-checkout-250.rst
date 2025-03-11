PayPal Checkout V. 2.5.0
========================

Release date: 16-08-2024

New or changed functions
------------------------

We have

* added the Google Pay and Apple Pay payment methods: :ref:`releases/paypal-checkout-250:Google Pay and Apple Pay`
* added the Configuring of pseudo shipping costs for PayPal Express: :ref:`releases/paypal-checkout-250:Configuring pseudo shipping costs for PayPal Express`


Google Pay and Apple Pay
^^^^^^^^^^^^^^^^^^^^^^^^

With Apple Pay and Google Pay, enable payment transactions worldwide and in 25 currencies.

For more information on coverage, see

* :ref:`introduction:Market coverage by payment method`
* :ref:`introduction:Currency coverage by payment method`

|procedure|

1. Install or update :productname:`PayPal Checkout`.
#. Go through the registration process (onboarding) (also for an update).

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

Configuring pseudo shipping costs for PayPal Express
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

To enable payments with PayPal Express, use so-called pseudo shipping costs to ensure that the value of the shopping cart corresponds approximately to the value that is collected from the customer's PayPal account at checkout.

For more information, see :ref:`configuration:Adjusting pseudo shipping costs for PayPal Express`.


Installation
------------

To use :productname:`PayPal Checkout` V. 2.5.0, install it in your :productname:`OXID eShop` 6.3.x to 6.5.x

For more information, see :ref:`installation:Installation`.


Update
------

To use the functions and corrections of :productname:`PayPal Checkout` V. 2.5.0, update.

For more information, see :ref:`installation:Installing a minor update`.

.. todo: reaktivieren in 2.5.1
   * :ref:`installation:Installing a patch update`
