PayPal Checkout V. 2.4.1
========================

Release date: #tbd-2024

New or changed functions
------------------------

We have added the Google Pay payment method.

Google Pay
^^^^^^^^^^

With Google Pay, enable payment transactions worldwide and in 25 currencies.

For more information on coverage, see

* :ref:`introduction:Market coverage by payment method`
* :ref:`introduction:Currency coverage by payment method`

|procedure|

1. Install or update :productname:`PayPal Checkout`.
#. Go through the registration process (onboarding) (also for an update).

   For more information, see :ref:`configuration:API credentials: Onboarding`.

#. Verify that the Google Pay payment method has been activated (:ref:`oxdajr05rn`, item 5).

   .. _oxdajr05rn:

   .. figure:: /media/screenshots/oxdajr05.png
      :alt: Client ID/password and webhook ID generated
      :width: 650
      :class: with-shadow

      Fig.: Client ID/password and webhook ID generated

   If no activation has taken place, contact PayPal support.

#. Configure the Google Pay country assignment.

   For more information, see :ref:`configuration:Optional: Configuring the country mapping of PayPal Checkout payment methods`.

#. To configure the Google Pay payment method, choose :menuselection:`Shop Settings --> Payment Methods --> GooglePay`.

#. Activate Google Pay for live operation after testing.

   For more information, see :ref:`configuration:Unlocking PayPal Checkout`.


Installation
------------

To use :productname:`PayPal Checkout` V. 2.4.1, install it in your :productname:`OXID eShop` 6.3.x to 6.5.x

For more information, see :ref:`installation:Installation`.


Update
------

To use the functions and corrections of :productname:`PayPal Checkout` V. 2.4.1, update.

For more information, see

* :ref:`installation:Installing a minor update`
* :ref:`installation:Installing a patch update`
