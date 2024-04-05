PayPal Checkout V. 3.4
======================

Release-Datum: 17.11.2023

:productname:`PayPal Checkout` 3.4 ist für :productname:`OXID eShop` Version 7.

Neue oder geänderte Funktionen
------------------------------

Mit :productname:`PayPal Checkout` 3.4 für :productname:`OXID eShop` Version 7 und 2.4 für :productname:`OXID eShop` Version 6.# bis 6.5 greifen folgende Änderungen.

PayPal Vaulting
^^^^^^^^^^^^^^^

.. todo: #ML: prüfen/verifizieren: siehe https://developer.paypal.com/braintree/docs/guides/paypal/checkout-with-vault/javascript/v3/

Ermöglichen Sie mit PayPal Vaulting wiederkehrenden Kunden einen nahtlosen Checkout-Prozess und erhöhen Sie so Ihre Konversionsrate.

**Hintergrund**

PayPal Vaulting bedeutet: Ihre Kunden speichern ihre Zahlungsinformationen sicher im Braintree-Tresor, um sie für zukünftige Transaktionen wiederzuverwenden.

PayPal Vaulting erstellt dazu automatisch eine PayPal-Abrechnungsvereinbarung. Dadurch können Sie das Konto in Zukunft belasten, ohne dass der Kunde sich erneut bei PayPal authentifizieren oder eine Zahlungsmethode aus seinem Wallet auswählen muss.

Hauptvorteile und Nutzungsmöglichkeiten:

* Speicherung für zukünftige Käufe: Kunden müssen ihre Zahlungsinformationen nicht bei jedem Kauf neu eingeben, was die Kaufabwicklung beschleunigt und die Benutzerfreundlichkeit erhöht.
* Vielseitigkeit: Unterstützt die Auswahl oder Hinzufügung von Versandadressen und Finanzierungsinstrumenten im PayPal-Konto, sowie Zwei-Faktor-Authentifizierung in mehreren Ländern.
* Verbesserte Kundenerfahrung bei Rückkehr: Kunden, die ihr PayPal Wallet im Tresor gespeichert haben, können bei zukünftigen Käufen schneller bezahlen und, falls gewünscht, ihre Zahlungsmethode ändern.

PayPal Vaulting nachträglich aktivieren
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Wenn Sie :productname:`PayPal Checkout` bereits nutzen, tun Sie folgendes, um PayPal Vaulting nachträglich zu aktivieren.

|procedure|

1. Machen Sie ein Update auf :productname:`PayPal Checkout` 3.4.0.

   Weitere Informationen finden Sie unter :ref:`installation:Minor Update installieren`.

#. Durchlaufen Sie den Registrierungs-Prozess (Onboarding) erneut.

   Wenn technisch alles in Ordnung ist, wird unter :guilabel:`Freischaltung für besondere Zahlarten erfolgt` angezeigt, dass PayPal Vaulting verfügbar ist (:ref:`oxdajr05`, Pos. 4)

   Weitere Informationen finden Sie unter :ref:`konfiguration:API-Anmeldeinformationen`.

|result|

PayPal Vaulting ist standardmäßig aktiviert (:ref:`oxdajr14`, Pos. 1).

Sie können es bei Bedarf deaktivieren. Weitere Informationen finden Sie unter :ref:`konfiguration:PayPal Vaulting deaktivieren`.


Geänderte Zahlungsarten
^^^^^^^^^^^^^^^^^^^^^^^

Folgende Zahlungsarten unterstützt :productname:`PayPal Checkout` 2.4/3.4 :emphasis:`nicht` mehr:

* Sofort
* MyBank

Weitere Informationen über unterstützte Zahlungsarten finden Sie unter :ref:`einfuehrung:Zahlungsarten in PayPal Checkout`.

Installation
------------

Um :productname:`PayPal Checkout` V. 3.3 zu nutzen, installieren Sie es in Ihrem OXID eShop 7.x.

Weitere Informationen finden Sie unter :ref:`installation:Installation`.

.. todo: für spätere Verwendung:
    Update
    ------
    Um die Funktionen und Korrekturen von :productname:`PayPal Checkout` V. 2.3 zu nutzen, machen Sie ein Update.
    Weitere Informationen finden Sie unter
    * :ref:`installation:Minor Update installieren`
    * :ref:`installation:Patch-Update installieren`
