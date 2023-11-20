Installation
============

Um das Zahlungsmodul :productname:`PayPal Checkout` zu installieren, installieren Sie verschiedene Versionen je nach der Version Ihres OXID eShops:

* Wenn Sie OXID eShop Version 6.3.x bis 6.5.x haben, installieren Sie :productname:`PayPal Checkout` 2.3.x (siehe :ref:`installation:PayPal Checkout installieren`).
* Wenn Sie OXID eShop Version 7.x haben, installieren Sie :productname:`PayPal Checkout` 3.3.x.
  |br|
  Weitere Informationen finden Sie in der zugehörigen Modul-Documentation unter `PayPal Checkout 3.3.x installieren <https://docs.oxid-esales.com/modules/paypal-checkout/de/3.3/installation.html>`_.
* Wenn Sie OXID eShop Version 6.1.x oder 6.2.x haben, installieren Sie :productname:`PayPal Checkout` 1.3.x.
  |br|
  Weitere Informationen finden Sie in der zugehörigen Modul-Documentation unter `PayPal Checkout 1.3.x installieren <https://docs.oxid-esales.com/modules/paypal-checkout/de/1.3/installation.html>`_.



Frühere Versionen des OXID eShops werden nicht unterstützt.

PayPal Checkout installieren
----------------------------

Installieren Sie für den OXID eShop ab Version 6.3. das Zahlungsmodul :productname:`PayPal Checkout` Version 2.3.x.

|prerequisites|

* Sie haben die OXID eShop-Version 6.3.x bis 6.5.x installiert.
* Sie haben `https` konfiguriert.

   a. Öffnen Sie im Verzeichnis :file:`<Rootverzeichnis des eShops>/source` die Datei :file:`config.inc.php`.
   b. Stellen Sie sicher, dass für die Basis-URL (Parameter :technicalname:`sShopURL`) `https` eingestellt ist.
      |br|
      Beispiel:

      .. code::

         $this->sShopURL = 'https://www.example.org';

|procedure|

1. Öffnen Sie eine Shell und wechseln Sie ins Root-Verzeichnis des eShops (in dem die Datei :file:`composer.json` liegt).
   |br|
   Beispiel:

   .. code:: bash

      cd /var/www/oxideshop

#. Führen Sie folgende Befehle aus:

   .. code:: bash

      composer config repositories.oscpaypal composer https://paypal-module.packages.oxid-esales.com/
      composer require oxid-solution-catalysts/paypal-module ^2.3.0

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

Minor Update installieren
-------------------------

Installieren Sie bei Bedarf ein  Minor Update, beispielsweise von :productname:`PayPal Checkout` Version 2.2.1 auf Version 2.3.0.

   .. code:: bash

      composer require oxid-solution-catalysts/paypal-module ^2.3.0
      composer update

Patch-Update installieren
-------------------------

Installieren Sie bei Bedarf ein Patch-Update, beispielsweise von :productname:`PayPal Checkout` Version 2.3.0 auf Version 2.3.1.


|procedure|

1. Führen Sie folgenden Befehl aus:

   .. code:: bash

      composer update

#. Bestätigen Sie die Abfrage, ob die :file:`oxid-solution-catalysts/paypal-module`-Dateien überschrieben werden sollen.


.. attention::

   **Länderzuordnungen prüfen nach Update auf PayPal Checkout Version 2.1.5**

   Mit Version 2.1.4 wurde die Länderabdeckung einzelner :productname:`PayPal Checkout`-Zahlungsmethoden erweitert.

   Stellen Sie sicher, dass Sie die erweiterte Länderabdeckung nutzen können.

   Hintergrund: Mit :productname:`PayPal Checkout` Version 2.1.5 sind bei der Erstinstallation die Länder automatisch den Zahlungsarten zugeordnet (siehe :ref:`konfiguration:Optional: Länderzuordnung von PayPal Checkout-Zahlungsmethoden konfigurieren`).

   Dadurch kann es sein, dass Konfigurationseinstellungen Ihrer bestehenden Version die Nutzung neuer Länderzuordnungen blockieren.

   Tun Sie Folgendes:

   1. Wählen Sie :menuselection:`Shopeinstellungen --> Zahlungsarten --> <Zahlungsart> --> Länder --> Länder zuordnen`.
   #. Um die gesamte Länderabdeckung einer Zahlungsart zu nutzen, löschen Sie bestehende Zuordnungen.



.. Intern: oxdajq, Status:
