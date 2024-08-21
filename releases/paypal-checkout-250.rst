PayPal Checkout V. 2.5.0
========================

.. todo: #ML: determine date

Release-Datum: #tbd.2024

Neue oder geänderte Funktionen
------------------------------

Wir haben die Zahlungsart GooglePay hinzugefügt.

.. todo: #tbd: delete: ML: Was steckt hinter folgendem? -- ML: nur intern
    * PayPal-Request-Id based on serialized body, no extra PayPal-Request-Id necessary anymore
    * use PayPal-Client v2.0.14


Apple Pay und Google Pay
^^^^^^^^^^^^^^^^^^^^^^^^

.. todo: ML: Registrierungsprozess (Onboarding) (erneut) durchlaufen nach Update? -- ja
.. todo: https://github.com/OXID-eSales/paypal-module/blob/v2.5.0-rc.1/src/Core/PayPalDefinitions.php

Ermöglichen Sie mit Apple Pay und Google Pay Zahlungsvorgänge weltweit und in 25 Währungen.

Weitere Informationen zur Abdeckung finden Sie unter

* :ref:`einfuehrung:Marktabdeckung nach Zahlungsmethoden`
* :ref:`einfuehrung:Währungsabdeckung nach Zahlungsmethode`

|procedure|

1. Installieren Sie :productname:`PayPal Checkout` neu oder machen Sie ein Update.
#. Durchlaufen Sie den Registrierungsprozess (Onboarding) (auch bei einem Update).

   Weitere Informationen finden Sie unter :ref:`konfiguration:API-Anmeldeinformationen: Onboarding`.

#. Verifizieren Sie, dass die Freischaltung für die Zahlungsart Google Pay erfolgt ist (:ref:`oxdajr05rn`, Pos. 5).

   .. _oxdajr05rn:

   .. figure:: /media/screenshots/oxdajr05.png
      :alt: Client-ID/Passwort und Webhook-ID erzeugt
      :width: 650
      :class: with-shadow

      Abb.: Client-ID/Passwort und Webhook-ID erzeugt

   Wenn keine Freischaltung erfolgt ist, kontaktieren Sie den PayPal-Support.

#. Aktivieren Sie Apple Pay.

   Weitere Informationen finden Sie unter :ref:`konfiguration:Apple Pay als Zahlungsart aktivieren`.

   Google Pay ist standardmäßig aktiviert. Sie brauchen nur ein Google-Konto und eine Kreditkarte.

#. Konfigurieren Sie die Länderzuordnung von Apple Pay und Google Pay.

   Weitere Informationen finden Sie unter :ref:`konfiguration:Optional: Länderzuordnung von PayPal Checkout-Zahlungsmethoden konfigurieren`.

#. Um die Zahlungsart Apple Pay und Google Pay zu konfigurieren, wählen Sie

   * :menuselection:`Shopeinstellungen --> Zahlungsarten --> GooglePay`.
   * :menuselection:`Shopeinstellungen --> Zahlungsarten --> ApplePay`.

#. Schalten Sie Google Pay nach dem Testen für den Live-Betrieb frei.

   Weitere Informationen finden Sie unter :ref:`konfiguration:PayPal Checkout freischalten`.

Installation
------------

Um :productname:`PayPal Checkout` V. 2.5.0 zu nutzen, installieren Sie es in Ihrem :productname:`OXID eShop` 6.3.x to 6.5.x.

Weitere Informationen finden Sie unter :ref:`installation:Installation`.

Update
------

Um die Funktionen und Korrekturen von :productname:`PayPal Checkout` V. 2.5.0 in einer bestehenden Installation zu nutzen, machen Sie ein Update.

Weitere Informationen finden Sie unter :ref:`installation:Minor Update installieren`.

.. todo: reaktivieren in 2.5.1
    * :ref:`installation:Patch-Update installieren`
