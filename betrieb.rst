:orphan:
Betrieb
=======


.. todo: #MK: Anwendungsfall für Webhook-Debugging definieren
    .. hint::
    It's possible to let the shop track the incoming webhooks by setting the config parameter `$this->sLogLevel` in the file `config.inc.php` to `debug`.
    After that, the webhook calls by PayPal are written to the file `oxideshop.log`.



Überwachen Sie Ihre Bestellungen und die mit PayPal ausgeführten Zahlungsvorgänge.

Nehmen Sie beispielsweise Rückzahlungen vor oder beheben Sie die Ursachen von Zahlungsproblemen.

|procedure|

1. Wählen Sie :menuselection:`Bestellungen --> Bestellungen verwalten`.
#. Wählen Sie die Bestellung.
#. Zeigen Sie auf der Registerkarte :guilabel:`PayPal` die Daten der Transaktion an.
#. Prüfen Sie den Status des Zahlungsvorgangs:

   * :guilabel:`abgeschlossen`: Die Zahlung ist erfolgt. Sie können den Artikel versenden (:ref:`oxdamd01`).

     .. _oxdamd01:

     .. figure:: /media/screenshots/oxdamd01.png
        :alt: PayPal-Auftragsstatus: abgeschlossen

        Abb.: PayPal-Auftragsstatus: abgeschlossen

   * :guilabel:`Ausstehend`: Die Zahlung steht aus (:ref:`oxdamd02`).
     |br|
     Wie lange eine Zahlung ausstehend bleibt, hängt von der Zahlungsart ab. Eine Kreditkarten-Zahlung kann beispielsweise zwei Tage dauern.
     |br|
     In bestimmten Fällen ist es auch sinnvoll, dass Sie eine Zahlung so konfigurieren, dass sie erst durch die Auslieferung ausgelöst wird (siehe auch: :ref:`konfiguration:Optionen für Kreditkarten/PayPal`).

     .. _oxdamd02:

     .. figure:: /media/screenshots/oxdamd02.png
        :alt: PayPal-Auftragsstatus: ausstehend

        Abb.: PayPal-Auftragsstatus: ausstehend

   * :guilabel:`Fehler`: Ein Problem ist aufgetreten.

#. Wenn ein Problem aufgetreten ist, tun Sie Folgendes, um die Ursache zu beheben:

   a. Fragen Sie Ihren Kunden, warum die Zahlung nicht erfolgt ist.
   b. Wenn die Ursache nicht beim Kunden liegt, wenden Sie sich unter `support@PayPal.com <support@PayPal.com>`_ an den fachlichen Support von PayPal.
      |br|
      Halten Sie dabei die folgenden Informationen bereit (:ref:`oxdamd03`):

       .. todo: tbd

   c. Wenn der fachliche Support von PayPal feststellt, dass es sich um ein technisches Problem handelt, halten Sie für den technischen Support zusätzlich die folgenden Informationen bereit (:ref:`oxdamd03`):

       .. todo: tbd


.. Intern: oxdamd, Status: