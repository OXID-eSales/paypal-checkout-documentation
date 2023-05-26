PayPal Checkout V. 2.3
======================

.. todo: #tbd: ReleaseDatum 2.3: 24.05.2023; 1.3: tbd

Release-Datum: 24.05.2023

Neue oder geänderte Funktionen
------------------------------

.. todo: https://github.com/OXID-eSales/paypal-module/blob/v2.3.0/CHANGELOG.md
.. todo: ML: Folgendes nicht doku-relevant: improved tests and static code analysis
.. todo: #ML: Folgendes prüfen:

* Bieten Sie Ihren Kunden für Überweisungen in Deutschland die neue Zahlungsart SEPA an.

  Für den Checkout-Schritt Versand & Zahlungsart können Sie damit die entsprechende Schaltfläche SEPA-Lastschrift konfigurieren (:ref:`oxdajr02`, Pos. 3)

* Wenn Sie Ihren Kunden bisher keine Zahlung per Kreditkarte anbieten konnten, nutzen Sie die Fallback-Lösung von PayPal.

  Weitere Informationen finden Sie unter :ref:`Freischaltung für besondere Zahlarten prüfen <freischaltung-kreditkarte>`.

* Weisen Sie durch Senden eines Tracking-Codes nach, dass Sie bestellte Waren abgesendet haben.

  Der Tracking-Code macht es PayPal im Fall von Auseinandersetzungen mit Kunden leichter, Ihren Schaden zu regulieren.

  Weitere Informationen finden Sie unter :ref:`betrieb:Artikel als versendet markieren`.

* Machen Sie sich bei einem Minor Update beispielsweise von PayPal Checkout V. 2.2 auf V. 2.3 keine Sorgen um die Konfiguration Ihrer Zahlungsarten: Ihre Konfiguration bleibt erhalten, Sie müssen Zahlungsarten nach einem Update nicht neu konfigurieren.

* Löschen Sie Bestellungen, die nicht abgeschlossen wurden, entweder automatisch oder manuell.

  Weitere Informationen finden Sie unter :ref:`konfiguration:Behandlung nicht beendeter Bestellungen festlegen`.

Korrekturen
-----------

Korrekturen finden Sie im Changelog (GitHub) unter https://github.com/OXID-eSales/paypal-module/blob/v2.3.0/CHANGELOG.md.


Update
------

Um die Funktionen und Korrekturen von :productname:`PayPal Checkout` V. 2.3 zu nutzen, machen Sie ein Update.

Voraussetzungen
^^^^^^^^^^^^^^^

.. todo: #tbd: x.3
        done: für OXID >=6.3 und OXID <=6.5 lautet die Version: v2.3.0
        für OXID >=6.1 und OXID <=6.2 lautet die Version: v1.3.0

* Sie haben OXID eShop V. 6.3.x bis 6.5.x.

Vorgehen
^^^^^^^^

Führen Sie den folgenden Befehl aus.

.. code:: bash

   composer update
