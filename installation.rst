Installation
============

Installieren Sie das Zahlungsmodul :productname:`PayPal Checkout` für den OXID eShop ab Version 6.2.



|prerequisites|

* Sie haben den OXID eShop 6.2 oder höher installiert.
* Sie haben `https` konfiguriert.

   a. Öffnen Sie im Verzeichnis :file:`<Rootverzeichnis des eShops>/source` die Datei :file:`config.inc.php`.
   b. Stellen Sie sicher, dass für die Basis-URL (Parameter :technicalname:`sShopURL`) `https` eingestellt ist.
      |br|
      Beispiel:

      .. code::

         $this->sShopURL     = 'https://www.example.org';

|procedure|

1. Öffnen Sie eine Shell und wechseln Sie ins Root-Verzeichnis des eShops (in dem die Datei :file:`composer.json` liegt).
   |br|
   Beispiel:

   .. code:: bash

      cd /var/www/oxideshop

#. Führen Sie folgende Befehle aus:

   .. code:: bash

      composer config repositories.oscpaypal composer https://paypal-module.packages.oxid-esales.com/
      composer require oxid-solution-catalysts/paypal-module ^1.0.0
      composer install
      ./vendor/bin/oe-console oe:module:install-configuration source/modules/osc/paypal
      ./vendor/bin/oe-console oe:module:apply-configuration

#. Optional: Um das Modul zu aktivieren, führen Sie folgenden Befehl aus.
   |br|
   Alternativ: Aktivieren Sie das Modul im Zuge der Konfiguration manuell (siehe :ref:`konfiguration:PayPal Checkout aktivieren`).
   |br|
   Das ist beispielsweise sinnvoll, wenn Sie bereits das Modul :productname:`PayPal` oder :productname:`PayPal Plus` nutzen.
   |br|
   In diesem Fall wollen Sie sicherstellen, dass die Module nur während einer Downtime zum Migrieren der Altdaten gleichzeitig aktiv sind.

   .. code:: bash

      ./vendor/bin/oe-console oe:module:activate osc_paypal

#. Bestätigen Sie die Abfragen.

|result|

Sobald der Installationsprozess abgeschlossen ist, erscheint das Modul :guilabel:`PayPal Checkout für OXID` im Administrationsbereich unter :menuselection:`Erweiterungen --> Module`.


.. todo: #tbd Bild ergänzen


Nächster Schritt: Um :productname:`PayPal Checkout` zu konfigurieren, wählen Sie :guilabel:`Weiter`.



.. Intern: oxdajq, Status: