Installation
============

Installieren Sie das Zahlungsmodul PayPal Checkout für den OXID eShop ab Version 6.2.


.. include:: /_static/reuse/paypal-checkout-migration.rst


|prerequisites|

* Sie haben den OXID eShop 6.2 oder höher installiert.
* Sie haben Transportverschlüsselung (`https`) konfiguriert.

   a. Öffnen Sie im Verzeichnis :file:`<Rootverzeichnis des eShops>/source` die Datei :file:`config.inc.php`.
   b. Stellen Sie sicher, dass für die eShop base URL (Parameter `sShopURL`) https eingestellt ist.
      |br|
      Beispiel:

      .. code::

         $this->sShopURL     = 'https://192.168.123.20';

|procedure|

1. Öffnen Sie eine Shell und wechseln Sie ins Root-Verzeichnis des eShops (in dem die Datei :file:`composer.json` liegt).
   |br|
   Beispiel:

   .. code:: bash

      cd /var/www/oxideshop

2. Führen Sie folgenden Befehl aus:

   .. code:: bash

      composer require --update-no-dev oxid-solution-catalysts/paypal-module


3. Bestätigen Sie die Abfragen.

|result|

Sobald der Installationsprozess abgeschlossen ist, erscheint das Modul :guilabel:`OSC :: PayPal - Online-Bezahldienst` im Administrationsbereich unter :menuselection:`Erweiterungen --> Module`.


.. todo: #tbd Bild ergänzen

.. todo: Nächster Schritt Konfiguration





.. Intern: oxdaab, Status: