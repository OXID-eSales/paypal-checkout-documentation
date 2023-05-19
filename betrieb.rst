Betrieb
=======

Reservierte Zahlung auslösen
----------------------------

.. todo: #tbd: Kap. ergänzen und Screenshot hinzufügen.

Sie haben für bestimmte Zahlungsarten festgelegt, dass Sie die Bezahlung manuell anstoßen wollen (siehe :ref:`konfiguration:Geldeinzug festlegen`:

|procedure|

1. Wählen Sie unter :menuselection:`Bestellungen verwalten --> Bestellungen` die Bestellung.
2. Wählen und auf der Registerkarte :guilabel:`PayPal Checkout` die Schaltfläche :guilabel:`Einziehen` (:ref:`oxdajt01`).


.. _oxdajt01:

.. figure:: /media/screenshots/oxdajt01.png
   :alt: Reservierte Zahlung auslösen
   :width: 650
   :class: with-shadow

   Abb.: Reservierte Zahlung auslösen

Tracking-Code senden
--------------------

.. todo: #tbd

.. _oxdajt02:

.. figure:: /media/screenshots/oxdajt02.png
   :alt: Tracking-Code senden
   :width: 650
   :class: with-shadow

   Abb.: Tracking-Code senden

Unvollständige Bestellungen manuell löschen
-------------------------------------------

.. todo: #tbd

Löschen Sie unvollständige Bestellungen manuell.

|background|

Aus technischen Gründen erzeugt PayPal Bestellungen, auch wenn die Bestellungen am Ende nicht abgeschlossen werden.

Um das System performant zu halten, müssen Sie soche Bestellungen regelmäßig entfernen.

Das manuelle Löschen im Gegensatz zum automatischen Löschen kann beispielsweise sinnvollsein, um zu prüfen, ob es regelmäßig Abbrüche bei bestimmten Zahlungsarten gibt.

|prerequisites|

Sie haben das automatische Löschen unvollständiger Bestellungen deaktiviert (siehe :ref:`konfiguration:Behandlung nicht beendeter Bestellungen festlegen`).

|procedure|

1. Wählen Sie :menuselection:`Bestellungen --> Bestellungen verwalten`.

   .. todo: #ML/#ES: Ich kann es nicht nachvollziehen: Wie erzeuge ich eine unabgeschlossene Bestellung, Woran erkenne ich sie im Backend, wie lösche ich sie manuell?
   .. todo: Wie identifiziere ich unvollständige Bestellungen, wie unterscheide ich sie von solchen wie Rechnungskauf, wo die Bezahlung noch nicht erfolgt ist?

#. Wählen Sie :guilabel:`Eintrag löschen` (:ref:`oxdajt02`.


.. _oxdajt03:

.. figure:: /media/screenshots/oxdajt03.png
   :alt: Unvollständige Bestellungen manuell löschen
   :width: 650
   :class: with-shadow

   Abb.: Unvollständige Bestellungen manuell löschen


.. Intern: oxdajt, Status:
