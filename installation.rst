Installation
============

Um das Zahlungsmodul :productname:`PayPal Checkout` zu installieren, folgen Sie verschiedene Verfahren, um entweder OXID eShop Version 6.1 oder OXID eShop Version 6.2 und höher zu unterstützen.

Frühere Versionen des OXID eShops werden nicht unterstützt.


PayPal Checkout für OXID eShop ab Version 6.2 installieren
----------------------------------------------------------

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
      composer require oxid-solution-catalysts/paypal-module ^2.0.0
      composer install
      ./vendor/bin/oe-console oe:module:install-configuration source/modules/osc/paypal
      ./vendor/bin/oe-console oe:module:apply-configuration

#. Optional: Um das Modul zu aktivieren, führen Sie folgenden Befehl aus.
   |br|
   Alternativ: Aktivieren Sie das Modul im Zuge der Konfiguration manuell (siehe :ref:`konfiguration:PayPal Checkout aktivieren`).

   .. code:: bash

      ./vendor/bin/oe-console oe:module:activate osc_paypal


|result|

Sobald der Installationsprozess abgeschlossen ist, erscheint das Modul :guilabel:`PayPal Checkout für OXID` im Administrationsbereich unter :menuselection:`Erweiterungen --> Module` (:ref:`oxdajq01`).

.. _oxdajq01:

.. figure:: /media/screenshots/oxdajq01.png
   :alt: PayPal Checkout für OXID erfolgreich installiert

   Abb.: PayPal Checkout für OXID erfolgreich installiert



Nächster Schritt: Um :productname:`PayPal Checkout` zu konfigurieren, wählen Sie :guilabel:`Weiter`.



PayPal Checkout für OXID eShop Version 6.1 installieren
-------------------------------------------------------

Um :productname:`PayPal Checkout` für den OXID eShop Version 6.1 zu installieren, installieren Sie :productname:`PayPal Checkout` V. 1.0.

|procedure|

Folgen Sie analog dem Vorgehen für die Installation für den OXID eShop ab Version 6.2 (siehe :ref:`installation:PayPal Checkout für OXID eShop ab Version 6.2 installieren`).

Führen Sie dabei die Befehle wie folgt aus:

   .. code:: bash

      composer config repositories.oscpaypal composer https://paypal-module.packages.oxid-esales.com/
      composer require oxid-solution-catalysts/paypal-module ^1.0.0
      composer install

.. Intern: oxdajq, Status: