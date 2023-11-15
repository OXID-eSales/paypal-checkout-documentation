Integrating Consent Management Platforms
========================================

If required, implement a consent procedure, for example with Usercentrics.

Visitors to the store will then be shown a "Privacy settings" banner when they first visit the store, informing them that third-party website tracking technologies are used.

Using the Usercentrics Consent Management Platform (CMP) as an example, you can find more information in the documentation of our module :productname:`OXID Cookie Management powered by usercentrics` under `Funktionsbeschreibung <https://docs.oxid-esales.com/modules/usercentrics/en/latest/funktionsbeschreibung.html>`_ (in German).

Background
----------

In the definition of consent management platforms, :productname:`PayPal Checkout` falls under the category "third-party services".
This is because the function of :productname:`PayPal Checkout` requires resources (specifically: Javascript files)
must be loaded from external servers (third-party providers).

Problem
^^^^^^^

Payment buttons, such as those used with :productname:`PayPal Checkout`, are elementary and functional components of a store because they enable fast and uncomplicated payment processes.

However, payment buttons may pose a data protection problem for particularly privacy-sensitive customers. Such customers may prefer other payment functions.
|br|
This is because third-party providers are theoretically able to use third-party provider access logs to track the customer's visit to the store website.

As a store owner, you must therefore weigh up between

* the functionality of your website

  and

* the data protection of your customers

Solution
^^^^^^^^

If data protection could be a problem for your customers, the solution is to use a consent procedure such as that offered by consent management platforms like Usercentrics.

Example: Integrating Usercentrics in :productname:`PayPal Checkout`
-------------------------------------------------------------------

Use the following instructions for integrating Usercentrics in :productname:`PayPal Checkout` as a sample that you can also implement in a modified form with any other CMP in order to implement a consent procedure.

|prerequisites|

* As a shop owner, you are registered a with Usercentrics and have booked a package suitable for your OXID eShop.

  For more information, see the documentation of our :productname:`OXID Cookie Management powered by Usercentrics` module under `Usercentrics-Paket buchen <https://docs.oxid-esales.com/modules/usercentrics/de/latest/einfuehrung.html#usercentrics-paket-buchen>`_ (in German).

* You have installed :productname:`OXID Cookie Management powered by Usercentrics`.

  For more information, see the documentation of our :productname:`OXID Cookie Management powered by Usercentrics` module under `Installation <https://docs.oxid-esales.com/modules/usercentrics/de/latest/installation.html>`_ (in German).

|procedure|

1. Overwrite the :productname:`PayPal Checkout` module template.

   **Background**: The :productname:`PayPal Checkout` module is prepared in such a way that all templates can be overwritten by individual customizations.
   |br|
   To do so, copy one or more files from the module into your theme template.
   |br|
   Your OXID eShop first uses the module templates, but overwrites them with theme templates if it finds identically defined templates in the store theme.

   To do so, copy the :file:`/source/modules/osc/paypal/views/tpl/shared/layout/base_js.tpl` file into the :file:`/source/Application/views/<Theme of the OXID eShop>/tpl/modules/osc/paypal/` directory.

   If the template directory :file:`/tpl/modules/osc/paypal/` does not yet exist, create it.

   .. _creating-data-processing-service:

#. Create a data processing service for :productname:`PayPal Checkout`.

   If you use Usercentrics, as in our example, do the following:

   a. Start the Usercentrics dashboard.
   #. Choose :menuselection:`Service Settings --> Data Processing Services` (:ref:`oxdajv01`, items 1, 2).
   #. To create a service for :productname:`PayPal Checkout`, choose :guilabel:`Create Custom DPS` (:ref:`oxdajv01`, item 3).

      Under :guilabel:`Custom Data Processing Services` (:ref:`oxdajv01`, item 4), the name of the data processing service is displayed (:ref:`oxdajv01`, item 5).

      .. todo: #tbd: screenshot EN

      .. _oxdajv01:

      .. figure:: /media/screenshots/oxdajv01.png
         :alt: Creating a data processing service in the Usercentrics dashbord
         :width: 650
         :class: with-shadow

         Fig: Creating a data processing service in the Usercentrics dashbord

#. In the :file:`/source/Application/views/<OXID eShop theme>/tpl/modules/osc/paypal/base_js.tpl` file, customize all :productname:`PayPal Checkout` scripts.

   Background: You want to ensure that :emphasis:`all` scripts are only executed after consent of your customer.

   Do the following:

   a. Add the :code:`type="text/plain"` type to your scripts.

      Background: This ensures that the script is not automatically interpreted and executed by the browser when the page is called up.

      To do so, search for the :code:`<script` expression and add :code:`<script type="text/plain"` (see :ref:`Example: Customizing the PayPal checkout scripts <customizing-scripts>`).

   #. Assign a custom data attribute to the scripts of the data processing services you use.

      Background: The data attribute is used to connect to the CMP and to query the consents.

      The syntax of this data attribute is :code:`data-usercentrics="<name of the data processing service>"`.

      Here, :code:`<name of the data processing service>` corresponds to the exact name of the data processing service that you created in step :ref:`Creating a data processing service <creating-data-processing-service>`.

      When copying the name, pay attention to upper and lower case and any spaces.

      In our example (:ref:`oxdajv01`, item 5), the data attribute is therefore :code:`data-usercentrics="PayPal Checkout"` (see :ref:`Example: Customizing the PayPal Checkout scripts <customizing-scripts>`).

   .. _customizing-scripts:

   Example: Customizing the :productname:`PayPal Checkout`-Scripts

   In our example, the original template :file:`/source/modules/osc/paypal/views/tpl/shared/layout/base_js.tpl` looks like this:

   .. code::

       ...
       <script src="[{$oViewConf->getPayPalJsSdkUrl()}]" data-partner-attribution-id="[{$oViewConf-
       >getPayPalPartnerAttributionIdForBanner()}]"></script>
       ...
       <script src="[{$oViewConf->getPayPalJsSdkUrlForACDC()}]" data-client-
       token="[{$oViewConf→getDataClientToken()}]"></script>
       ...
       <script src="[{$oViewConf->getPayPalJsSdkUrlForButtonPayments()}]" data-partner-attribution-
       id="[{$oViewConf→getPayPalPartnerAttributionIdForBanner()}]}]"></script>
       ...
       <script src="[{$oViewConf->getPayPalApiBannerUrl()}]" data-partner-attribution-
       id="[{$oViewConf->getPayPalPartnerAttributionIdForBanner()}]"></script>
       ...


   After customizing the scripts, your template :file:`/source/Application/views/<Theme of the OXID eShop>/tpl/modules/osc/paypal/base_js.tpl` looks like this:

   .. code::

       ...
       <script type="text/plain" data-usercentrics="PayPal Checkout" src="[{$oViewConf-
       >getPayPalJsSdkUrl()}]" data-partner-attribution-id="[{$oViewConf-
       >getPayPalPartnerAttributionIdForBanner()}]"></script>
       ...
       <script type="text/plain" data-usercentrics="PayPal Checkout" src="[{$oViewConf-
       >getPayPalJsSdkUrlForACDC()}]" data-client-
       token="[{$oViewConf→getDataClientToken()}]"></script>
       ...
       <script type="text/plain" data-usercentrics="PayPal Checkout" src="[{$oViewConf-
       >getPayPalJsSdkUrlForButtonPayments()}]" data-partner-attribution-
       id="[{$oViewConf→getPayPalPartnerAttributionIdForBanner()}]}]"></script>
       ...
       <script type="text/plain" data-usercentrics="PayPal Checkout" src="[{$oViewConf-
       >getPayPalApiBannerUrl()}]" data-partner-attribution-id="[{$oViewConf-
       >getPayPalPartnerAttributionIdForBanner()}]"></script>
       ...

|result|

When the page is loaded, the :productname:`PayPal Checkout` scripts are only executed  if your customer has given :productname:`PayPal Checkout` their consent.

.. Intern: oxdajv, Status: