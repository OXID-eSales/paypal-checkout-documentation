PayPal Checkout V. 2.6.0
========================

.. todo: #ML: Release-Datum:

Neue oder geänderte Funktionen
------------------------------

* Wir haben die Navigation geändert: Konfigurieren Sie PayPal Checkout auf der Registerkarte :guilabel:`Einstell.` des Moduls (siehe :ref:`konfiguration:PayPal Checkout konfigurieren`).
* Gestalten Sie Anordnung, Farbe, Form und Beschriftung der PayPal Checkout-Schaltflächen.

  Weitere Informationen finden Sie unter :ref:`konfiguration:PayPal Checkout-Schaltflächen konfigurieren`.

.. todo: #ML: Was bedeutet "enabled for the Smart-Buttons in the Checkout-Flow"? gemeint ist : Kredit- oder Debitkarte verwalten, PayPal verwalten

* Die von :productname:`PayPal Checkout` bereitgestellten Zahlungsarten sind bei der Neuinstallation mit dem Präfix `PayPal` markiert (siehe :ref:`oxdajr07`).

  Dies verschafft Ihnen beim Konfigurieren Ihrer Zahlungsarten eine bessere Übersicht.

  Weitere Informationen finden Sie unter :ref:`konfiguration:PayPal Checkout testen`, :ref:`Schritt 4 <praefix-anpassen>`.

* Ermöglichen Sie PayPal ein schnelleres Bearbeiten Ihrer Support-Anfragen. Standardmäßig ist dazu bei Bestellungen das Übermitteln der Versionsnummer Ihres OXID eShops und des PayPal Checkout-Moduls aktiviert.

  Weitere Informationen finden Sie unter :ref:`konfiguration:Übermitteln von Daten an PayPal deaktivieren`.

* Kunden speichern Zahlungsinformationen (Kreditkarte und PayPal) für spätere Wiederverwendung im Checkout und können diese Zahlungsinformationen in ihrem Konto verwalten.

  Weitere Informationen finden Sie unter :ref:`konfiguration:PayPal Vaulting deaktivieren`.

.. todo: nicht doku-relevant:Paypal Später zahlen ist deprecated: nicht mhr in Liste, sondern ist jetzt Button;
.. todo: nicht doku-relevant: PP-Standard works with Smart-Buttons in the Checkout-Flow (no redirect anymore) 25:18)
.. todo: #ML: Nur wichtig, wenn Screenshots da; Vorschlag: weglassen
    * Wenn Ihr Kunde im Checkout die :guilabel:`PayPal`-Schaltfläche zum Bezahlen wählt, gelangt er ohne Redirect in das Dialogfenster zum Anmelden bei PayPal.

Installation
------------

Um :productname:`PayPal Checkout` V. 2.6.0 zu nutzen, installieren Sie es in Ihrem :productname:`OXID eShop` 6.3.x to 6.5.x.

Weitere Informationen finden Sie unter :ref:`installation:Installation`.

Update
------

Um die Funktionen und Korrekturen von :productname:`PayPal Checkout` V. 2.6.0 in einer bestehenden Installation zu nutzen, machen Sie ein Update.

Weitere Informationen finden Sie unter :ref:`installation:Minor Update installieren`.

.. todo: reaktivieren in 2.5.1
    * :ref:`installation:Patch-Update installieren`
