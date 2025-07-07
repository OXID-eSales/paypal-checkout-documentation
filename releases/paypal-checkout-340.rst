PayPal Checkout V. 3.4
======================

Release-Datum: `06.02.2025 <https://github.com/OXID-eSales/paypal-module/blob/v3.4.0/CHANGELOG.md#340---2025-02-06>`_

Neue oder geänderte Funktionen
------------------------------

Wir haben

* die Zahlungsarten Google Pay und Apple Pay hinzugefügt: :ref:`releases/paypal-checkout-340:Apple Pay und Google Pay`
* die Funktion PayPal Vaulting hinzugefügt: :ref:`releases/paypal-checkout-340:PayPal Vaulting`
* die Zahlungsarten Sofort und MyBank entfernt: :ref:`releases/paypal-checkout-340:Geänderte Zahlungsarten`
* das Konfigurieren von Pseudoversandkosten für PayPal Express ergänzt: :ref:`releases/paypal-checkout-340:Konfigurieren von Pseudoversandkosten für PayPal Express`

Apple Pay und Google Pay
------------------------

Ermöglichen Sie mit Apple Pay und Google Pay Zahlungsvorgänge weltweit und in 25 Währungen.

Weitere Informationen zur Abdeckung finden Sie unter

* :ref:`einfuehrung:Marktabdeckung nach Zahlungsmethoden`
* :ref:`einfuehrung:Währungsabdeckung nach Zahlungsmethode`

|procedure|

1. Installieren Sie :productname:`PayPal Checkout` neu oder machen Sie ein Update.
#. Durchlaufen Sie den Registrierungsprozess (Onboarding) erneut (auch bei einem Update).

   Weitere Informationen finden Sie unter :ref:`konfiguration:API-Anmeldeinformationen: Onboarding`.

#. Verifizieren Sie, dass die Freischaltung für die Zahlungsarten Apple Pay und Google Pay erfolgt ist (:ref:`oxdajr05rn`, Pos. 5).

   .. _oxdajr05rn:

   .. figure:: /media/screenshots/oxdajr05.png
      :alt: Client-ID/Passwort und Webhook-ID erzeugt
      :width: 650
      :class: with-shadow

      Abb.: Client-ID/Passwort und Webhook-ID erzeugt

   Wenn keine Freischaltung erfolgt ist, kontaktieren Sie den PayPal-Support.

#. Aktivieren Sie Apple Pay mit Ihrem Sandbox-Konto.

   Weitere Informationen finden Sie unter :ref:`konfiguration:Apple Pay als Zahlungsart aktivieren`.

   Google Pay ist standardmäßig aktiviert. Sie brauchen nur ein Google-Konto und eine Kreditkarte.

#. Konfigurieren Sie die Länderzuordnung von Apple Pay und Google Pay.

   Weitere Informationen finden Sie unter :ref:`konfiguration:Optional: Länderzuordnung von PayPal Checkout-Zahlungsmethoden konfigurieren`.

#. Um die Zahlungsart Apple Pay und Google Pay zu konfigurieren, wählen Sie

   * :menuselection:`Shopeinstellungen --> Zahlungsarten --> GooglePay`.
   * :menuselection:`Shopeinstellungen --> Zahlungsarten --> ApplePay`.

#. Schalten Sie Apple Pay und Google Pay nach dem Testen für den Live-Betrieb frei.

   Weitere Informationen finden Sie unter

   * Apple Pay: `Go live <https://developer.paypal.com/docs/checkout/apm/apple-pay/#link-golive>`_
   * :ref:`konfiguration:PayPal Checkout freischalten`.

PayPal Vaulting
---------------

Ermöglichen Sie mit PayPal Vaulting wiederkehrenden Kunden einen nahtlosen Checkout-Prozess und erhöhen Sie so Ihre Konversionsrate.

Hintergrund
^^^^^^^^^^^

PayPal Vaulting bedeutet: Ihre Kunden speichern ihre Zahlungsinformationen sicher im Braintree-Tresor, um sie für zukünftige Transaktionen wiederzuverwenden.

PayPal Vaulting erstellt dazu automatisch eine PayPal-Abrechnungsvereinbarung. Dadurch können Sie das Konto in Zukunft belasten, ohne dass der Kunde sich erneut bei PayPal authentifizieren oder eine Zahlungsmethode aus seinem Wallet auswählen muss.

Hauptvorteile und Nutzungsmöglichkeiten:

* Speicherung für zukünftige Käufe: Kunden müssen ihre Zahlungsinformationen nicht bei jedem Kauf neu eingeben, was die Kaufabwicklung beschleunigt und die Benutzerfreundlichkeit erhöht.
* Vielseitigkeit: Unterstützt die Auswahl oder Hinzufügung von Versandadressen und Zahlungsarten im PayPal-Konto, sowie Zwei-Faktor-Authentifizierung in mehreren Ländern.
* Verbesserte Kundenerfahrung bei Rückkehr: Kunden, die ihr PayPal Wallet im Tresor gespeichert haben, können bei zukünftigen Käufen schneller bezahlen und, falls gewünscht, ihre Zahlungsmethode ändern.

Weitere Informationen zu PayPal Vaulting finden Sie unter :ref:`konfiguration:Konfiguration` im Abschnitt :ref:`konfiguration:PayPal Vaulting deaktivieren`.

PayPal Vaulting nachträglich aktivieren
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Wenn Sie :productname:`PayPal Checkout` bereits nutzen, aktivieren Sie PayPal Vaulting nachträglich:

|procedure|

1. Aktualisieren Sie auf :productname:`PayPal Checkout` 2.4.0.

   Weitere Informationen finden Sie unter :ref:`installation:Minor Update installieren`.

#. Durchlaufen Sie den Registrierungs-Prozess (Onboarding) erneut.

   Nach erfolgreicher technischer Überprüfung wird die Verfügbarkeit von PayPal Vaulting im Bereich :guilabel:`Freischaltung für besondere Zahlarten erfolgt` bestätigt (:ref:`oxdajr05`, Pos. 4).

   Weitere Informationen zum Durchlaufen Sie den Registrierungs-Prozesses (Onboarding) finden Sie unter :ref:`konfiguration:API-Anmeldeinformationen: Onboarding`.

|result|

PayPal Vaulting ist standardmäßig aktiviert (:ref:`oxdajr14`, Pos. 1).

Deaktivieren Sie es bei Bedarf. Weitere Informationen finden Sie unter :ref:`konfiguration:PayPal Vaulting deaktivieren`.


Geänderte Zahlungsarten
-----------------------

Folgende Zahlungsarten unterstützt :productname:`PayPal Checkout` 2.4 :emphasis:`nicht` mehr:

* Sofort
* MyBank

Weitere Informationen über unterstützte Zahlungsarten finden Sie unter :ref:`einfuehrung:Zahlungsarten in PayPal Checkout`.

Konfigurieren von Pseudoversandkosten für PayPal Express
--------------------------------------------------------

Um Zahlungen mit PayPal Express zu ermöglichen, stellen Sie durch sogenannte Pseudoversandkosten sicher, dass der Wert des Warenkorbs ungefähr dem Wert entspricht, der beim Checkout vom PayPal-Konto des Kunden eingezogen wird.

Weitere Informationen finden Sie unter :ref:`konfiguration:Pseudoversandkosten für PayPal Express anpassen`.

Installation
------------

Um :productname:`PayPal Checkout` V. 3.4 zu nutzen, installieren Sie es in Ihrem OXID eShop 7.x.

Weitere Informationen finden Sie unter :ref:`installation:Installation`.


Update
------

Um die Funktionen und Korrekturen von :productname:`PayPal Checkout` V. 3.4 zu nutzen, machen Sie ein Update.
Weitere Informationen finden Sie unter :ref:`installation:Minor Update installieren`.

.. todo: für spätere Verwendung:
    * :ref:`installation:Patch-Update installieren`
