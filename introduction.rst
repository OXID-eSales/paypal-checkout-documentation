For what?/Where not?
====================

Use :productname:`PayPal Checkout`,

* if you do not yet offer PayPal as a payment method in your OXID eShop
* if you already use PayPal but want to offer a wide range of popular payment methods, including purchase on invoice, especially to international customers

:productname:`PayPal Checkout` checks and confirms your payment request in real time. As a store owner you are therefore protected against payment failures.


Payment methods in PayPal Checkout
----------------------------------

.. image:: media/paypal-logo.png
    :alt: PayPal-Logo
    :class: no-shadow
    :height: 38
    :width: 150

Restriction for B2B stores
^^^^^^^^^^^^^^^^^^^^^^^^^^^

If you have set prices to be net prices (typically in B2B stores), the Pay upon Invoice payment method is not available.

In the typical case, you specify all prices as gross prices in your OXID eShop, and you can offer the Pay upon Invoice payment method to your private customers.

Market coverage by country
^^^^^^^^^^^^^^^^^^^^^^^^^^

With :productname:`PayPal Checkout`, offer payment methods popular in the following markets.

In each case, note the currency coverage of each payment method (see :ref:`introduction:currency coverage by payment method`).

================= ==========================
Market            Payment Methods
================= ==========================
Worldwide         Creditcard
Worldwide         PayPal
Worldwide         PayPal Express
Austria           eps
Austria           PayPal - Pay Later
Austria           Sofort (Klarna Pay now)
Belgium           Bancontact
Belgium           Sofort (Klarna Pay now)
France            PayPal - Pay Later
Germany           GiroPay
Germany           PayPal - Pay Later
Germany           Pay upon Invoice
Germany           Sofort (Klarna Pay now)
Great Britain     Sofort (Klarna Pay now)
Great Britain     PayPal - Pay Later
Italy             MyBank
Italy             Sofort (Klarna Pay now)
Italy             PayPal - Pay Later
Netherlands       iDEAL
Netherlands       Sofort (Klarna Pay now)
Poland            BLIK
Poland            Przelewy24
Spain             Sofort (Klarna Pay now)
Spain             PayPal - Pay Later
United States     PayPal - Pay Later
================= ==========================


Market coverage by payment methods
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

In each case, note the currency coverage of each payment method (see :ref:`introduction:currency coverage by payment method`).

=============================== ===============
Payment methods                 Markets
=============================== ===============
Bancontact                      Belgium
BLIK                            Poland
Creditcard                      Worldwide
eps                             Austria
GiroPay                         Germany
iDEAL                           Netherlands
MyBank                          Italy
PayPal                          Worldwide
PayPal Express                  Worldwide
PayPal - Pay Later               Austria
PayPal - Pay Later               France
PayPal - Pay Later               Germany
PayPal - Pay Later               Great Britain
PayPal - Pay Later               Italy
PayPal - Pay Later               Spain
PayPal - Pay Later               United States
Przelewy24                      Poland
Pay upon Invoice                Germany
Sofort (Klarna Pay now)         Belgium
Sofort (Klarna Pay now)         Germany
Sofort (Klarna Pay now)         Great Britain
Sofort (Klarna Pay now)         Italy
Sofort (Klarna Pay now)         Netherlands
Sofort (Klarna Pay now)         Austria
Sofort (Klarna Pay now)         Spain
=============================== ===============

Currency coverage by payment method
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

=============================== ===============
Payment methods                 Currencies
=============================== ===============
PayPal                          AUD, BRL, CAD, CNY, CZK, DKK, EUR, HKD, HUF, ILS, JPY, MYR, MXN, TWD, NZD, NOK, PHP, PLN, GBP, RUB, SGD, SEK, CHF, THB, USD
PayPal Express                  AUD, BRL, CAD, CNY, CZK, DKK, EUR, HKD, HUF, ILS, JPY, MYR, MXN, TWD, NZD, NOK, PHP, PLN, GBP, RUB, SGD, SEK, CHF, THB, USD
PayPal - Später bezahlen        AUD, EUR, GBP, USD
Rechnungskauf                   EUR
Kreditkarte                     AUD, CAD, CHF, CZK, DKK, EUR, GBP, HKD, HUF, JPY, NOK, NZD, PLN, SEK, SGD, USD
Bancontact                      EUR
BLIK                            PLN
EPS                             EUR
GiroPay                         EUR
Ideal                           EUR
MyBank                          EUR
Przelewy24                      EUR, PLN
Sofort (Klarna Pay now)         EUR, GBP
=============================== ===============

You have the PayPal module?
---------------------------

Switch to :productname:`PayPal Checkout` to offer your customers additional payment methods including purchase on account,
which are popular in international markets.

For more information, see `developer.paypal.com/docs/checkout/apm/ <https://developer.paypal.com/docs/checkout/apm/>`_.


You have the PayPal Plus module?
--------------------------------

The API of PayPal Plus is outdated. PayPal does not develop the API and does not offer new contracts for it.

Switch to :productname:`PayPal Checkout` if it is important for you to offer your customers the Quick Purchase feature or the Pay Later feature of :productname:`PayPal Checkout`:

* With the Quick Purchase feature, your customers can skip the registration process in your eShop and start ordering and paying directly on the product detail page, for example (see :ref:`configuration:Button placement settings: Quick purchase`).
* With the Pay Later function, customers in Germany can pay with a 30-day deferral or by PayPal installment, for example (see :ref:`configuration:Button Placement Settings: Pay Later`).
  |br|
  For more information about country coverage and country-specific features of the Pay Later feature, see `developer.paypal.com/docs/checkout/pay-later/de/ <https://developer.paypal.com/docs/checkout/pay-later/de/>`_.

.. Intern: oxdajp, Status: