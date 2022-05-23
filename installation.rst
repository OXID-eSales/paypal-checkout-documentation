Installation
============

Installieren Sie das Zahlungsmodul :productname:`PayPal Checkout` 1.0, wenn Sie OXID eShop Version 6.1 haben.

Wenn Sie OXID eShop Version 6.2 oder höher haben, installieren Sie :productname:`PayPal Checkout` 2.0 oder höher.

|prerequisites|

* Sie haben den OXID eShop 6.1 installiert.
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

#. Bestätigen Sie die Abfragen.

|result|

Sobald der Installationsprozess abgeschlossen ist, erscheint das Modul :guilabel:`PayPal Checkout für OXID` im Administrationsbereich unter :menuselection:`Erweiterungen --> Module`.


.. todo: #tbd Bild ergänzen


Nächster Schritt: Um :productname:`PayPal Checkout` zu konfigurieren, wählen Sie :guilabel:`Weiter`.



.. Intern: oxdajq, Status: