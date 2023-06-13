Troubleshooting
===============

"Kreditkarte" und "Rechnungskauf" nicht verfügbar
-------------------------------------------------

Es kann sein, dass die Zahlungsarten "Kreditkarte" und "Rechnungskauf" nicht zur Verfügung stehen.

Das ist der Fall, wenn Sie zum Generieren eines Webhooks bei PayPal die API-Anmeldeinformationen (beispiesweise aus einer existierenden Version von PayPal Checkout) :emphasis:`manuell` eingegeben haben, statt den Prozess mit der Schaltfläche :guilabel:`Anmeldung Händler PayPal-Integration` zu starten.

**Abhilfe**

Um sicherzustellen, dass alle Zahlungsarten verfügbar sind, tun Sie (am Beispiel eines Sandbox-Kontos) Folgendes:

1. Wählen Sie :menuselection:`PayPal --> Konfiguration`.
#. Löschen Sie unter :guilabel:`API-Anmeldeinformationen` alle Anmeldeinformationen und wählen :guilabel:`Speichern`.
   |br|
   Die Schaltfläche :guilabel:`Anmeldung Händler PayPal-Integration (Sandbox)` erscheint.
#. Wählen Sie :guilabel:`Anmeldung Händler PayPal-Integration (Sandbox)`.
#. Durchlaufen Sie den Registrierungs-Prozess mit der E-Mail-Adresse des Sandbox-Händlerkontos.

Weitere Informationen finden Sie im Kapitel :ref:`konfiguration:Konfiguration` unter :ref:`konfiguration:API-Anmeldeinformationen`.


.. todo: Inhalt aus Hinweis in Konfig erg.:
        Wenn die Webhooks des Moduls geprüft werden müssen, dann bietet es sich an, den Parameter $this->sLogLevel in der Datei config.inc.php auf den Wert debug zu setzen.
        Auf diese Weise werden die an den Shop gesendeten Webhook Calls von PayPal im Log oxideshop.log aufgezeichnet.