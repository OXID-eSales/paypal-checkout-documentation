Installation
============

Um das Zahlungsmodul :productname:`PayPal Checkout` zu installieren, installieren Sie verschiedene Versionen je nach der Version Ihres OXID eShops:

* Wenn Sie OXID eShop Version 7.x haben, installieren Sie :productname:`PayPal Checkout` 3.3.x (siehe :ref:`installation:PayPal Checkout installieren`).

  .. important::

     **Einschränkung**

     :productname:`PayPal Checkout` 3.3.x unterstützt nur Twig-Themes (beispielsweise APEX).

     Installieren Sie :productname:`PayPal Checkout` 3.3.x nicht, wenn Sie Smarty einsetzen.

* Wenn Sie OXID eShop Version 6.3.x bis 6.5.x haben, installieren Sie :productname:`PayPal Checkout` 2.3.x.
  |br|
  Weitere Informationen finden Sie in der zugehörigen Modul-Documentation unter `PayPal Checkout 2.3.x installieren <https://docs.oxid-esales.com/modules/paypal-checkout/de/2.3/installation.html>`_.
* Wenn Sie OXID eShop Version 6.1.x oder 6.2.x haben, installieren Sie :productname:`PayPal Checkout` 1.3.x.
  |br|
  Weitere Informationen finden Sie in der zugehörigen Modul-Documentation unter `PayPal Checkout 1.3.x installieren <https://docs.oxid-esales.com/modules/paypal-checkout/de/1.3/installation.html>`_.

Frühere Versionen des OXID eShops werden nicht unterstützt.

PayPal Checkout installieren
----------------------------

Installieren Sie für den OXID eShop Version 7.x das Zahlungsmodul :productname:`PayPal Checkout`

|prerequisites|

* Sie haben die OXID eShop-Version 7.x installiert.
* Sie verwenden ein Twig Theme.
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
      composer require oxid-solution-catalysts/paypal-module ^3.3.0

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


.. todo: Folgende Varianten später reaktivieren
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






.. Intern: oxdajq, Status:
