PayPal Checkout V. 2.3
======================

.. todo: #ML: wann ist Release?

Release-Datum: 30.05.2023

Neue oder geänderte Funktionen
------------------------------

.. todo: https://github.com/OXID-eSales/paypal-module/blob/v2.3.0-rc.3/CHANGELOG.md

* Bieten Sie Ihren Kunden für Überweisungen in Deutschland die neue Zahlungsart SEPA an.

  Im Checkout

  .. todo: #tbd: Ref. auf PP-URL

* Wenn Sie Ihren Kunden bisher keine Zahlung per Kreditkarte anbieten konnten, nutzen Sie die Fallback-Lösung von PayPal.

  Weitere Informatinen finden Sie unter :ref:`Freischaltung für besondere Zahlarten prüfen <freischaltung-kreditkarte>`.

* Machen Sie sich bei einem Minor Update beispielsweise von PayPal Checkout V. 2.2 auf V. 2.3 keine Sorgen um die Konfiguration Ihrer Zahlungsarten: Ihre Konfiguration bleibt erhalten, Sie müssen Zahlungsarten nach einem Update nicht neu konfigurieren..

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

.. todo: #tbd:
        done: für OXID >=6.3 und OXID <=6.5 lautet die Version: v2.3.0-rc.3
        für OXID >=6.1 und OXID <=6.2 lautet die Version: v1.3.0-rc.3

* Sie haben OXID eShop V. 6.3.x bis 6.5.x.

Vorgehen
^^^^^^^^

.. todo: #tbd: verifizieren: stimmt

Führen Sie den folgenden Befehl aus.

.. code:: bash

   composer update
