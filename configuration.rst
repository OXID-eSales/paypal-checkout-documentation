Configuration
=============

Make the :productname:`PayPal Checkout` module operational for your OXID eShop.

You already have PayPal or PayPal Plus?
---------------------------------------

Ensure a smooth transition to the new :productname:`PayPal Checkout` module.

To do this, note the following two restrictions:

* You cannot run :productname:`PayPal Checkout` with your :productname:`PayPal Plus` credentials.

  Reason: Access data and webhook must be regenerated so that the connection to :productname:`PayPal Checkout` works with the full range of functions.

  Follow the instructions under :ref:`configuration:Re-running the registration for PayPal Checkout`.

* To manage existing orders, both modules, for example :productname:`PayPal Checkout` and :productname:`PayPal`, must be active at the same time.
  |br|
  Follow the instructions under :ref:`configuration:Administering existing PayPal or PayPal Plus orders`.

Re-running the registration for PayPal Checkout
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. attention::

   **Do not reuse access data**

   Do not use the access data of your existing :productname:`PayPal Plus` account to set up :productname:`PayPal Checkout`.

   If you reuse :productname:`PayPal Plus` credentials, you will encounter technical problems limiting the functionality of :productname:`PayPal Checkout`:

   * The webhooks are not activated correctly, information is not transmitted correctly, but the errors are not immediately recognizable.
   * Payment methods such as installment purchase are not available, payment by credit card is not activated, functions are not available.

   To ensure correct functioning and activation of all features and payment methods, go through the registration process again.

   This is the only way to generate new access data and webhook, with which the connection to :productname:`PayPal Checkout` works to its full extent.

|procedure|

Do the following:

1. Test :productname:`PayPal Checkout` in the PayPal sandbox with :emphasis:`test` accounts as described in :ref:`configuration:Configuring PayPal Checkout`.
#. To unlock your :emphasis:`live` system, generate new credentials.
   |br|
   To do this, go through the PayPal registration process again with your PayPal merchant account details.

   For more information, see :ref:`configuration:API credentials: Onboarding`.

Administering existing PayPal or PayPal Plus orders
---------------------------------------------------

If you already use the :productname:`PayPal` or :productname:`PayPal Plus` module, note the following limitation:

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


#. Enable :productname:`PayPal Checkout` for live operation as described under :ref:`configuration:Activating PayPal Checkout manually`.
#. Choose :menuselection:`Shop Settings --> Payment Methods`.
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
#. Go through the registration process with PayPal (onboarding).
#. Optional: Disable the express checkout feature of :productname:`PayPal Checkout` if needed.
#. Optional: Specify if you want to offer PayPal installment payment (see :ref:`oxdajr08`) to your customers.
#. If necessary, contact PayPal Customer Service to determine the best way for PayPal to handle 3D Secure authentication in your case (see :ref:`oxdajr11`).
#. Configure the payment methods provided by :productname:`PayPal Checkout` as payment methods in your eShop:

   * Enable the countries you want to cover.
   * Link the payment methods to your shipping methods and shipping rules.

#. Run test payments in the :productname:`PayPal Checkout` sandbox. and adjust the configuration until all payment processes works as you want.
#. Enable :productname:`PayPal Checkout`:

   a. If you do not have a merchant account yet, create one for live operation.
   b. Switch to :guilabel:`Live` operation mode.
#. If required: If you have particularly privacy-sensitive customers, implement a consent procedure, for example with Usercentrics.

   For more information, see :ref:`cmp-integration:Integrating Consent Management Platforms`.

Activating PayPal Checkout manually
-----------------------------------

Ensure :productname:`PayPal Checkout` is activated in each subshop where you want to use the module.

|Procedure|

1. Choose :menuselection:`Extensions --> Modules`.
#. Choose the :guilabel:`PayPal Checkout for OXID` module and choose :menuselection:`Overview --> Activate`.


|result|

Under :menuselection:`Shop Settings --> Payment Methods`, the payment methods :guilabel:`PayPal` as well as other important payment methods are marked as active.

The payment methods that belong to :guilabel:`PayPal Checkout for OXID` have the prefix `PayPal`, for example, `PayPal ApplePay`. This allows you to easily distinguish them from similar payment methods provided by other payment modules.

