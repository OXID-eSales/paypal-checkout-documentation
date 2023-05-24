Betrieb
=======

Reservierte Zahlung auslösen
----------------------------

Bei der Zahlungsart :technicalname:`PayPal` können Sie die Zahlung manuell auslösen.

Wenn Sie diese Möglichkeit nutzen, überwachen Sie dazu noch nicht bezahlte Bestellungen.

|background|

Sie haben für die Zahlungsart :technicalname:`PayPal` festgelegt, dass Sie die Bezahlung manuell anstoßen wollen (siehe :ref:`konfiguration:Geldeinzug festlegen`).

|prerequisites|

* Sie haben den Artikel versendet (siehe :ref:`betrieb:Artikel als versendet markieren`).

|procedure|

1. Wählen Sie unter :menuselection:`Bestellungen verwalten --> Bestellungen` die noch nicht bezahlte Bestellung (:ref:`oxdajt01`, Pos. 1).
#. Optional: Makieren Sie den Artikel als versendet.
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

Empfehlung: Wenn Sie physische Artikel versenden und Sie einen Tracking-Code (beispielsweise eine DHL-Sendnungsnummer) haben, dann speichern Sie den Tracking-Code.

Sie können nicht nur Ihren Kunden per E-Mail über den Verbleib der Sendung informieren.

Im Fall von Auseinandersetzungen mit Kunden ist es für PayPal damit leichter leichter, Ihren Schaden zu regulieren.

|procedure|

1. Wählen Sie unter :menuselection:`Bestellungen verwalten --> Bestellungen` die Bestellung.
#. Geben Sie auf der Registerkarte :guilabel:`Stamm` wie gewohnt den Tracking Code im gleichnamigen Eingabefeld ein.
#. Damit PayPal die Information verarbeiten kann, erfassen Sie zusätzlich auch folgende Informationen in den entsprechenden Auswahllisten:

   * Versanddienstleister (Land):
   * Versanddienstleister (Anbieter): beispielsweise DHL

#. Speichern Sie Ihre Einstellungen.

.. todo: Erneut testen: Bestellung anlegen, Code erfassen: KJD0123456789012345678910, prüfen ob Auswahl Dienstleister zwingend
.. todo: #ML: Bug?: Wenn ich etwas Falsches im Feld Tracking Code eingebe und speichere, kann ich den Wert nicht mehr korrigieren; korrigieren nur möglich, wenn noch nicht bezahlt? -- nein, geht auch nch Bezahlen
.. todo: #ML: "Damit PayPal die Information verarbeiten kann, ": Was passiert, wenn ich die Land und Anbieter leer lasse?
.. todo: #ML: Was ist maßgeblich für "Versanddienstleister (Land): ": das Zielland der Lieferung, das Ausgangsland, der Sitz des Providers?
.. todo: #tbd: EN: :guilabel:`Main`; Tracking Carrier (Country); Tracking Carrier (Provider)

.. _oxdajt03:

.. figure:: /media/screenshots/oxdajt03.png
   :alt: Tracking-Code mit Angaben zum Versanddienstleister senden
   :width: 650
   :class: with-shadow

   Abb.: Tracking-Code mit Angaben zum Versanddienstleister senden

Unvollständige Bestellungen manuell löschen
-------------------------------------------

Löschen Sie unvollständige Bestellungen manuell.

|background|

Aus technischen Gründen erzeugt PayPal Bestellungen, auch wenn die Bestellungen am Ende nicht abgeschlossen werden.

Um das System performant zu halten, müssen Sie solche unvollständigen Bestellungen regelmäßig entfernen.

Das :emphasis:`manuelle` Löschen -- im Gegensatz zum :emphasis:`automatischen` Löschen -- kann beispielsweise sinnvoll sein, um zu prüfen, ob es regelmäßig Abbrüche bei bestimmten Zahlungsarten gibt.

|prerequisites|

Sie haben das automatische Löschen unvollständiger Bestellungen deaktiviert (siehe :ref:`konfiguration:Behandlung nicht beendeter Bestellungen festlegen`).

|procedure|

1. Wählen Sie :menuselection:`Bestellungen --> Bestellungen verwalten`.

   .. todo: #ML/#ES: Ich kann es nicht nachvollziehen: Wie erzeuge ich eine unabgeschlossene Bestellung, Woran erkenne ich sie im Backend, wie lösche ich sie manuell?
   .. todo: #ML/Wie identifiziere ich unvollständige Bestellungen, wie unterscheide ich sie von solchen wie Rechnungskauf, wo die Bezahlung noch nicht erfolgt ist?

#. Wählen Sie :guilabel:`Eintrag löschen` (:ref:`oxdajt03`).

.. todo:  #tbd: Bild anlegen

.. _oxdajt04:

.. figure:: /media/screenshots/oxdajt04.png
   :alt: Unvollständige Bestellungen manuell löschen
   :width: 650
   :class: with-shadow

   Abb.: Unvollständige Bestellungen manuell löschen


.. Intern: oxdajt, Status:
