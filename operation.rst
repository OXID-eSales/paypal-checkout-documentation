Operation
=========

Triggering reserved payments manually
-------------------------------------

In case of :technicalname:`PayPal` payment type you can defer and manually trigger the money collection (deferred capture).

If you use this option, make sure to monitor the orders that have not been paid yet.

.. include:: /_static/reuse/note-capture-deferred.rst

|prerequisites|

* For the :technicalname:`PayPal` payment type you have specified how you want to trigger the delayed money collection (see :ref:`configuration:Configuring money collection`).

|procedure|

1. Under :menuselection:`Administer Orders --> Orders`, choose the unpaid order (:ref:`oxdajt01`, item 1).
#. Do the following, depending on how you have configured deferred money collection:

   * If you have selected :guilabel:`Automatically upon delivery`, mark the item as shipped.
     |br|
     To do this, on the :guilabel:`Overview` tab, choose the :guilabel:`Ship Now` button (see :ref:`Operation:Marking an item as shipped`).
   * If you have selected :guilabel:`Manually`, do the following:

     a. Technically optional: Mark the item as shipped (see :ref:`operation:Marking an item as shipped`).
     #. On the :guilabel:`PayPal Checkout` tab, choose the :guilabel:`Capture` button (:ref:`oxdajt01`, item 2).

.. _oxdajt01:

.. figure:: /media/screenshots/oxdajt01.png
   :alt: Triggering a reserved payment manually
   :width: 650
   :class: with-shadow

   Figure: Triggering a reserved payment manually

|result|

With the next page refresh, the order is marked as paid in the list of orders (:ref:`oxdajt02`, item 1).

The PayPal status is :technicalname:`Completed` (:ref:`oxdajt02`, item 2).

.. _oxdajt02:

.. figure:: /media/screenshots/oxdajt02.png
   :alt: Reserved payment: Checking the PayPal status
   :width: 650
   :class: with-shadow

   Figure: Reserved payment: Checking the PayPal status

Marking an item as shipped
--------------------------

Recommendation: If you are shipping physical items and you have a tracking code (a DHL shipment number, for example), save the tracking code.

With the tracking code you can

* Inform your customer by email about the whereabouts of the shipment
* make it easier for PayPal to settle your claim in case of disputes with customers

|procedure|

1. Under :menuselection:`Administer Orders --> Orders` choose the order.
#. On the :guilabel:`Main` tab, enter the tracking code in the corresponding input field (:ref:`oxdajt03`, item 2) as usual.
#. In addition, enter the following information in the corresponding drop-down lists (:ref:`oxdajt03`, item 1):

   * Tracking Carrier (Country): Country-specific version of the shipping service provider.

     Some shipping providers have a global version and one or more country-specific versions, for example DHL Deutsche Post.

     Example: In the case of DHL Deutsche Post as the shipping service provider, :technicalname:`Austria` stands for DHL Austria.

     For more information, see PayPal at `developer.paypal.com/docs/tracking/reference/carriers/ <https://developer.paypal.com/docs/tracking/reference/carriers/>`_.

   * Tracking Carrier (Provider): DHL Deutsche Post, for example

#. Save your settings.

|result|

The tracking code will be sent to PayPal.

.. _oxdajt03:

.. figure:: /media/screenshots/oxdajt03.png
   :alt: Sending tracking code and shipping carrier data to PayPal
   :width: 650
   :class: with-shadow

   Figure: Sending tracking code and shipping provider data to PayPal

Deleting incomplete orders manually
-----------------------------------

Delete incomplete orders manually.

|background|

For technical reasons, PayPal creates orders even if the orders are not completed at the end.

This is the case when the customer selects the :guilabel:`Payment order` button in the checkout, but then does not log in to PayPal and complete the payment process.

To keep the system performant, remove such incomplete orders regularly.

The :emphasis:`manual` deletion -- as opposed to :emphasis:`automatic` deletion -- can be useful, for example, to check whether there are regular cancellations for certain PayPal payment types.

|prerequisites|

You have enabled manual deletion of incomplete orders (see :ref:`configuration:Configuring the handling of incomplete orders`).

|procedure|

1. Choose :menuselection:`Administer Orders --> Orders`.

   Unfinished orders have order number :technicalname:`0` (:ref:`oxdajt04`, item 1a, 1b).

#. Choose :guilabel:`Delete Entry` (:ref:`oxdajt04`, item 2).

.. _oxdajt04:

.. figure:: /media/screenshots/oxdajt04.png
   :alt: Deleting incomplete orders manually
   :width: 650
   :class: with-shadow

   Figure: Deleting incomplete orders manually


.. Intern: oxdajt, Status:
