PayPal Checkout V. 2.4
======================

Release-Datum: 04.04.2024

Neue oder geänderte Funktionen
------------------------------

Wir haben

* die Funktion PayPal Vaulting hinzugefügt
* die Zahlungsarten Sofort und MyBank entfernt

PayPal Vaulting
^^^^^^^^^^^^^^^

Ermöglichen Sie mit PayPal Vaulting wiederkehrenden Kunden einen nahtlosen Checkout-Prozess und erhöhen Sie so Ihre Konversionsrate.

**Hintergrund**

PayPal Vaulting bedeutet: Ihre Kunden speichern ihre Zahlungsinformationen sicher im Braintree-Tresor, um sie für zukünftige Transaktionen wiederzuverwenden.

PayPal Vaulting erstellt dazu automatisch eine PayPal-Abrechnungsvereinbarung. Dadurch können Sie das Konto in Zukunft belasten, ohne dass der Kunde sich erneut bei PayPal authentifizieren oder eine Zahlungsmethode aus seinem Wallet auswählen muss.

Hauptvorteile und Nutzungsmöglichkeiten:

* Speicherung für zukünftige Käufe: Kunden müssen ihre Zahlungsinformationen nicht bei jedem Kauf neu eingeben, was die Kaufabwicklung beschleunigt und die Benutzerfreundlichkeit erhöht.
* Vielseitigkeit: Unterstützt die Auswahl oder Hinzufügung von Versandadressen und Zahlungsarten im PayPal-Konto, sowie Zwei-Faktor-Authentifizierung in mehreren Ländern.
* Verbesserte Kundenerfahrung bei Rückkehr: Kunden, die ihr PayPal Wallet im Tresor gespeichert haben, können bei zukünftigen Käufen schneller bezahlen und, falls gewünscht, ihre Zahlungsmethode ändern.

Weitere Informationen zu PayPal Vaulting finden Sie unter :ref:`konfiguration:Konfiguration` im Abschnitt :ref:`konfiguration:PayPal Vaulting verwenden`.

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

Deaktivieren Sie es bei Bedarf. Weitere Informationen finden Sie unter :ref:`konfiguration:PayPal Vaulting verwenden`.


Geänderte Zahlungsarten
^^^^^^^^^^^^^^^^^^^^^^^

Folgende Zahlungsarten unterstützt :productname:`PayPal Checkout` 2.4 :emphasis:`nicht` mehr:

* Sofort
* MyBank

Weitere Informationen über unterstützte Zahlungsarten finden Sie unter :ref:`einfuehrung:Zahlungsarten in PayPal Checkout`.

Installation
------------

Um :productname:`PayPal Checkout` V. 2.4 zu nutzen, installieren Sie es in Ihrem :productname:`OXID eShop` 6.3.x to 6.5.x.

Weitere Informationen finden Sie unter :ref:`installation:Installation`.

Update
------

Um die Funktionen und Korrekturen von :productname:`PayPal Checkout` V. 2.4 zu nutzen, machen Sie ein Update.

Weitere Informationen finden Sie unter

* :ref:`installation:Minor Update installieren`

.. todo: Mit 241 reaktivieren: * :ref:`installation:Patch-Update installieren`
