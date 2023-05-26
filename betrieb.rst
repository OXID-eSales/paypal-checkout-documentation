Betrieb
=======

Reservierte Zahlung auslösen
----------------------------

Bei der Zahlungsart :technicalname:`PayPal` können Sie die Zahlung manuell auslösen.

Wenn Sie diese Möglichkeit nutzen, dann überwachen Sie die noch nicht bezahlten Bestellungen.

|background|

Sie haben für die Zahlungsart :technicalname:`PayPal` festgelegt, dass Sie die Bezahlung manuell anstoßen wollen (siehe :ref:`konfiguration:Geldeinzug festlegen`).

|prerequisites|

* Sie haben den Artikel versendet (siehe :ref:`betrieb:Artikel als versendet markieren`).

|procedure|

1. Wählen Sie unter :menuselection:`Bestellungen verwalten --> Bestellungen` die noch nicht bezahlte Bestellung (:ref:`oxdajt01`, Pos. 1).
#. Optional: Markieren Sie den Artikel als versendet.
   |br|
   Dazu wählen Sie auf der Registerkarte :guilabel:`Übersicht` die Schaltfläche :guilabel:`Jetzt versenden`.
#. Wählen Sie auf der Registerkarte :guilabel:`PayPal Checkout` die Schaltfläche :guilabel:`Einziehen` (:ref:`oxdajt01`, Pos. 2).

.. _oxdajt01:

.. figure:: /media/screenshots/oxdajt01.png
   :alt: Reservierte Zahlung auslösen
   :width: 650
   :class: with-shadow

   Abb.: Reservierte Zahlung auslösen

|result|

Mit der nächsten Aktualisierung der Seite ist die Bestellung in der Liste der Bestellungen als bezahlt markiert (:ref:`oxdajt02`, Pos. 1).

Der PayPal-Status ist :technicalname:`abgeschlossen` (:ref:`oxdajt02`, Pos. 2).

.. _oxdajt02:

.. figure:: /media/screenshots/oxdajt02.png
   :alt: Reservierte Zahlung: PayPal-Status prüfen
   :width: 650
   :class: with-shadow

   Abb.: Reservierte Zahlung: PayPal-Status prüfen

Artikel als versendet markieren
-------------------------------

Empfehlung: Wenn Sie physische Artikel versenden und Sie einen Tracking-Code (beispielsweise eine DHL-Sendungsnummer) haben, dann speichern Sie den Tracking-Code.

Mit dem Tracking-Code können Sie

* Ihren Kunden per E-Mail über den Verbleib der Sendung informieren
* es PayPal erleichtern, im Fall von Auseinandersetzungen mit Kunden Ihren Schaden zu regulieren

|procedure|

1. Wählen Sie unter :menuselection:`Bestellungen verwalten --> Bestellungen` die Bestellung.
#. Erfassen Sie auf der Registerkarte :guilabel:`Stamm` wie gewohnt den Tracking Code im gleichnamigen Eingabefeld (:ref:`oxdajt03`, Pos. 2).
#. Erfassen Sie zusätzlich auch folgende Informationen in den entsprechenden Auswahllisten (:ref:`oxdajt03`, Pos. 1):

   * Versanddienstleister (Land): Landespezifische Version des Versanddienstleisters

     Einige Versandunternehmen haben eine globale Version und eine oder mehrere länderspezifische Versionen, beispielsweise DHL Deutsche Post.

     Beispiel: Im Fall von DHL Deutsche Post als Versanddienstleister steht :technicalname:`Österreich` für DHL Austria.

     Weitere Informationen finden Sie bei PayPal unter `developer.paypal.com/docs/tracking/reference/carriers/ <https://developer.paypal.com/docs/tracking/reference/carriers/>`_.

   * Versanddienstleister (Anbieter): beispielsweise DHL Deutsche Post

#. Speichern Sie Ihre Einstellungen.

|result|

Der Tracking-Code wird an PayPal übermittelt.

.. todo: #tbd: EN: :guilabel:`Main`; Tracking Carrier (Country); Tracking Carrier (Provider)

.. _oxdajt03:

.. figure:: /media/screenshots/oxdajt03.png
   :alt: Tracking-Code und Versanddienstleister-Daten an PayPal senden
   :width: 650
   :class: with-shadow

   Abb.: Tracking-Code und Versanddienstleister-Daten an PayPal senden

Unvollständige Bestellungen manuell löschen
-------------------------------------------

Löschen Sie unvollständige Bestellungen manuell.

|background|

Aus technischen Gründen erzeugt PayPal Bestellungen, auch wenn die Bestellungen am Ende nicht abgeschlossen werden.

Das ist der Fall, wenn der Kunde im Checkout die Schaltfläche :guilabel:`Zahlungspflichtig bestellen` wählt, sich dann aber nicht bei PayPal anmeldet und den Bezahlvorgang abschließt.

Um das System performant zu halten, müssen Sie solche unvollständigen Bestellungen regelmäßig entfernen.

Das :emphasis:`manuelle` Löschen -- im Gegensatz zum :emphasis:`automatischen` Löschen -- kann beispielsweise sinnvoll sein, um zu prüfen, ob es regelmäßig Abbrüche bei bestimmten PayPal-Zahlungsarten gibt.

|prerequisites|

Sie haben das manuelle Löschen unvollständiger Bestellungen aktiviert (siehe :ref:`konfiguration:Behandlung nicht beendeter Bestellungen festlegen`).

|procedure|

1. Wählen Sie :menuselection:`Bestellungen --> Bestellungen verwalten`.

   Unabgeschlossene Bestellungen haben die Bestellnummer :technicalname:`0` (:ref:`oxdajt04`, Pos. 1a, 1b).

#. Wählen Sie :guilabel:`Eintrag löschen` (:ref:`oxdajt04`, Pos. 2).

.. _oxdajt04:

.. figure:: /media/screenshots/oxdajt04.png
   :alt: Unvollständige Bestellungen manuell löschen
   :width: 650
   :class: with-shadow

   Abb.: Unvollständige Bestellungen manuell löschen


.. Intern: oxdajt, Status:
