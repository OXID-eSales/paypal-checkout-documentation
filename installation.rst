Installation
============

Um das Zahlungsmodul :productname:`PayPal Checkout` zu installieren, folgen Sie verschiedenen Verfahren je nach der Version Ihres OXID eShops:

* Wenn Sie OXID eShop Version 6.1.x oder 6.2.x haben, installieren Sie :productname:`PayPal Checkout` 1.2 wie im Folgenden beschrieben.
* Wenn Sie OXID eShop Version 6.3.x oder höher haben, installieren Sie `PayPal Checkout 2.2 <https://docs.oxid-esales.com/modules/paypal-checkout/de/2.2/>`_.


Frühere Versionen des OXID eShops werden nicht unterstützt.

Führen Sie die gleichen Composer-Befehle aus, um ein Patch-Update von :productname:`PayPal Checkout` zu installieren


PayPal Checkout für OXID eShop Version 6.1.x oder 6.2.x installieren
--------------------------------------------------------------------

Installieren Sie :productname:`PayPal Checkout` V. 1.2.

|prerequisites|

* Sie haben den OXID eShop 6.1.x oder 6.2.x installiert.
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
      composer require oxid-solution-catalysts/paypal-module ^1.2.0

   Sobald der Installationsprozess abgeschlossen ist, erscheint das Modul :guilabel:`PayPal Checkout für OXID` im Administrationsbereich unter :menuselection:`Erweiterungen --> Module` (:ref:`oxdajq01`).

   .. _oxdajq01:

   .. figure:: /media/screenshots/oxdajq01.png
      :alt: PayPal Checkout für OXID erfolgreich installiert

      Abb.: PayPal Checkout für OXID erfolgreich installiert

#. Aktivieren Sie das Modul.

Nächster Schritt: Um :productname:`PayPal Checkout` zu konfigurieren, wählen Sie :guilabel:`Weiter`.


Minor Update installieren
-------------------------

Installieren Sie bei Bedarf ein  Minor Update, beispielsweise von :productname:`PayPal Checkout` Version 1.1.4 auf Version 1.2.0.

   .. code:: bash

      composer require oxid-solution-catalysts/paypal-module ^1.2.0



Patch-Update installieren
-------------------------

Installieren Sie bei Bedarf ein Patch-Update, beispielsweise von :productname:`PayPal Checkout` Version 1.2.2 auf Version 1.2.3.


|procedure|

1. Führen Sie folgenden Befehl aus:

   .. code:: bash

      composer update

#. Bestätigen Sie die Abfrage, ob die :file:`oxid-solution-catalysts/paypal-module`-Dateien überschrieben werden sollen.





.. Intern: oxdajq, Status:
