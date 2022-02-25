Installation
============

Installieren Sie das Zahlungsmodul PayPal Checkout für den OXID eShop ab Version 6.3.

.. todo:
   #Mario: klärt:
   6.2. kommt wahrcheinlich
   6.1 fraglich


.. todo: Altes Paypal-Modul: Theoretisch kann man beide Versionen konfiguriert haben.: An Stichtag umstellen; Empfehling Testsystem, Sandbox, A/B-Vergleich: z.B. bei Geschftskunden, die immergleiche Optik erwarten  (Vorgehen 12'03)
.. todo: #Mario: Ist das für den Übergang korekt?: Oder eine andere Empfehlug?

.. ATTENTION::

   **Keine Migration von PayPal zu PayPal Checkout möglich**

   Sie können Bestellungen nicht vom Modul PayPal zum Modul PayPal Checkout migrieren.

   Empfehlung: Warten Sie mit dem Umstieg zu Paypal Checkout, bis eine Version vorliegt, die Ihre Bestellungen migriert.

   Nicht empfohlen: Wenn Sie von PayPal zum Modul PayPal Checkout bereits jetzt umsteigen wollen, tun Sie Folgendes:

      1. Testen Sie PayPal Checkout in einem Testsystem.
      2. Stellen Sie auf PayPal Checkout um, wenn Sie sicher sind, dass es keine offenen PayPal-Bestellungen mehr gibt.


Modul installieren
------------------

|prerequisites|

* Sie haben den OXID eShop 6.3 oder höher installiert.
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

Sobald der Installationsprozess abgeschlossen ist, erscheint das Modul im Administrationsbereich unter :menuselection:`Erweiterungen --> Zahlungsarten`.


.. todo: #tbd Bild ergänzen

.. todo: Nächster Schritt Konfiguration



Installation abschließen
------------------------

.. todo: #Mario: /modules/oe/oepaypal/logs gibt es offenbar nicht für PayPal checkout; Schritt überflüssig?

1. Setzen Sie die Berechtigung für das Logging.
   |br|
   Ändern Sie dazu die Schreibrechte von :file:`/modules/oe/oepaypal/logs`. Geben Sie volle Schreibrechte für Besitzer und Gruppe (755 oder 777).
   |br|
   Beispiel:

   .. code:: bash

      chmod 777 /modules/oe/oepaypal/logs


2. Löschen Sie temporäre Dateien.
   |br|
   Löschen Sie dazu alle Dateien und Ordner außer :file:`.htaccess` aus dem Verzeichnis :file:`/tmp` des Shops.


.. Intern: oxdaab, Status: