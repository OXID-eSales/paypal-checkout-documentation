Troubleshooting
===============

Zahlungsarten oder Funktionen nicht verfügbar
---------------------------------------------

Es kann sein, dass Zahlungsarten wie Google Pay, Kreditkarte und Rechnungskauf oder eine bestimmte Funktion nicht wie beschrieben zur Verfügung stehen.

Das ist der Fall, wenn Sie zum Generieren eines Webhooks bei PayPal die API-Anmeldeinformationen (beispielsweise aus einer existierenden Version von PayPal Checkout) :emphasis:`manuell` eingegeben haben, statt den Registrierungs-Prozess mit der Schaltfläche :guilabel:`Anmeldung Händler PayPal-Integration` zu starten und neu zu durchlaufen.

|procedure|

Um sicherzustellen, dass alle Zahlungsarten und Funktionen verfügbar sind, tun Sie (am Beispiel eines Sandbox-Kontos) Folgendes:

1. Wählen Sie :menuselection:`PayPal --> Konfiguration`.
#. Löschen Sie unter :guilabel:`API-Anmeldeinformationen` alle Anmeldeinformationen und wählen :guilabel:`Speichern`.
   |br|
   Die Schaltfläche :guilabel:`Anmeldung Händler PayPal-Integration (Sandbox)` erscheint.
#. Wählen Sie :guilabel:`Anmeldung Händler PayPal-Integration (Sandbox)`.
#. Um Zugangsdaten und Webhook neu zu generieren, durchlaufen Sie den Registrierungs-Prozess (Onboarding) mit der E-Mail-Adresse des Sandbox-Händlerkontos.

Weitere Informationen finden Sie im Kapitel :ref:`konfiguration:Konfiguration` unter :ref:`konfiguration:API-Anmeldeinformationen: Onboarding`.

Google Pay funktioniert nicht
-----------------------------

|procedure|

* Prüfen Sie, ob Google Pay aktiv ist.

  Weitere Informationen finden Sie unter :ref:`paypal-sandbox:Google Pay- and Apple Pay-Aktivierung prüfen`.

Debug-Modus einschalten
-----------------------

Wenn beispielsweise Verbindungsprobleme auftreten oder Zahlungsvorgänge mit :productname:`PayPal Checkout` nicht erwartungsgemäß funktionieren, wenden Sie sich an den Support von PayPal.

Es ist hilfreich, wenn Sie bereits Log-Dateien haben, wenn Sie den PayPal-Support kontaktieren. Dazu aktivieren Sie den Debug-Modus.

Damit zeichnen Sie die an den OXID eShop gesendeten Webhook Calls von PayPal in der Log-Datei :file:`oxideshop.log` auf.

|procedure|

1. Öffnen Sie die Datei :file:`source/source/config.inc.php`.
#. Ändern Sie den Wert des Parameters :technicalname:`sLogLevel` zu :technicalname:`debug`.

   .. code::

      $this->sLogLevel = 'debug';

#. Stellen Sie dem Support die Datei :file:`/source/source/log/oxideshop.log` zur Verfügung.
#. Sobald das Problem gelöst ist, ändern Sie den Wert des Parameters :technicalname:`sLogLevel` wieder zum Standardwert :technicalname:`error`.

