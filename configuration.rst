Configuration
=============


Make the :productname:`PayPal Checkout` module operational for your OXID eShop.

Administering PayPal or PayPal Plus orders
------------------------------------------

If you already use :productname:`PayPal` or :productname:`PayPal Plus` module, please note the following limitation:

To manage existing orders, both modules, :productname:`PayPal Checkout` and :productname:`PayPal` for example, must be active at the same time.

However, to prevent that, in our example, the PayPal payment method redundantly displayed in the frontend, you must deactivate the :emphasis:`payment method` :guilabel:`PayPal`.

We recommend the following procedure.

|procedure|

.. tip::

   **Scheduling a downtime**

   Schedule a short downtime for the step of deactivating the payment method belonging to :productname:`PayPal` or :productname:`PayPal Plus`.

.. todo: #tbd: check navig paths

1. Install :productname:`PayPal Checkout`.
#. Activate and configure :productname:`PayPal Checkout` as described below under :ref:`configuration:Basic procedure`.
   |br|
   Result: To manage your orders, under :menuselection:`Administer Orders --> Orders`, you will find separate tabs for the :productname:`PayPal Checkout` and :productname:`PayPal` or :productname:`PayPal Plus` modules.
   |br|
   However, on the :guilabel:`PayPal Checkout` tab, you can only :emphasis:`display` the orders of your respective module already in use, :productname:`PayPal`, for example.
   |br|
   :emphasis:`Actions` for order management, for example refunds, are only possible on the tab corresponding to the payment module you have used, :productname:`PayPal`, for example.
#. Enable :productname:`PayPal Checkout` for live operation as described under :ref:`configuration:Activating PayPal Checkout`.
#. Select :menuselection:`Shop Settings --> Payment Methods`.
#. Identify the payment methods corresponding to :productname:`PayPal` or :productname:`PayPal Plus`:

   * :guilabel:`PayPal` (ID: :technicalname:`oxidpaypal`)
   * :guilabel:`PayPal Plus` (ID: :technicalname:`payppaypalplus`)

   .. hint::

      The ID is displayed in the lower left corner of the window when you hover over the payment type name.

#. Disable the payment type corresponding to :productname:`PayPal` or :productname:`PayPal Plus`.
   |br|
   To do this, on the :guilabel:`Main` tab, uncheck the :guilabel:`Active` checkbox.
   |br|
   Result: The :productname:`PayPal` or :productname:`PayPal Plus` module is still active, but the associated payment methods are no longer offered to your customers. Only the payment methods of :productname:`PayPal Checkout` are offered.
   |br|
   You can still edit existing orders as usual under :menuselection:`Administer Orders --> Orders` on the tab corresponding to the payment module.
#. Recommended: As soon as you are sure that existing orders will no longer require any actions (refunds, for example), under :menuselection:`Extensions --> Modules` disable :productname:`PayPal` or :productname:`PayPal Plus`.

   .. hint::

      **Administering orders in the PayPal merchant account**

      Nothing can go wrong if you deactivate :productname:`PayPal` or :productname:`PayPal Plus`.

      You can always manage existing orders in your PayPal merchant account.


Basic procedure
---------------

1. Activate the module.
   |br|
   The most important payment methods are automatically activated.
#. Connect to your PayPal merchant account.
   |br|
   For testing purposes, create only a test account (PayPal Sandbox) at first.
#. Optional: Disable the express checkout feature of :productname:`PayPal Checkout` if needed.
#. Optional: Specify if you want to offer PayPal installment payment to your customers.
#. Configure the payment methods provided by :productname:`PayPal Checkout` as payment methods in your eShop:

   * Enable the countries you want to cover.
   * Link the payment methods to your shipping methods and shipping rules.

#. Run test payments in the :productname:`PayPal Checkout` sandbox.

   .. hint::

      Note: The :guilabel:`Sandbox` mode is set by default after enabling.

#. Test :productname:`PayPal Checkout` in the PayPal sandbox and adjust the configuration until all payment processes works as you want.
#. Enable :productname:`PayPal Checkout`:

   a. If you do not have a merchant account yet, create one for live operation.
   b. Switch to :guilabel:`Live` operation mode.


Activating PayPal Checkout
--------------------------

Enable :productname:`PayPal Checkout` in each subshop where you want to use the module.

|Procedure|

1. Choose :menuselection:`Extensions --> Modules`.
#. Choose the :guilabel:`PayPal Checkout for OXID` module and choose :menuselection:`Overview --> Activate`.


|result|

Under :menuselection:`Shop Settings --> Payment Methods`, the payment methods :guilabel:`PayPal v2` as well as important additional payment methods, are marked as active.

To actually use a certain country-specific payment method, you must have marked the respective country as active under :menuselection:`Master Settings --> Countries`.

|example|

To be able to offer iDEAL, you must have made sure that you have set the Netherlands as active under :menuselection:`Master Settings --> Countries`.

.. todo: #ML: Zahlungsartname PayPal v2 klären

.. todo: #Bild ergänzen;
   .. image:: media/screenshots/oxdaac01.png
       :alt: PayPal, Moduleinstellungen
       :class: with-shadow
       :height: 344
       :width: 650


Configuring PayPal Checkout
---------------------------

To start the configuration, choose :menuselection:`PayPal --> Configuration`.


API Credentials
^^^^^^^^^^^^^^^

Register a webhook to connect your eShop with PayPal.

The webhook allows PayPal to contact your OXID eShop and provide real-time status messages about, for example, completed transactions.

In the first run, you test the payment methods provided with :productname:`PayPal Checkout` with test credentials in a *sandbox*.

Only when everything works as you want, use the credentials for *live* operation.


|procedure|


1. To log in to the sandbox, choose :guilabel:`API credentials` and click :guilabel:`Start Merchant Integration (Sandbox)`.
2. Go through the registration process.

.. hint::

   **Payment method credit card**.

   If the activation for the payment method credit card has not been done automatically, the payment method appears as a separate :guilabel:`creditcard` button under the Paypal button.

   .. image:: media/screenshots/oxdajr02.png
       :alt: Payment method credit card
       :class: no-shadow


.. hint::

   **Payment method Pay upon Invoice**

   PayPal offers the payment method Pay upon Invoice only to shop owners from Germany.


|result|

Once you have given PayPal permission to connect your Sandbox account to the PayPal Test Store, the API credentials are displayed, and the module is active.

Under :menuselection:`Shop Settings --> Payment Methods` the payment method :guilabel:`PayPal v2` is active.

.. todo: Add picture;

.. hint::

   **Generate new webhook**.

   Sometimes it may be necessary to delete the existing webhook and generate a new one.

   To delete a webhook, delete the credentials and select :guilabel:`Save`.

   The :guilabel:`Start Merchant Integration` button appears, and you can regenerate the webhook.




Button placement settings
^^^^^^^^^^^^^^^^^^^^^^^^^

Decide if you want to offer the quick purchase feature of :productname:`PayPal Checkout`.

With the quick purchase feature, the customer skips logging into your eShop.

|example|

* Your customers typically have only one item in their shopping cart when they place an order?
  |br|
  In this case, it makes sense to guide customers to their destination as quickly and barrier-free as possible and activate the quick purchase function.
* Do you generate a significant portion of sales or margin from accessory items?
  |br|
  In this case, it may make sense to delay payment and offer the PayPal buttons only in the shopping cart and checkout, for example.

So, you determine,

* whether customers have to go through your checkout process and register in your eShop

  or

* whether customers can directly trigger the order without registering with their PayPal account (quick purchase).

:emphasis:`By default`, the Quick Purchase feature is :emphasis:`active`, and the PayPal button appears on the following pages:

* on the product detail page
* in the shopping cart
* on the checkout page

So, your customers can use their PayPal account to trigger the order at any time.

If you want your customers to have to register in your eShop, disable the quick purchase feature.

|procedure|

1. To disable the express checkout feature, uncheck :guilabel:`Product details page` and :guilabel:`Basket`.
2. Save your settings.

|Result|

The PayPal button appears only on the checkout page.



Login with PayPal
^^^^^^^^^^^^^^^^^

Set customers to be automatically logged into your OXID eShop

* if the email address of the PayPal account and the eShop account are identical

and

* as soon as your customer is logged in to their PayPal account.

Benefit: You make the signup process more convenient for your customers.

Your customers will skip the login mechanism. Your customers log in to your OXID eShop :emphasis:`without having to enter their password`.


Disadvantages:

* Often spouses, for example, use the same PayPal account.
  |br|
  One of the partners could thereby view the partner's order history or other customer data in the OXID eShop.
  |br|
  So potentially there is a privacy risk.
* If your customers do not have to log in to your eShop, you will lose customer order history data.
  |br|
  You could otherwise use such data for statistical analysis to target your customers.


If you do :emphasis:`not` enable :guilabel:`Login with PayPal`, the following happens:

* If the customer's PayPal email address is :emphasis:`known`, the PayPal payment process will be interrupted, and the customer will have to log in to your eShop.
  |br|
  The PayPal session is created, and your customer is logged into your eShop.
  |br|
  The customer's identity is clearly established, and the current order is added to the customer's order history.
* If the customer's PayPal email address is :emphasis:`not` known, your customer will complete the order using a guest account.
  |br|
  Your customer lands on the checkout page with the PayPal address data. The data is stored only once for the current order, no customer account is created in the eShop.

.. todo: #tbd: function description: add aspect order history

|procedure|

.. ATTENTION::

   The :guilabel:`Login with PayPal` function is **enabled** by default.

1. Check what can go wrong in the worst case if several users use the same PayPal account and can see each other's data in your eShop.
#. There is no serious risk if your customers conveniently log in to your eShop automatically with their PayPal accounts?
   |br|
   Then leave the :guilabel:`Automatically log in to shop during checkout` checkbox selected.
   |br|
   Otherwise, deselect the checkbox.
#. Save your settings.


Banner settings: re-use
^^^^^^^^^^^^^^^^^^^^^^^

Optional: If you already use the :productname:`PayPal` module, conveniently re-use your banner settings for :productname:`PayPal Checkout`.

Alternatively, set the banner settings manually as described below under :ref:`configuration:Banner Settings`.

|prerequisites|

:productname:`PayPal` is activated.


|procedure|

.. todo #ML: verify button name

1. To apply the existing PayPal banner advertising settings, choose the :guilabel:`Apply settings from the classic PayPal module` button.
   |br|
   The button appears only if the :productname:`PayPal` module is still activated.
#. Save your settings.


Banner settings
^^^^^^^^^^^^^^^

Optional: specify whether you want to advertise PayPal installments with banners.

If you want to take advantage of advertising PayPal installments, specify where you want the banners to appear, for example, on the home page, on the detail page of items, on category pages, in search results, and/or in the checkout process.

.. attention::

   **Privacy**

   To let the banners appear, a permanent communication with the PayPal servers is necessary.

   For this purpose, scripts are started with every page view, which observe user behavior and collect the information necessary for the PayPal payment process and transmit it to PayPal.

   This communication may be undesirable, for example for reasons of

      * data protection
      * performance

   In this case, make sure that the feature is disabled.

   By default, the feature is turned on.

.. todo: #tbd: add screenshot -- function description 0301,


|procedure|

1. To disable running scripts for PayPal banner ads, uncheck the :guilabel:`Enable installment banners` checkbox.
   |br|
   If you do not check the box, the scripts will not be executed.
#. If you :emphasis:`allow` running scripts for PayPal banner ads, specify on which pages the banner should appear.
   |br|
   To do this, choose the appropriate checkbox.
#. If you use a custom theme or a customized OXID theme, do the following:

   a. Identify the CSS selector of the page behind which you want to place the banner.
   b. Enter the CSS selector in appropriate input field.
#. Set the desired color of the banner under :guilabel:`Select installment banner's color`.
#. Save your settings.


Testing PayPal Checkout
-----------------------

Configure :productname:`PayPal Checkout` according to your needs and test the result.

|procedure|

1. Under :menuselection:`Master Settings --> Countries`, make sure that the markets you want to cover are active.
#. Under :menuselection:`Shop Settings --> Payment Methods`, do the following:

   a. Assign at least one user group to each of the desired :productname:`PayPal Checkout` payment methods (for example :guilabel:`iDEAL (via PayPal)`.
   b. On corresponding :guilabel:`Master` tab, make sure that you have set the desired minimum and maximum purchase value for the :productname:`PayPal Checkout` payment methods.
      |br|
      Example: The maximum purchase value for :guilabel:`PayPal v2` payment type is limited to €10,000 by default. The minimum purchase value is €10.
#. Under :menuselection:`Shop Settings --> Shipping Methods`, do the following:

   a. Assign the desired :productname:`PayPal Checkout` payment methods to the respective shipping methods.
   b. Make sure that at least one shipping method is created for payment with the :guilabel:`PayPal v2` payment method.
      |br|
      Typically, this is the default payment method.

.. todo: #tbd: prüfen Zahlungsart :guilabel:`PayPal` oder PP v2?
.. todo: #tbd: prüfen: Weitere Informationen finden Sie unter `Zahlungsarten <https://docs.oxid-esales.com/eshop/de/6.0/einrichtung/zahlungsarten/zahlungsarten.html>`_ der Anwenderdokumentation des OXID eShop. Ändern Sie ggf. den Einkaufswert (€) in 0 bis 99999.


Unlocking PayPal Checkout
-------------------------

Unlock :productname:`PayPal Checkout` after testing.

|prerequisites|

You have configured the desired payment methods and tested them successfully with test payments in the PayPal sandbox.

|procedure|

1. Under :guilabel:`API credentials` choose the :guilabel:`Live` operating mode.
#. Choose the :guilabel:`Start Merchant Integration (Live)` button.
   |br|
   A dialog box for logging in to PayPal appears.
#. Log in with your existing PayPal merchant account. If you don't have a live login yet, create a new PayPal merchant account.
#. Save your settings.
#. If you use :productname:`PayPal` or :productname:`PayPal Plus`, follow the recommendations under :ref:`configuration:Administering PayPal or PayPal Plus orders`.


|result|

The PayPal API credentials will be inserted.

The :productname:`PayPal Checkout` module is active and ready for orders from your customers.



.. Intern: oxdajr, Status: