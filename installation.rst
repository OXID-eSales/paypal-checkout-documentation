Installation
============

Um das Zahlungsmodul :productname:`PayPal Checkout` zu installieren, installieren Sie verschiedene Versionen je nach der Version Ihres OXID eShops:

* Wenn Sie OXID eShop Version 7.x haben, installieren Sie :productname:`PayPal Checkout` 3.5.x (siehe :ref:`installation:PayPal Checkout installieren`).

* Wenn Sie OXID eShop Version 6.3.x bis 6.5.x haben, installieren Sie :productname:`PayPal Checkout` 2.x.x.
  |br|
  Weitere Informationen finden Sie in der zugehörigen Modul-Documentation unter `PayPal Checkout 2.6.x installieren <https://docs.oxid-esales.com/modules/paypal-checkout/de/2.6/installation.html>`_.
* Wenn Sie OXID eShop Version 6.1.x oder 6.2.x haben, installieren Sie :productname:`PayPal Checkout` 1.x.x.
  |br|
  Weitere Informationen finden Sie in der zugehörigen Modul-Dokumentation unter `PayPal Checkout 1.3.x installieren <https://docs.oxid-esales.com/modules/paypal-checkout/de/1.3/installation.html>`_.

Frühere Versionen des OXID eShops werden nicht unterstützt.

PayPal Checkout installieren
----------------------------

Installieren Sie für den OXID eShop Version 7.x das Zahlungsmodul :productname:`PayPal Checkout`

|prerequisites|

* Sie haben die OXID eShop-Version 7.x installiert.
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

#. Führen Sie folgenden Befehl aus:

   .. code:: bash

      composer require oxid-solution-catalysts/paypal-module ^3.5.0

#. Optional: Um das Modul zu aktivieren, führen Sie folgenden Befehl aus.
   |br|
   Alternativ: Aktivieren Sie das Modul im Zuge der Konfiguration manuell (siehe :ref:`konfiguration:PayPal Checkout manuell aktivieren`).

   .. code:: bash

      ./vendor/bin/oe-console oe:module:activate osc_paypal


|result|

Sobald der Installationsprozess abgeschlossen ist, erscheint das Modul :guilabel:`PayPal Checkout für OXID` im Administrationsbereich unter :menuselection:`Erweiterungen --> Module` (:ref:`oxdajq01`).

.. _oxdajq01:

.. figure:: /media/screenshots/oxdajq01.png
   :alt: PayPal Checkout für OXID installiert und aktiviert
   :width: 650
   :class: with-shadow

   Abb.: PayPal Checkout für OXID installiert und aktiviert

Minor Update installieren
-------------------------

Installieren Sie bei Bedarf ein Minor Update, beispielsweise von :productname:`PayPal Checkout` Version 3.4.0 auf Version 3.5.0.

|procedure|

1. Deaktivieren Sie das Modul.
#. Führen Sie folgenden Konsolen-Befehl aus:

   .. code:: bash

      composer require oxid-solution-catalysts/paypal-module ^3.5.0 -W --with-all-dependencies
      composer update

#. Aktivieren Sie das Modul.
#. Um neue Zahlungsarten oder Funktionen nutzen zu können, durchlaufen Sie den Registrierungsprozess (Onboarding) neu.

   Weitere Informationen finden Sie unter :ref:`konfiguration:API-Anmeldeinformationen: Onboarding`.

.. todo: reaktivieren für 2.5.1
    Patch-Update installieren
    -------------------------
    Installieren Sie bei Bedarf ein Patch-Update, beispielsweise von :productname:`PayPal Checkout` Version 2.4.0 auf Version 2.4.1.
    |procedure|
    1. Führen Sie folgenden Befehl aus:
       .. code:: bash
          composer update
    #. Bestätigen Sie die Abfrage, ob die :file:`oxid-solution-catalysts/paypal-module`-Dateien überschrieben werden sollen.
    #. Um neue Zahlungsarten oder Funktionen nutzen zu können, durchlaufen Sie den Registrierungsprozess (Onboarding) neu.
       Weitere Informationen finden Sie unter :ref:`konfiguration:API-Anmeldeinformationen: Onboarding`.

.. Intern: oxdajq, Status:
