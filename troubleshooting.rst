Troubleshooting
===============

"Kreditkarte" und "Rechnungskauf" nicht verfügbar
-------------------------------------------------

Es kann sein, dass die Zahlungsarten "Kreditkarte" und "Rechnungskauf" nicht zur Verfügung stehen.

Das ist der Fall, wenn Sie zum Generieren eines Webhooks bei PayPal die API-Anmeldeinformationen (beispiesweise aus einer existierenden Version von PayPal Checkout) :emphasis:`manuell` eingegeben haben, statt den Prozess mit der Schaltfläche :guilabel:`Anmeldung Händler PayPal-Integration` zu starten.

|procedure|

Um sicherzustellen, dass alle Zahlungsarten verfügbar sind, tun Sie (am Beispiel eines Sandbox-Kontos) Folgendes:

1. Wählen Sie :menuselection:`PayPal --> Konfiguration`.
#. Löschen Sie unter :guilabel:`API-Anmeldeinformationen` alle Anmeldeinformationen und wählen :guilabel:`Speichern`.
   |br|
   Die Schaltfläche :guilabel:`Anmeldung Händler PayPal-Integration (Sandbox)` erscheint.
#. Wählen Sie :guilabel:`Anmeldung Händler PayPal-Integration (Sandbox)`.
#. Durchlaufen Sie den Registrierungs-Prozess mit der E-Mail-Adresse des Sandbox-Händlerkontos.

Weitere Informationen finden Sie im Kapitel :ref:`konfiguration:Konfiguration` unter :ref:`konfiguration:API-Anmeldeinformationen`.

Debug-Modus einschalten
-----------------------

Wenn beispielsweise Verbindungsprobleme auftreten oder Zahlungsvorgänge mit :productname:`PayPal Checkout` nicht erwartungsgemäß funktionieren, wenden Sie sich an den Support von PayPal.

.. todo: #ML: Was ist die Support-Adresse von Paypal?
.. todo: #tbd: Pfad der Logdatei verifizieren: :file:`/source/source/log/oxideshop.log`

Es ist hilfreich, wenn Sie bereits Log-Dateien haben, wenn Sie den PayPal-Support kontaktieren. Dazu aktivieren Sie den Debug-Modus.

Damit zeichnen Sie die an den OXID eShop gesendeten Webhook Calls von PayPal in der Log-Datei :file:`oxideshop.log` auf.

|procedure|

1. Öffnen Sie die Datei :file:`source/source/config.inc.php`.
#. Ändern Sie den Wert des Parameters :technicalname:`sLogLevel` zu :technicalname:`debug`.

   .. code::

      $this->sLogLevel = 'debug';

#. Stellen Sie dem Support die Datei :file:`/source/source/log/oxideshop.log` zur Verfügung.
#. Sobald das Problem gelöst ist, ändern Sie den Wert des Parameters :technicalname:`sLogLevel` wieder zum Standardwert :technicalname:`error`.
