Configuration
=============


Make the :productname:`PayPal Checkout` module operational for your OXID eShop.

You already have PayPal or PayPal Plus?
---------------------------------------

Ensure a smooth transition to the new :productname:`PayPal Checkout` module.

To do this, note the following two restrictions:

* You cannot run :productname:`PayPal Checkout` with your :productname:`PayPal Plus` credentials.
  |br|
  Follow the instructions under :ref:`configuration:Re-running the registration for PayPal Checkout`.
* To manage existing orders, both modules, for example :productname:`PayPal Checkout` and :productname:`PayPal`, must be active at the same time.
  |br|
  Follow the instructions under :ref:`configuration:Administering existing PayPal or PayPal Plus orders`.

Re-running the registration for PayPal Checkout
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

If you have :productname:`PayPal Plus`, please note the following:

The credentials and registration process of :productname:`PayPal Checkout` are outwardly similar to :productname:`PayPal Plus`.

However, do not let this tempt you to reuse the credentials from :productname:`PayPal Plus`.

This would lead to the following disappointments:

* Webhooks are not activated correctly, information is not transmitted correctly, but without the errors being immediately apparent.
* Payment methods such as installment purchase are not available, payment by credit card is not enabled.

|procedure|

Do the following:

1. Test :productname:`PayPal Checkout` in the PayPal sandbox with :emphasis:`test` accounts as described in :ref:`configuration:Configuring PayPal Checkout`.
#. To unlock your :emphasis:`live` system, generate new credentials.
   |br|
   To do this, go through the PayPal registration process again with your PayPal merchant account details.

Administering existing PayPal or PayPal Plus orders
---------------------------------------------------

If you already use the :productname:`PayPal` or :productname:`PayPal Plus` module, please note the following limitation:

To administer existing orders, both modules, :productname:`PayPal Checkout` and :productname:`PayPal` for example, must be active at the same time.

However, to prevent that, in our example, the PayPal payment method redundantly displayed in the frontend, you must deactivate the :emphasis:`payment method` :guilabel:`PayPal`.


|procedure|

We recommend the following procedure.

.. tip::

   **Scheduling a downtime**

   Schedule a short downtime for the step of deactivating the payment method belonging to :productname:`PayPal` or :productname:`PayPal Plus`.


1. Install :productname:`PayPal Checkout`.
#. Activate and configure :productname:`PayPal Checkout` as described below under :ref:`configuration:Basic procedure`.
   |br|
   Result: To administer your orders, under :menuselection:`Administer Orders --> Orders` you find separate tabs for :productname:`PayPal Checkout` and for :productname:`PayPal` or :productname:`PayPal Plus` (depending on which of the two modules you use).

   .. note::

      **Administering orders in the PayPal merchant account**

      Nothing can go wrong if you disable :productname:`PayPal` or :productname:`PayPal Plus` as described below.

      You can administer orders in your PayPal merchant account at any time.

      **Technical dependencies**

      On the separate tab for :productname:`PayPal` or :productname:`PayPal Plus` you can :emphasis:`edit` your old orders until you deactivate your previously used module.

      Once you deactivate your previously used module, you can still :emphasis:`view` your old orders on the :guilabel:`PayPal Checkout` tab, but :emphasis:`not` edit them.

      If you clean up your system after deactivating your previously used module and therefore also delete the module's database, your old orders will also no longer be displayed on the :guilabel:`PayPal Checkout` tab.

      After deleting the database, you will still be able to view and administer the old orders in your PayPal merchant account.


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


Basic procedure
---------------

.. include:: /_static/reuse/note-ee-onboarding.rst

1. Activate the module.
   |br|
   The most important payment methods are automatically activated.
#. Connect to PayPal via a webhook.

   .. attention::

      * Do not use the credentials for :productname:`PayPal Plus` to establish the connection.
      * Test :productname:`PayPal Plus` in the PayPal sandbox first.

#. Optional: Disable the express checkout feature of :productname:`PayPal Checkout` if needed.
#. Optional: Specify if you want to offer PayPal installment payment (see :ref:`oxdajr08`) to your customers.
#. Configure the payment methods provided by :productname:`PayPal Checkout` as payment methods in your eShop:

   * Enable the countries you want to cover.
   * Link the payment methods to your shipping methods and shipping rules.

#. Run test payments in the :productname:`PayPal Checkout` sandbox. and adjust the configuration until all payment processes works as you want.
#. Enable :productname:`PayPal Checkout`:

   a. If you do not have a merchant account yet, create one for live operation.
   b. Switch to :guilabel:`Live` operation mode.


Activating PayPal Checkout
--------------------------

Ensure :productname:`PayPal Checkout` is activated in each subshop where you want to use the module.

|Procedure|

1. Choose :menuselection:`Extensions --> Modules`.
#. Choose the :guilabel:`PayPal Checkout for OXID` module and choose :menuselection:`Overview --> Activate`.


|result|

Under :menuselection:`Shop Settings --> Payment Methods`, the payment methods :guilabel:`PayPal` as well as important additional payment methods, are marked as active.

To actually use a certain country-specific payment method, you must have marked the respective country as active under :menuselection:`Master Settings --> Countries`.

|example|

To be able to offer iDEAL, you must have made sure that you have set the Netherlands as active under :menuselection:`Master Settings --> Countries`.



Configuring PayPal Checkout
---------------------------

To start the configuration, choose :menuselection:`PayPal --> Configuration`.


API Credentials
^^^^^^^^^^^^^^^

Register a webhook to connect your eShop with PayPal.

The webhook allows PayPal to contact your OXID eShop and provide real-time status messages about, for example, completed transactions.

.. hint::

  It's possible to let the shop track the incoming webhooks by setting the config parameter `$this->sLogLevel` in the file `config.inc.php` to `debug`. After that, the webhook calls by PayPal are written to the file `oxideshop.log`.


In the first run, you test the payment methods provided with :productname:`PayPal Checkout` with test credentials in a *sandbox*.

.. hint::

   **What does testing in the sandbox do for me?**

   `sandbox.paypal.com` is a mirror system.
   |br|
   All functions and the API are identical to `sandbox.paypal.com`.

   This means that any error you can create here will also exist in the live system.
   |br|
   Conversely, any error not generated will not occur in the production system either.

   Therefore, test your :productname:`PayPal Checkout` integration with a sandbox system first.

   Nothing can go wrong:

   * Test payments in the sandbox cost nothing.
   * You avoid chargebacks as they would be necessary with test payments with the live account.

Only when everything works as you want, use the credentials for *live* operation.

|prerequisites|

* On PayPal's developer page, you have created a sandbox merchant account and a sandbox customer account.
  |br|
  For more information, see :ref:`paypal-sandbox:Generating PayPal sandbox accounts`.

* Your test environment has SSL.
  |br|
  If you are testing :productname:`PayPal Checkout` in a local development environment that is only accessible via :technicalname:`http://` (i.e. :emphasis:`without SSL` via :technicalname:`https://`), then use, for example, NGROK to provide your test environment with temporary SSL.
  |br|
  For more information, see :ref:`paypal-sandbox:Setting up temporary SSL`.

|procedure|

We describe the process using a sandbox account as an example. The live process is analogous.

.. include:: /_static/reuse/note-ee-onboarding.rst

1. To log in to the sandbox, under :guilabel:`API credentials` choose the :guilabel:`Start Merchant Integration (Sandbox) in a new window` button.
#. Select :guilabel:`Sign Up Merchant Integration (Sandbox)`.
#. Go through the registration process with the sandbox merchant account email address.

   a. Log in (:ref:`oxdajr01`), and confirm the prompts.

      .. todo: #tbd: screenshot EN

      .. _oxdajr01:

      .. figure:: /media/screenshots/oxdajr01.png
         :alt: Starting the registration of the sandbox merchant account

         Figure: Starting the registration of the sandbox merchant account

   #. Finally, choose :guilabel:`Back to John Doe`s Test Store` (:ref:`oxdajr03`).

      .. _oxdajr03:

      .. figure:: /media/screenshots/oxdajr03.png
         :alt: Completing the registration of the merchant account

         Figure: Completing the registration of the merchant account

      A message indicates success (:ref:`oxdajr04`).

      .. _oxdajr04:

      .. figure:: /media/screenshots/oxdajr04.png
         :alt: Message onboarding successful

         Figure: Message onboarding successful

#. Switch back to your OXID eShop.

   The webhook is created.

   The client ID and the webhook ID are displayed (:ref:`oxdajr05`).

   .. _oxdajr05:

   .. figure:: /media/screenshots/oxdajr05.png
      :alt: Webhook created

      Figure: Webhook created


#. If you want to use the payment methods Pay upon Invoice or credit card, under :guilabel:`Activation for special payment methods has taken place` (:ref:`oxdajr05`) check whether the activation has been done.
   |br|
   If the activation did not happen automatically, contact your PayPal representative.

.. hint::

   **Credit card payment method**.

   If the credit card payment method has not been activated automatically, the payment method will appear as a separate :guilabel:`credit card` button below the PayPal button.

   .. image:: media/screenshots/oxdajr02.png
       :alt: Payment method credit card not activated
       :class: no-shadow

   Once the activation is done, your customer sees the PayPal button, and the credit card payment method is available in the Shipping & Payment Method checkout step.

   .. image:: media/screenshots/oxdajr06.png
       :alt: Payment method credit card activated
       :class: no-shadow

.. hint::

   **Payment method Pay upon Invoice**

   PayPal offers the payment method Pay upon Invoice only to show owners from Germany.


|result|

Once you have given PayPal permission to connect your sandbox account to the
PayPal test store, the API credentials are displayed and the module is active (:ref:`oxdajr05`).

Under :menuselection:`Shop Settings --> Payment Methods`, the payment method :guilabel:`PayPal` (technical name :technicalname:`oscpaypal`) is active (:ref:`oxdajr07`).

   .. _oxdajr07:

   .. figure:: /media/screenshots/oxdajr07.png
      :alt: Payment method PayPal active

      Figure: Payment method PayPal active

.. hint::

   **Generating a new webhook**.

   Sometimes it may be necessary to delete the existing webhook and generate a new one.

   To delete a webhook, delete the credentials and select :guilabel:`Save`.

   The :guilabel:`Register Merchant PayPal Integration` button appears and you can regenerate the webhook.




Button placement settings: Quick purchase
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Decide if you want to offer the quick purchase feature of :productname:`PayPal Checkout`.

With the quick purchase feature, your customers skip logging into your eShop.

|example|

* Your customers typically have only one item in their shopping cart when they place an order?
  |br|
  In this case it makes sense to guide customers to their destination as quickly and barrier-free as possible and activate the quick purchase function.
* Do you generate a significant portion of sales or margin from accessory items?
  |br|
  In this case it may make sense to delay payment and offer the PayPal buttons only in the shopping cart and checkout, for example.

So, you determine,

* whether customers have to go through your checkout process and register in your eShop

  or

* whether customers can directly trigger the order without registering with their PayPal account (quick purchase).

:emphasis:`By default`, the Quick Purchase feature is :emphasis:`active`, and the PayPal button appears on the following pages:

* on the product detail page
* in the shopping cart
* in the mini shopping cart (:ref:`oxdajr09`, Pos. 1)
* on the checkout page

So, your customers can use their PayPal account to trigger the order at any time.

If you want your customers to have to register in your eShop, disable the quick purchase feature.

.. todo: #tbd: Screenshot EN

.. _oxdajr09:

.. figure:: /media/screenshots/oxdajr09.png
   :alt: Mini shopping cart and Pay Later

   Abb.: Mini shopping cart and Pay Later

|procedure|

1. To disable the express checkout feature, uncheck :guilabel:`Product details page` and :guilabel:`Basket`.
2. Save your settings.

|Result|

The PayPal button appears only on the checkout page.

Button placement settings: Pay later
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Decide whether you want to offer the Pay Later feature (:ref:`oxdajr09`, pos. 2).

Pay Later means, for example, that PayPal offers customers in Germany the "Pay after 30 days" or PayPal installments options.

For more information about country coverage and country-specific features of the Pay Later feature, see `developer.paypal.com/docs/checkout/pay-later/en <https://developer.paypal.com/docs/checkout/pay-later/de/>`_.


|procedure|

1. To offer your customers Pay Later features, choose the :guilabel:`"Show Pay Later" button?` checkbox.
#. Save your settings.


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


Banner settings: Re-using your PayPal banner settings
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Optional: If you already use the :productname:`PayPal` module, conveniently re-use your banner settings for :productname:`PayPal Checkout`.

Alternatively, set the banner settings manually as described below under :ref:`configuration:Banner settings`.

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

Specify whether you want to advertise PayPal installments with banners (:ref:`oxdajr08`).

If you want to take advantage of advertising PayPal installments, specify where you want the banners to appear, for example, on the home page, on the detail page of items, on category pages, in search results, and/or in the checkout process.

.. todo: screenshot EN

.. _oxdajr08:

.. figure:: /media/screenshots/oxdajr08.png
   :alt: Example: Installment payment banner on a category page

   Figure: Example: installment banner on a category page

.. attention::

   **Privacy**

   To let the banners appear, a permanent communication with the PayPal servers is necessary.

   For this purpose, scripts are started with every page view, which observe user behavior and collect the information necessary for the PayPal payment process and transmit it to PayPal.

   This communication may be undesirable, for example for reasons of

      * data protection
      * performance

   In this case, make sure that the feature is disabled.

   By default, the feature is turned on.


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


Optional: Configuring the country mapping of PayPal Checkout payment methods
----------------------------------------------------------------------------

Make sure that certain :productname:`PayPal Checkout` payment methods are only available in the countries you choose.

|background|

With the initial installation, the :productname:`PayPal Checkout` payment methods are automatically assigned to the corresponding countries.

Most :productname:`PayPal Checkout` payment methods cover multiple countries. For example, the :productname:`Credit Card` payment method is available to customers worldwide, and the :productname:`Pay Later` payment method is available to your customers in countries in Europe, the USA, and Australia, for example.

For more information about the country coverage of each :productname:`PayPal Checkout` payment method, see :ref:`introduction:Market coverage by payment methods`.


The basic rule here is: A customer's :emphasis:`billing address`, not the shipping address, determines whether a :productname:`PayPal Checkout` payment method is available for the customer.
|br|
Example: Only customers with a billing address in Poland will be offered the :productname:`Przelewy24` payment method.



|procedure|

To restrict the accessibility of a :productname:`PayPal Checkout` payment method to specific countries if needed, choose :menuselection:`Shop Settings --> Payment Methods --> <payment method> --> Country --> Assign Countries`.


Testing PayPal Checkout
-----------------------

Configure :productname:`PayPal Checkout` according to your needs and test the result.

|procedure|

1. Under :menuselection:`Master Settings --> Countries`, make sure that the markets you want to cover are active.
#. Under :menuselection:`Shop Settings --> Payment Methods`, do the following:

   a. Assign at least one user group to each of the desired :productname:`PayPal Checkout` payment methods (for example :guilabel:`iDEAL (via PayPal)`.
   b. On corresponding :guilabel:`Master` tab, make sure that you have set the desired minimum and maximum purchase value for the :productname:`PayPal Checkout` payment methods.
      |br|
      Example: The maximum purchase value for :guilabel:`PayPal` payment type is limited to €10,000 by default. The minimum purchase value is €10.
#. Under :menuselection:`Shop Settings --> Shipping Methods`, do the following:

   a. Assign the desired :productname:`PayPal Checkout` payment methods to the respective shipping methods.
   b. Make sure that at least one shipping method is created for payment with the :guilabel:`PayPal` payment method.
      |br|
      Typically, this is the default payment method.

   For more information, see `Payment methods <https://docs.oxid-esales.com/eshop/en/latest/setup/payment-methods/payment-methods.html>`_ of the OXID eShop user documentation.
   |br|
   If required, change the purchase value (€) in 0 to 99999.


Unlocking PayPal Checkout
-------------------------

Unlock :productname:`PayPal Checkout` after testing.

.. attention::

   **Do not use PayPal Plus credentials**

   You already have :productname:`PayPal Plus`? In this case do **not** use the credentials for :productname:`PayPal Checkout`.

   Generate the credentials for :productname:`PayPal Checkout` with your PayPal merchant account again, as described below.

|prerequisites|

You have configured the desired payment methods and tested them successfully with test payments in the PayPal sandbox (see :ref:`configuration:Testing PayPal Checkout`).

|procedure|

1. Under :guilabel:`API credentials` choose the :guilabel:`Live` operating mode.
#. Choose the :guilabel:`Start Merchant Integration (Live)` button.
   |br|
   A dialog box for logging in to PayPal appears.
#. Log in with your existing PayPal merchant account. If you don't have a live login yet, create a new PayPal merchant account.
#. Save your settings.
#. If you use :productname:`PayPal` or :productname:`PayPal Plus`, follow the recommendations under :ref:`configuration:Administering existing PayPal or PayPal Plus orders`.


|result|

The PayPal API credentials are inserted.

The :productname:`PayPal Checkout` module is active and ready for orders from your customers.



.. Intern: oxdajr, Status:
