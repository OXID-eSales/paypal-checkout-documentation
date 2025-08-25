PayPal Checkout V. 2.4
======================

Release date: 04-04-2024

New or changed functions
------------------------

We have

* added the PayPal Vaulting function
* removed two payment methods

PayPal Vaulting
^^^^^^^^^^^^^^^

With PayPal Vaulting, enable a seamless checkout process for returning customers and increase your conversion rate.

**Background**

PayPal Vaulting means: Your customers store their payment information securely in the Braintree vault to reuse it for future transactions.

PayPal Vaulting automatically creates a PayPal billing agreement. This allows you to charge the account in the future without your customers having to re-authenticate with PayPal or select a payment method from their wallet.

Main benefits and uses:

* Storage for future purchases: customers do not have to re-enter their payment information with each purchase, speeding up the checkout process and increasing ease of use.
* Versatility: Supports the selection or addition of shipping addresses and payment methods in the PayPal account, as well as two-factor authentication in multiple countries.
* Improved customer experience on return: Customers who have saved their PayPal Wallet in the vault can pay faster for future purchases and, if desired, change their payment method.

For more information on PayPal Vaulting, under :ref:`configuration:Configuration` see the section on :ref:`configuration:Using PayPal Vaulting`.

Activating PayPal Vaulting retrospectively
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

If you already use :productname:`PayPal Checkout`, activate PayPal Vaulting afterwards:

|procedure|

1. Update to :productname:`PayPal Checkout` 2.4.0.

   For more information, see :ref:`installation:Installing a minor update`.

#. Go through the registration process (onboarding) again.

   After a successful technical check, the availability of PayPal Vaulting is confirmed in the :guilabel:`Activation for special payment methods has taken place` area (:ref:`oxdajr05`, item 4).

   For more information on going through the registration process (onboarding), see :ref:`configuration:API credentials: Onboarding`.

|result|

PayPal Vaulting is activated by default (:ref:`oxdajr14`, Pos. 1).

Deactivate it if required. For more information, see :ref:`configuration:Using PayPal Vaulting`.

Changed payment methods
^^^^^^^^^^^^^^^^^^^^^^^

With :productname:`PayPal Checkout` 2.4, the following payment methods are :emphasis:`not` supported anymore:

* Sofort
* MyBank

For more information about supported payment methods, see :ref:`introduction:Payment methods in PayPal Checkout`.

Installation
------------

To use :productname:`PayPal Checkout` V. 2.4, install it in your :productname:`OXID eShop` 6.3.x to 6.5.x

For more information, see :ref:`installation:Installation`.


Update
------

To use the functions and corrections of :productname:`PayPal Checkout` V. 2.4, update.

For more information, see

* :ref:`installation:Installing a minor update`

.. todo: reaktivierenmit 241
    * :ref:`installation:Install patch update`