To actually use a specific country-specific payment method, under :menuselection:`Master Settings --> Countries`, mark the relevant country as active .

|example|

To be able to offer iDEAL, you must have made sure that you have set the Netherlands as active under :menuselection:`Master Settings --> Countries`.

Configuring PayPal Checkout
---------------------------

Start configuring.

|prerequisites|

* You have activated the :productname:`PayPal Checkout` module.
* You have created a PayPal Sandbox account.

  For more information, see :ref:`paypal-sandbox:Testing PayPal Checkout in the PayPal Sandbox`.

|procedure|

1. Under :menuselection:`Extensions --> Modules`, choose the `PayPal Checkout for OXID` module.
2. Choose the :guilabel:`Settings` tab.

API Credentials: Onboarding
^^^^^^^^^^^^^^^^^^^^^^^^^^^

Go through the registration process with PayPal (onboarding).

You use it to create access data (client ID and password), activate functions (e.g. payment methods or new functions such as PayPal Vaulting) and generate a webhook.

The webhook allows PayPal to contact your OXID eShop and provide real-time status messages, for example about completed transactions.

In the first step, you test the payment methods provided with :productname:`PayPal Checkout` with test access data in a *sandbox*.

.. tip::

   To debug, let the shop track the incoming webhooks.

   For more information, see :ref:`troubleshooting:Switching on the debug mode`.


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

* If you want to offer Google Pay, for test payments you have

  * a Google account
  * a credit card

  If you make payments with your credit card in sandbox mode, your credit card will :emphasis:`not` be charged. Google will replace your real credit card number with a sample credit card number.

  If necessary, check whether Google Pay is active. For more information, see :ref:`paypal-sandbox:Checking Google Pay and Apple Pay activation`.

|procedure|

We describe the registration process (onboarding) using a sandbox account as an example. The live process is analogous.

.. include:: /_static/reuse/note-ee-onboarding.rst

.. attention::

   **Reusing access data and webhook**

   In any case, make sure that :emphasis:`all` PayPal payment methods and functions are available to you.

   * Case 1: You have :productname:`PayPal` or :productname:`PayPal Plus`? -- Go through the registration process again to regenerate access data and webhook to connect to :productname:`PayPal Checkout`.

     For more information, see :ref:`configuration:You already have PayPal or PayPal Plus?`.

   * Case 2: You have an earlier version of :productname:`PayPal Checkout` and are updating? -- Go through the registration process again.

     Otherwise, the payment methods and functions of the newer version of :productname:`PayPal Checkout` will not be available to you.

   * Case 3: You have already completed the registration process for the current version of :productname:`PayPal Checkout` and are moving your OXID eShop to another domain, for example? -- In this case, you can reuse the access data and webhook.

1. To log in to the sandbox, under :guilabel:`API credentials`, choose the :guilabel:`Sign Up Merchant Integration (Sandbox)` button (:ref:`oxdajr03`, item 1).

   .. _oxdajr03:

   .. figure:: /media/screenshots/oxdajr03.png
      :alt: Starting the webhook generation
      :width: 650
      :class: with-shadow

      Fig.: Starting the webhook generation

#. Log in with the e-mail address of the sandbox merchant account (:ref:`oxdajr01`) and confirm the queries.

   .. _oxdajr01:

   .. figure:: /media/screenshots/oxdajr01.png
      :alt: Starting the registration of the sandbox merchant account

      Fig.: Starting the registration of the sandbox merchant account

   A message indicates success (:ref:`oxdajr04`).

    .. _oxdajr04:

    .. figure:: /media/screenshots/oxdajr04.png
       :alt: Message onboarding successful
       :width: 650
       :class: with-shadow

       Fig.: Message onboarding successful

    You go back to your OXID eShop.

    The client ID and the webhook ID are displayed (:ref:`oxdajr05`, items 1, 2).

    .. _oxdajr05:

    .. figure:: /media/screenshots/oxdajr05.png
       :alt: Client ID/secret and webhook ID created
       :width: 650
       :class: with-shadow

       Fig.: Client ID/secret and webhook ID created


    .. _activation-creditcard:

#. If you want to use the payment methods Pay upon Invoice or credit card, under :guilabel:`Activation for special payment methods has taken place` (:ref:`oxdajr05`, item 5), check whether the activation has been done.

   .. hint::

      **Payment method fallback credit card**.

      If the activation :emphasis:`did not` happen automatically (:guilabel:`credit card: No`), contact your PayPal representative.

      If the activation has taken place, the credit card payment method is available in the checkout step Shipping & Payment Method (:ref:`oxdajr02`, item 1).

      If activation is :emphasis:`not` possible, a fallback solution is available as an alternative (:ref:`oxdajr02`, ìtem 2).

      .. _oxdajr02:

      .. figure:: media/screenshots/oxdajr02.png
         :alt: Credit card options and SEPA Direct Debit
         :width: 650
         :class: with-shadow

         Fig.: Credit card options and SEPA Direct Debit


   .. hint::

      **Payment method Purchase upon invoice**

      PayPal offers the payment method Purchase upon invoice only to store operators from Germany.

|result|

* As soon as you have authorized PayPal to connect your sandbox account with the PayPal test store, the API credentials will be displayed. The module is active (:ref:`oxdajr05a`, item 1).

  .. _oxdajr05a:

  .. figure:: /media/screenshots/oxdajr05a.png
     :alt: PayPal Checkout module active
     :width: 650

     Fig.: PayPal Checkout module active

* Under :menuselection:`Shop Settings --> Payment Methods`, the payment method :guilabel:`PayPal` (technical name :technicalname:`oscpaypal`, shown at the bottom left) is active (:ref:`oxdajr07`).

  .. _oxdajr07:

  .. figure:: /media/screenshots/oxdajr07.png
     :alt: PayPal payment method active
     :width: 650

     Fig.: PayPal payment method active


The payment methods "Credit card" and "Purchase upon invoice" are not available? Follow the instructions under :ref:`troubleshooting:Payment methods or functions not available`.

.. hint::

   **Generating a new webhook**

   Sometimes it may be necessary to delete the existing webhook and generate a new one.

   Do the following:

   1. To delete the webhook, delete the login data and choose :guilabel:`Save`.
   #. To go through the registration process again and regenerate access data and webhook, chose the :guilabel:`Signup Merchant Integration` button.

.. include:: /_static/reuse/hint-debugmode.rst

Activating the Apple Pay payment method
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

If you want to offer :productname:`Apple Pay`, register the (sandbox) domain of your OXID e-shop.

|procedure|

1. Under `paypal.com/signin <https://www.paypal.com/signin>`_, log in with your PayPal (sandbox) merchant account.

   Alternatively: To jump directly to step :ref:`Add Domain <addDomain>`, log in at the following URL: `sandbox.paypal.com/uccservicing/apm/applepay <https://www.sandbox.paypal.com/uccservicing/apm/applepay>`_.

#. In the menu under your name, choose the :guilabel:`Account Settings` menu item (:ref:`oxdajr18`, item 1).

   .. _oxdajr18:

   .. figure:: /media/screenshots/oxdajr18.png
      :alt: Open account settings
      :width: 650
      :class: with-shadow

      Fig.: Open account settings

#. In the left navigation bar, choose :guilabel:`Payment methods`.
#. Choose :guilabel:`ApplePay verwalten` (:ref:`oxdajr18a`).

   .. todo: :guilabel:`ApplePay verwalten` im Original deutsch!

   .. _oxdajr18a:

   .. figure:: /media/screenshots/oxdajr18a.png
      :alt: Managing the ApplePay payment method
      :width: 650
      :class: with-shadow

      Fig.: Managing the ApplePay payment method

   .. _addDomain:

#. Choose :guilabel:`Add Domain` (:ref:`oxdajr18b`).

   .. _oxdajr18b:

   .. figure:: /media/screenshots/oxdajr18b.png
      :alt: Adding the domain
      :width: 650
      :class: with-shadow

      Fig.: Adding the domain

   You go to a page to register your website with Apple Pay (:ref:`oxdajr19`).

#. Specify the domain name (the URL without the schema, e.g. ``https://``) of your OXID e-shop (``www.my-oxid-eshop.com``, for example) (:ref:`oxdajr19`, item 1).

   .. _oxdajr19:

   .. figure:: /media/screenshots/oxdajr19.png
      :alt: Registering the domain name
      :width: 300
      :class: with-shadow

      Fig.: Registering the domain name

   The system generates a domain association file which you use to proves that you are the owner of the website.

   It is automatically saved in the root directory of your OXID eShop. The :emphasis:`manual` download and hosting of the file (:ref:`oxdajr19`, item 2) is therefore normally :emphasis:`not` necessary.

#. Optional: To check whether the domain association file is available, open the file via browser.

   To do so, add the directory name to the URL of your OXID eShop (:ref:`oxdajr20`).

   Schema: ``https://<sandbox-domain-name>/.well-known/apple-developer-merchantid-domain-association``

   .. _oxdajr20:

   .. figure:: /media/screenshots/oxdajr20.png
      :alt: Verifying the domain association file
      :width: 350
      :class: with-shadow

      Fig.: Verifying the domain association file

#. Choose :guilabel:`Register Domain` (:ref:`oxdajr19`, item 3).
#. Confirm the message confirming that Apple Pay has registered your OXID eShop (:ref:`oxdajr21`).

   .. _oxdajr21:

   .. figure:: /media/screenshots/oxdajr21.png
      :alt: Confirming the domain registration
      :width: 350
      :class: with-shadow

      Fig.: Confirming the domain registration

#. Under :menuselection:`Shop settings --> Payment methods`, configure the :technicalname:`Apple Pay` payment method.
#. Optional: Carry out a test payment with an Apple device.

   .. note::
      To make test payments with Apple Pay, you need an Apple device.

      Customers without an Apple device will not be offered the :technicalname:`Apple Pay` payment method.

For more information on registering your sandbox domain and going live with Apple Pay, see the PayPal documentation under

* `Set up your sandbox account to accept Apple Pay <https://developer.paypal.com/docs/checkout/apm/apple-pay/#link-setupyoursandboxaccounttoacceptapplepay>`_
* `Go live <https://developer.paypal.com/docs/checkout/apm/apple-pay/#link-golive>`_

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
* in the mini shopping cart (:ref:`oxdajr09`, item 1)
* on the checkout page

So, your customers can use their PayPal account to trigger the order at any time.

If you want your customers to have to register in your eShop, disable the quick purchase feature.

.. todo: #tbd: Screenshot EN

.. _oxdajr09:

.. figure:: /media/screenshots/oxdajr09.png
   :alt: Mini shopping cart and Pay Later
   :width: 650

   Fig.: Mini shopping cart and Pay Later

|procedure|

1. To disable :productname:`PayPal Checkout`'s express checkout feature, uncheck :guilabel:`Product details page`, :guilabel:`Basket`, and :guilabel:`Mini-Basket` (:ref:`oxdajr10`, item 1).
2. Save your settings.

.. _oxdajr10:

.. figure:: /media/screenshots/oxdajr10.png
   :alt: Controlling the display of PayPal buttons
   :width: 650

   Fig.: Controlling the display of PayPal buttons

|Result|

The PayPal button appears only on the checkout page.

Button placement settings: Pay later
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Decide whether you want to offer the Pay Later feature (:ref:`oxdajr09`, item 2).

Pay Later means, for example, that PayPal offers customers in Germany the "Pay after 30 days" or PayPal installments options.

For more information about country coverage and country-specific features of the Pay Later feature, see `developer.paypal.com/docs/checkout/pay-later/en <https://developer.paypal.com/docs/checkout/pay-later/de/>`_.


|procedure|

1. To offer your customers Pay Later features, choose the :guilabel:`"Show Pay Later" button?` checkbox (:ref:`oxdajr10`, item 2).
#. Save your settings.

Configuring PayPal Checkout Buttons
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Customize the PayPal Checkout buttons to match the design of your OXID eShop.

Specify how the PayPal Checkout buttons should be displayed in terms of layout, color, shape, and label on the product detail page, in the cart, and during checkout.

|procedure|

1. Choose :guilabel:`Buttons Customization`.
2. Choose the desired settings (:ref:`oxdajr22`).

   .. _oxdajr22:

   .. figure:: /media/screenshots/oxdajr22.png
      :alt: Configuring PayPal Checkout buttons
      :width: 650
      :class: with-shadow

      Fig.: Configuring PayPal Checkout buttons

3. Save your settings.

|result|

The PayPal Checkout buttons will appear in the desired design, in our example, round and black (:ref:`oxdajr23`).

.. _oxdajr23:

.. figure:: /media/screenshots/oxdajr23.png
   :alt: PayPal Checkout buttons: Checking the layout
   :width: 350
   :class: with-shadow

   Fig.: PayPal Checkout buttons: Checking the layout


Login with PayPal: Activating automatic login
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

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

Configuring money collection
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

For the :guilabel:`PayPal` payment type, specify whether payments are to be collected immediately, or whether payments should be deferred for a maximum of 30 days.

|example|

Typically, the invoice amount is collected immediately.

However, in certain cases it makes sense that the payment is only triggered by the delivery:

* You sell certain individualized products that you do not manufacture, commission, or order until the order is received.
* You have an eShop for business customers. Here, the delivery quantities and payment amounts are larger than for private customers.
  |br|
  In the event of an error, returns management would be correspondingly more difficult.
  |br|
  That's why you want to make sure that payment is only triggered when the goods are there or on their way to be shipped.

.. include:: /_static/reuse/note-capture-deferred.rst


|procedure|

1. Under :guilabel:`PayPal Standard - Money Collection` (:ref:`oxdajr12`), you have the following options:

   * To have payments always triggered directly, choose :guilabel:`Directly`.
   * To reserve the payment only and trigger it later, you have the following options:

     * :guilabel:`automatically upon delivery`: The payment is triggered as soon as you have set the ordered item to the status :technicalname:`delivered` in your eShop.
     * :guilabel:`manually`: The payment is triggered when you select the order under :menuselection:`Administer Orders --> Orders` and, on the :guilabel:`PayPal Checkout` tab, choose the :guilabel:`Collect` button.

   Reservation is not possible for the :emphasis:`Quick Purchase` function of :productname:`PayPal Checkout` (payment method :guilabel:`PayPal Express`). The invoice amount is always collected immediately for :guilabel:`PayPal Express` payment method.

   .. _oxdajr12:

   .. figure:: /media/screenshots/oxdajr12.png
      :alt: Configuring deferred payment
      :width: 650
      :class: with-shadow

      Fig.: Configuring deferred payment

#. Save your settings.
#. Make sure you have assigned the :guilabel:`PayPal` payment method only to the customized products in your eShop.
   |br|
   The delayed payment for :productname:`PayPal Checkout` payments will take effect for all items in your eShop to which you have assigned this payment method.
   |br|
   Reservation is not possible for the :emphasis:`Fast Checkout` feature of :productname:`PayPal Checkout` (payment method :guilabel:`PayPal Express`).  For the :guilabel:`PayPal Express` payment method, the invoice amount is always collected immediately.

#. Assign the :guilabel:`PayPal` payment method to the customized products in your eShop.

   It is technically not possible to assign certain payment methods exclusively to certain items. We suggest the following workaround:

   a. Create a dedicated shipping cost rule and assign the items in question to it.
      |br|
      Make sure that the :guilabel:`Quantity` condition is correctly specified.
   b. Create a dedicated shipping method and assign the :guilabel:`PayPal` payment method and shipping cost rule for individualized products to it.
   c. In the description text of the item, instruct your customers to choose only the dedicated shipping method for payment (:ref:`oxdajr06`, item 1).

      .. _oxdajr06:

      .. figure:: /media/screenshots/oxdajr06.png
         :alt: Choosing a dedicated shipping method in checkout
         :width: 650
         :class: with-shadow

         Fig.: Choosing a dedicated shipping method in checkout

|result|

In case of deferred money collection, under :menuselection:`Administer orders --> Orders`, collect the invoice amounts as follows (see :ref:`operation:Triggering reserved payments manually`):

* If you have chosen :guilabel:`automatically upon delivery`: You will trigger the payment as soon as you select the :guilabel:`Ship Now` button, setting the ordered item to the :technicalname:`Delivered` status.
* If you have chosen :guilabel:`manually`: You trigger the payment by choosing the order under :menuselection:`Administer Orders --> Orders` and choosing the :guilabel:`PayPal Checkout` button on the :guilabel:`Collect` tab.


Configuring 3D Secure for debit and credit cards
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

To meet the legal requirements for online payments with credit cards, use 3D Secure authentication.

With 3D Secure authentication, during the transaction, the issuing bank asks the customer to identify himself as the legitimate cardholder by entering a password.

This authentication by the issuing bank is mandatory throughout Europe in certain situations -- for example, when depositing a credit card in an e-wallet (PayPal, for example) or for risky transactions.

For more information about 3D Secure authentication, see `paypal.com/en/webapps/mpp/3dsecure-faqs <https://www.paypal.com/en/webapps/mpp/3dsecure-faqs>`_.

You have the following options:

* For the highest possible security, enforce a 3D Secure query for every credit card transaction.
* Have PayPal ensure that 3D Secure is only used when necessary.
  |br|
  PayPal ensures that most of your customers can shop undisturbed.
* Disable 3D Secure result evaluation: To learn in which cases this setting may be useful for you, contact PayPal Customer Service at `paypal.com/en/webapps/helpcenter/helphub/home/ <https://www.paypal.com/en/webapps/helpcenter/helphub/home/>`_.

|procedure|

1. If needed: To determine the best setting for your purposes, contact PayPal Customer Service at `paypal.com/en/webapps/helpcenter/helphub/home <https://www.paypal.com/de/webapps/helpcenter/helphub/home/>`_.
#. Choose the desired setting (:ref:`oxdajr11`).
#. Save your settings.

.. _oxdajr11:

.. figure:: /media/screenshots/oxdajr11.png
   :alt: Configuring 3D Secure authentication
   :width: 650

   Fig.: Configuring 3D Secure authentication

Configuring the handling of incomplete orders
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Specify whether to delete incomplete orders automatically or manually.

-----------------------------------------------------------

|background|

For technical reasons, PayPal creates orders even if the orders are not completed at the end.

This is the case when the customer chooses the :guilabel:`Payment order` button in the checkout, but then does not log in to PayPal and complete the payment process.

For more information, see :ref:`operation:Deleting incomplete orders manually`.

-----------------------------------------------------------

* The :emphasis:`automatic` deletion is recommended, for example, if you sell low-priced bulk items.
  |br|
  It would be inconvenient for you to manually delete numerous incomplete orders one by one.
* :emphasis:`manual` deletion may be useful, for example, if you sell high-priced goods with small sales volumes.

  If customers bounce during the order process, manual deletion allows you to determine if there may be difficulties with certain PayPal payment methods.

|procedure|

1. If you want the system to automatically delete incomplete orders, choose the :guilabel:`Automatically delete not finished orders?` checkbox (:ref:`oxdajr13`, item 1).

   If necessary, adjust the default retention time of 60 minutes :ref:`oxdajr13`, item 2).

#. Save your settings.

|result|

If you leave automatic deletion disabled, you will have to delete incomplete orders manually on a regular basis.

For more information see :ref:`operation:Deleting incomplete orders manually`.

.. _oxdajr13:

.. figure:: /media/screenshots/oxdajr13.png
   :alt: Configuring automatic deletion of incomplete orders.
   :width: 650
   :class: with-shadow

   Fig.: Configuring automatic deletion of incomplete orders


Banner settings: Re-using your PayPal banner settings
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Optional: If you already use the :productname:`PayPal` module, conveniently re-use your banner settings for :productname:`PayPal Checkout`.

Alternatively, set the banner settings manually as described below under :ref:`configuration:Banner settings: Configuring PayPal installments`.

|prerequisites|

:productname:`PayPal` is activated.


|procedure|

1. To apply the existing PayPal banner advertising settings, choose the :guilabel:`Apply settings from the classic PayPal module` button.
   |br|
   The button appears only if the :productname:`PayPal` module is still activated.
#. Save your settings.

Banner settings: Configuring PayPal installments
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Specify whether you want to advertise PayPal installments with banners (:ref:`oxdajr08`).

If you want to take advantage of advertising PayPal installments, specify where you want the banners to appear, for example, on the home page, on the detail page of items, on category pages, in search results, and/or in the checkout process.

.. todo: screenshot EN

.. _oxdajr08:

.. figure:: /media/screenshots/oxdajr08.png
   :alt: Example: Installment payment banner on a category page
   :width: 650

   Fig.: Example: installment banner on a category page

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

Locals: Localizing PayPal Checkout buttons
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

By default, German and American English are configured as languages in which customers are asked to enter their credit card details, for example.

If you have configured additional languages under :menuselection:`Master data --> Languages`, make sure that you configure the appropriate variant (language abbreviation according to ISO 639-1 and country according to ISO 3166-1, for example fr_CA for Canadian French) for messages from :productname:`PayPal Checkout`.

|procedure|

1. Under :menuselection:`Master Settings --> Languages`, check the languages that you have configured.
#. Under :menuselection:`Locals`, in the :guilabel:`regional language settings` field, enter the corresponding language abbreviations  separated by commas in the :technicalname:`<language abbreviation>_<country abbreviation>` format.

   Or adapt the default language abbreviations. Example: If your OXID eShop is aimed at customers in Great Britain, enter the language abbreviation for English in :technicalname:`en_UK`.

#. Save your settings.

Using PayPal Vaulting
^^^^^^^^^^^^^^^^^^^^^

PayPal Vaulting is :emphasis:`activated` by default.

Your customers can use this feature to save their payment information (for credit cards or PayPal accounts) during checkout for future purchases (:ref:`oxdajr15`, item 1) and, if needed, delete them under :guilabel:`Manage PayPal` or :guilabel:`Manage Credit or Debit Card` (:ref:`oxdajr16`).


.. _oxdajr15:

.. figure:: /media/screenshots/oxdajr15.png
   :alt: Saving payment information during checkout
   :width: 650
   :class: with-shadow

   Fig.: Saving payment information during checkout

.. _oxdajr16:

.. figure:: /media/screenshots/oxdajr16.png
   :alt: Managing payment information in the account
   :width: 650
   :class: with-shadow

   Fig.: Managing payment information in the account

This speeds up the checkout process for regular customers and increases the user-friendliness of your OXID eShop. The payment button is labeled accordingly (:ref:`oxdajr17`, item 1).

.. _oxdajr17:

.. figure:: /media/screenshots/oxdajr17.png
   :alt: Paying with saved payment method
   :width: 650
   :class: with-shadow

   Fig.: Paying with saved payment method

PayPal Vaulting automatically creates a PayPal billing agreement with your customers. This allows you to charge the account in the future without your customers having to re-authenticate with PayPal or select a payment method from their wallet.

The function is practical, but you can deactivate it if required.

|procedure|

1. To deactivate PayPal Vaulting, deactivate the :guilabel:`PayPal Vaulting active` checkbox (:ref:`oxdajr14`, item 1).
#. Save your settings.

.. _oxdajr14:

.. figure:: /media/screenshots/oxdajr14.png
   :alt: Deactivating PayPal Vaulting
   :width: 650
   :class: with-shadow

   Figure: Deactivating PayPal Vaulting

Adjusting pseudo shipping costs for PayPal Express
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

To enable payments with PayPal Express, use so-called pseudo shipping costs. In this way you ensure that the value of the shopping basket corresponds approximately to the value that is collected from the customer's PayPal account at checkout.

The :emphasis:`actual` shipping costs are determined during the checkout process. The customer therefore does not pay the pseudo shipping costs, but the real costs.

|background|

The pseudo shipping costs are only used for the moment of authorization (the customer cannot be logged in at that moment).

When a customer uses PayPal Express and adds an item to the shopping basket, they authorize a payment in the amount of the basket value plus a tolerance of approximately 5% for shipping costs.

In the case of low-priced items, the shipping costs may amount to more than 5% of the item price.

Example: The item price is 5 euros, the shipping costs are 4 euros. The tolerance is far exceeded.

If PayPal must permanently hold financial reserves because the real shipping costs permanently deviate from the shipping costs that PayPal estimates and that PayPal Express authorizes, then it may become difficult for PayPal to continue to provide you with the PayPal Express payment method.

To avoid this, bring the authorization price as close as possible to the final price.

Exceptions:

* If the customer is already logged in, the system uses the real shipping costs for authorization from the outset.
* If you have activated the :guilabel:`Calculate default Shipping costs when ser is not logged in yet` (in your  OXID eShop under :menuselection:`Master Settings --> Core Settings --> Settings --> Other Settings` ), the shipping costs will be displayed accordingly and not the PayPal pseudo shipping costs.

  If you have :emphasis:`not` activated the function (default setting), the PayPal pseudo shipping costs are displayed.

  For more information, in the OXID eShop user documentation under :menuselection:`Setup --> Payment and shipping`, see `Display shipping costs in the shopping basket overview <https://docs.oxid-esales.com/eshop/en/latest/setup/payment-and-shipping/displaying-shipping-costs.html>`_.

|procedure|

Under :guilabel:`Pseudo shipping costs for PayPal Express`, adjust the default value of 3.50 euros.

Specify a value for the standard shipping costs that corresponds to the shipping costs of typical purchases in your OXID eShop.

A value that covers more than 90% of purchases is ideal.

Disabling Transmitting Data to PayPal
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Under :guilabel:`PayPal custom id field contents`, the checkbox :guilabel:`PayPal custom id field will be JSON encoded string with order number, shop version and the PayPal module version` is enabled by default.

By enabling this, you agree that, when placing an order, not only the order number but also the version of your OXID eShop and the PayPal Checkout module will be transmitted to PayPal in the `Order Number` field.

In the event of a support request, PayPal can use this information to process your inquiry more quickly.

|procedure|

If you want to disable the transmission of the OXID eShop and PayPal Checkout version, simply uncheck the box :guilabel:`PayPal custom id field will be JSON encoded string with order number, shop version and the PayPal module version`.

Configure Webhook
^^^^^^^^^^^^^^^^^

Specify how long the system waits after receiving a webhook before processing it.

|background|

PayPal webhooks inform the shop about the current order status and partially finalize orders if a customer does not complete the checkout process through to the "Thank you" page.

For certain alternative payment methods — for example iDEAL or Bancontact — PayPal confirms the payment asynchronously: the customer completes the checkout in the frontend, but the actual payment confirmation only arrives shortly after via webhook.

In this time window, a race condition can occur: the webhook tries to mark the order as paid before the shop has fully saved the order data.

The time delay prevents this conflict. If a webhook arrives before the waiting time has elapsed, the system responds with HTTP 503 and a :technicalname:`Retry-After` header. PayPal automatically retries the delivery.

|procedure|

1. Under :guilabel:`Webhook`, enter the desired waiting time in seconds in the :guilabel:`Time delay in seconds (default: 20)` field.
#. Save your settings.

Optional: Configuring the country mapping of PayPal Checkout payment methods
----------------------------------------------------------------------------

Make sure that certain :productname:`PayPal Checkout` payment methods are only available in the countries you choose.

|background|

With the initial installation, the :productname:`PayPal Checkout` payment methods are automatically assigned to the corresponding countries.

Most :productname:`PayPal Checkout` payment methods cover multiple countries. For example, the :productname:`Credit Card` payment method is available to customers worldwide, and the :productname:`Pay Later` payment method is available to your customers in countries in Europe, the USA, and Australia, for example.

For more information about the country coverage of each :productname:`PayPal Checkout` payment method, see :ref:`introduction:Market coverage by payment method`.

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

      Die von :productname:`PayPal Checkout` bereitgestellten Zahlungsarten haben das Präfix PayPal, beispielsweise `PayPal Bancontact`.

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

   .. _adjust-prefix:

#. Make sure that under :menuselection:`Shop Settings --> Payment Methods`, you have entered the name of each payment method in the :guilabel:`Name` field as you want it to appear during checkout.

   .. important::

      Typically, you remove the `PayPal` prefix that the payment methods provided by :productname:`PayPal Checkout` have.

      The prefix is used solely for clarity during configuration.

      Example: The name displayed at checkout should be `GooglePay` instead of `PayPal GooglePay`, `Bancontact` instead of `PayPal Bancontact`, and so on.

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
#. Choose the :guilabel:`Sign Up Merchant Integration (Live)` button.
   |br|
   A dialog box for logging in to PayPal appears.
#. Log in with your existing PayPal merchant account. If you don't have a live login yet, create a new PayPal merchant account.
#. Save your settings.
#. If you use :productname:`PayPal` or :productname:`PayPal Plus`, follow the recommendations under :ref:`configuration:Administering existing PayPal or PayPal Plus orders`.


|result|

The PayPal API credentials are inserted.

The :productname:`PayPal Checkout` module is active and ready for orders from your customers.



.. Intern: oxdajr, Status:
