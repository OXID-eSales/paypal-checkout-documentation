Konfiguration
=============


Machen Sie das Modul :productname:`PayPal Checkout` für Ihren OXID eShop betriebsbereit.


.. include:: /_static/reuse/paypal-checkout-migration.rst

Grundsätzliches Vorgehen
------------------------


1. Aktivieren Sie das Modul.
   |br|
   Die wichtigsten Zahlungsmethoden sind damit automatisch aktiviert.
#. Stellen Sie die Verbindung zu Ihrem PayPal-Händlerkonto her.
   |br|
   Erstellen Sie zum Testen zunächst nur ein Testkonto (PayPal Sandbox).
#. Optional: Deaktivieren Sie bei Bedarf die Express-Checkout-Funktion von :productname:`PayPal Checkout`.
#. Optional: Legen Sie fest, ob Sie Ihren Kunden die PayPal-Ratenzahlung anbieten wollen.
#. Konfigurieren Sie die von :productname:`PayPal Checkout` bereitgestellten Zahlungsmethoden als Zahlungsarten in Ihrem eShop:

   * Aktivieren Sie die Länder, die Sie abdecken wollen.
   * Verknüpfen Sie die Zahlungsarten mit Ihren Versandarten und Versandkostenregeln.

#. Führen Sie Testzahlungen in der :productname:`PayPal Checkout`-Sandbox aus.

   .. hint::

      Hinweis: Die Betriebsart :guilabel:`Sandbox` ist nach dem Aktivieren standardmäßig eingestellt.

.. todo: #tbd: Verifizieren: Die Betriebsart :guilabel:`Sandbox` ist nach dem Aktivieren standardmäßig eingestellt.

7. Testen Sie :productname:`PayPal Checkout` in der PayPal-Sandbox und passen Sie die Konfiguration an, bis alle Zahlungsprozess nach Ihren Vorstellungen funktionieren.
#. Wenn Sie vom Modul PayPal oder PayPal PLUS zu :productname:`PayPal Checkout` umsteigen wollen, tun Sie Folgendes:

   a. Stellen Sie sicher, dass es keine offenen Bestellungen gibt.
   b. Deaktivieren Sie das Modul PayPal oder PayPal PLUS.
#. Schalten Sie :productname:`PayPal Checkout` frei:

   a. Wenn Sie noch kein Händlerkonto haben, legen Sie für den Livebetrieb eins an.
   b. Wechseln Sie in den Betriebsmodus :guilabel:`Live`.


PayPal Checkout aktivieren
--------------------------

Aktivieren Sie :productname:`PayPal Checkout` in jedem Subshop, in dem Sie das Modul nutzen wollen.

|procedure|

1. Wählen Sie :menuselection:`Erweiterungen --> Module`. 
2. Wählen Sie das Modul :guilabel:`OSC :: PayPal - Online-Bezahldienst` und wählen Sie :menuselection:`Stamm --> Aktivieren`.


|result|

Unter :menuselection:`Shopeinstellungen --> Zahlungsarten` sind die Zahlungsarten :guilabel:`PayPal v2` sowie wichtige weitere Zahlungsarten, als aktiv gekennzeichnet.

Um eine bestimmte länderspezifische Zahlungsart tatsächlich nutzen zu können, müssen Sie unter :menuselection:`Stammdaten --> Länder` das betreffende Land als aktiv markiert haben.

|example|

Um iDEAL anbieten zu können, müssen Sie sichergestellt haben, dass Sie unter :menuselection:`Stammdaten --> Länder` die Niederlande aktiv gesetzt haben.

.. todo: #Mario: Zahlungsartname PayPal v2 klären

.. todo: #tbd: erläutern, wie man den Shop um neue Länder und dedizierte Unzer-Zahlungsmethoden erweitert

.. todo: #Bild ergänzen;
   .. image:: media/screenshots/oxdaac01.png
       :alt: PayPal, Moduleinstellungen
       :class: with-shadow
       :height: 344
       :width: 650


PayPal Checkout konfigurieren
-----------------------------

Um die Konfiguration zu starten, wählen Sie :menuselection:`PayPal --> Konfiguration`. 



API-Anmeldeinformationen
^^^^^^^^^^^^^^^^^^^^^^^^

Registrieren Sie einen Webhook, um Ihren eShop mit PayPal zu verbinden.

Der Webhook erlaubt es PayPal, Ihren OXID eShop zu kontaktieren und in Echtzeit Statusmeldungen beispielsweise über abgeschlossene Transaktionen zu liefern.

Im ersten Durchgang testen Sie die mit :productname:`PayPal Checkout` bereitgestellten Zahlungsarten mit Test-Zugangsdaten in einer *Sandbox*.

Erst wenn alles nach Ihren Vorstellungen funktioniert, nutzen Sie die Zugangsdaten für den *Live*-betrieb.


|procedure|


1. Um sich auf der Sandbox anzumelden, wählen Sie unter :guilabel:`API-Anmeldeinformationen` die Schaltfläche :guilabel:`Anmeldung Händler PayPal-Integration (Sandbox)`.
2. Durchlaufen Sie den Registrierungs-Prozess.

.. hint::

   Die Zahlungsmethode Rechnungskauf bietet PayPal nur Shop-Betreibern aus Deutschland an.


|result|

Sobald Sie PayPal die Genehmigung erteilt haben, Ihr Sandbox-Konto mit dem
PayPal Test Store zu verbinden, werden die API-Anmeldeinformationen angezeigt, und das
Modul ist aktiv.

Unter :menuselection:`Shopeinstellungen --> Zahlungsarten` ist die Zahlungsart :guilabel:`PayPal v2` aktiv.

.. todo: Bild ergänzen;

.. hint::

   **Neuen Webhook generieren**

   Manchmal kann es nötig sein, den bestehenden Webhook zu löschen und einen neuen zu generieren.

   Um einen Webhook zu löschen, löschen Sie die Anmeldedaten und wählen :guilabel:`Speichern`.

   Die Schaltfläche :guilabel:`Anmeldung Händler PayPal-Integration` erscheint, und Sie können den Webhook neu generieren.


.. _Einstellungen-fuer-die-Buttonplatzierung:

Einstellungen für die Buttonplatzierung
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Entscheiden Sie, ob Sie die Schnellkauf-Funktion von :productname:`PayPal Checkout` anbieten wollen.

Mit der Schnellkauf-Funktion überspringt der Kunde die Anmeldung in Ihrem eShop.

|example|

* Ihre Kunden haben typischerweise nur einen einzigen Artikel im Warenkorb, wenn sie eine Bestellung aufgeben?
  |br|
  In diesem Fall ist es sinnvoll, die Kunden so schnell und barrierefrei wie möglich zum Ziel zu führen und die Schnellkauf-Funktion zu aktivieren.
* Einen bedeutenden Teil von Umsatz oder Marge erwirtschaften Sie mit Zubehörartikeln?
  |br|
  In diesem Fall kann es sinnvoll sein, das Bezahlen hinauszuzögern und die PayPal-Schaltflächen beispielsweise nur im Warenkorb und im Checkout anzubieten.

Sie legen also fest,

* ob die Kunden Ihren Checkout-Prozess durchlaufen und sich in Ihrem eShop registrieren müssen

  oder

* ob die Kunden ohne Registrierung mit ihrem PayPal-Konto die Bestellung direkt auslösen können (Schnellkauf).

**Standardmäßig** ist die Schnellkauf-Funktion aktiv, und die PayPal-Schaltfläche erscheint auf folgenden Seiten.

* auf der Produkt-Detailseite
* im Warenkorb
* auf der Checkout-Seite

Ihre Kunden können also jederzeit mit ihrem PayPal-Konto die Bestellung auslösen.

Wenn Sie wollen, dass Ihre Kunden sich in Ihrem eShop registrieren müssen, deaktivieren Sie die Schnellkauf-Funktion.

|procedure|

1. Um die Express-Checkout-Funktion zu deaktivieren, deaktivieren Sie die Kontrollkästchen :guilabel:`Produktdetailseite` und :guilabel:`Warenkorb`.
2. Speichern Sie Ihre Einstellungen.

|Result|

Die PayPal-Schaltfläche erscheint nur auf der Checkout-Seite.

.. todo: #tbd Funktionsbeschreibung "Später bezahlen" (0301, 0'31'10)


Login mit PayPal
^^^^^^^^^^^^^^^^

Legen Sie fest, dass Kunden automatisch in Ihrem OXID eShop angemeldet sind,

* wenn die E-Mail-Adresse des PayPal-Kontos und des eShop-Kontos identisch sind

und

* sobald Ihr Kunde in seinem PayPal-Konto angemeldet ist

Vorteil: Sie gestalten den Anmeldeprozess für Ihre Kunden bequemer.

Ihre Kunden überspringen damit den Anmeldemechanismus. Ihre Kunden melden sich in Ihrem OXID eShop an, *ohne ihr Passwort eingeben zu müssen*.


Nachteile:

* Oft nutzen beispielsweise Ehepartner dasselbe PayPal-Konto.
  |br|
  Einer der Partner könnte dadurch die Bestellhistorie oder andere Kundendaten des Partner im OXID eShop einsehen.
  |br|
  Potentiell besteht also ein Datenschutz-Risiko.
* Müssen sich Ihre Kunden nicht in Ihrem eShop anmelden, gehen Ihnen Daten zur Bestellhistorie der Kunden verloren.
  |br|
  Solche Daten könnten Sie andernfalls für statistische Auswertungen zur gezielten Ansprache Ihrer Kunden nutzen.


Wenn Sie die :guilabel:`Login mit PayPal` *nicht* aktivieren, passiert Folgendes:

* Wenn die PayPal-E-Mail-Adresse des Kunden *bekannt* ist, wird der PayPal-Bezahlvorgang unterbrochen, und der Kunde muss sich in Ihrem eShop anmelden.
  |br|
  Die PayPal-Session ist erstellt, und Ihr Kunde ist in Ihrem eShop angemeldet.
  |br|
  Die Identität des Kunden steht eindeutig fest, und die aktuelle Bestellung wird zur Bestellhistorie des Kunden hinzugefügt.
* Wenn die PayPal-E-Mail-Adresse des Kunden *nicht* bekannt ist, führt Ihr Kunde die Bestellung mit einem Gast-Konto aus.
  |br|
  Ihr Kunde landet mit den PayPal-Adressdaten auf der Checkout-Seite. Die Daten werden nur für die aktuelle Bestellung einmalig gespeichert, es wird kein Kundenkonto im eShop angelegt.

.. todo: #tbd: Funktionsbeschreibung: Aspekt Bestellhistorie hinzufügen

|procedure|

.. ATTENTION::

   Die Funktion :guilabel:`Login mit PayPal` ist standardmäßig **aktiviert**.

1. Prüfen Sie, was im schlimmsten Fall schiefgehen kann, wenn mehrere Benutzer dasselbe PayPal-Konto nutzen und in Ihrem eShop die Daten der anderen Benutzer einsehen können.
2. Es besteht kein ernstes Risiko darin besteht, wenn Ihre Kunden sich in Ihrem eShop bequem automatisch mit ihren PayPal-Konten anmelden?
   |br|
   Dann lassen Sie das Kontrollkästchen :guilabel:`Im Shop beim Kauf automatisch einloggen` aktiviert.
   |br|
   Andernfalls deaktivieren Sie das Kontrollkästchen.
3. Speichern Sie Ihre Einstellungen.


Banner-Einstellungen
^^^^^^^^^^^^^^^^^^^^

Optional: Legen Sie fest, ob Sie mit Bannern für die PayPal-Ratenzahlung werben wollen.


Wenn Sie die Vorteile nutzen wollen, legen Sie fest, wo die Banner erscheinen sollen, beispielsweise auf der Startseite, auf der Detailseite von Artikeln, auf den Kategorieseiten, in den Suchergebnissen und/oder im Bestellprozess.

.. attention::

   **Datenschutz**

   Um die Banner erscheinen zu lassen, ist eine permanente Kommunikation mit den Servern von PayPal nötig.

   Dazu werden bei jedem Seitenaufruf Skripte gestartet, die das Nutzerverhalten beobachten und die die für den PayPal-Bezahlprozess nötigen Informationen sammeln und an PayPal übermitteln.

   Diese Kommunikation kann unerwünscht sein, beispielsweise aus Gründen

      * des Datenschutzes
      * der Performance

   Stellen Sie in diesem Fall sicher, dass die Funktion deaktiviert ist.

   Standardmäßig ist die Funktion eingeschaltet.

.. todo: #tbd: Screenshot ergänzen -- Funktionsbeschreibung 0301,


|procedure|

1. Um das Ausführen von Skripten für die PayPal-Bannerwerbung auszuschalten, deaktivieren Sie das Kontrollkästchen :guilabel:`Ratenzahlung-Banner aktivieren`.
   |br|
   Wenn Sie das Kontrollkästchen nicht markieren, dann werden die Skripte nicht ausgeführt.
#. Wenn Sie das Ausführen von Skripten für die PayPal-Bannerwerbung :emphasis:`zulassen`, legen Sie fest, auf welchen Seiten das Banner erscheinen soll.
   |br|
   Markieren Sie dazu das entsprechende Kontrollkästchen.
#. Wenn Sie ein individuelles Theme oder ein angepasstes OXID-Theme verwenden, tun Sie Folgendes:

   a. Identifizieren Sie den CSS-Selektor der Seite, hinter dem Sie den Banner platzieren wollen.
   b. Geben Sie den CSS-Selektor in entsprechende Eingabefeld ein.
#. Legen Sie unter :guilabel:`Farbe des Ratenzahlung-Banners auswählen` die gewünschte Farbe des Banners fest.
#. Speichern Sie Ihre Einstellungen.


PayPal Checkout testen
----------------------

Konfigurieren Sie :productname:`PayPal Checkout` nach Ihren Wünschen und testen Sie das Ergebnis.

|procedure|


1. Stellen Sie sicher, dass unter :menuselection:`Stammdaten --> Länder` die Märkte aktiv sind, die Sie abdecken wollen.
#. Tun Sie unter :menuselection:`Shopeinstellungen --> Zahlungsarten` Folgendes:

   a. Ordnen Sie den gewünschten :productname:`PayPal Checkout`-Zahlungsarten (beispielsweise :guilabel:`iDEAL (über PayPal)` jeweils mindestens eine Benutzergruppen zu.
   b. Stellen Sie sicher, dass Sie den :productname:`PayPal Checkout`-Zahlungsarten auf der Registerkarte :guilabel:`Stamm` den jeweils gewünschten minimalen und maximalen Einkaufswert festgelegt haben.
      |br|
      Beispiel: Der maximale Einkaufswert für die Zahlungsart :guilabel:`PayPal v2` ist standardmäßig auf 10.000 € begrenzt. Der Mindest-Einkaufswert ist 10 €.
#. Tun Sie unter :menuselection:`Shopeinstellungen --> Versandarten` Folgendes:

   a. Weisen Sie die gewünschten :productname:`PayPal Checkout`-Zahlungsarten den jeweiligen Versandarten zu.
   b. Stellen Sie sicher, dass mindestens eine Versandart für die Bezahlung mit der Zahlungsart :guilabel:`PayPal v2` angelegt ist.
      |br|
      Typischerweise ist das die Standard-Zahlungsart.

.. todo: #tbd: prüfen Zahlungsart :guilabel:`PayPal` oder PP v2?
.. todo: #tbd: prüfen: Weitere Informationen finden Sie unter `Zahlungsarten <https://docs.oxid-esales.com/eshop/de/6.0/einrichtung/zahlungsarten/zahlungsarten.html>`_ der Anwenderdokumentation des OXID eShop. Ändern Sie ggf. den Einkaufswert (€) in 0 bis 99999.


PayPal Checkout freischalten
----------------------------

Schalten Sie :productname:`PayPal Checkout` nach dem Testen frei.

|prerequisites|

Sie haben die gewünschten Zahlungsarten konfiguriert und mit Testzahlungen in der PayPal-Sandbox erfolgreich getestet.

|procedure|

1. Wählen Sie unter :guilabel:`API-Anmeldeinformationen` den Betriebsmodus :guilabel:`Live`.
#. Wählen Sie die Schaltfläche :guilabel:`Anmeldung Händler PayPal-Integration (Live)`.
   |br|
   Sie gelangen in ein Dialogfenster zum Anmelden bei PayPal.
#. Melden Sie sich mit Ihrem bestehenden PayPal-Händlerkonto an. Wenn Sie noch keine Zugangsdaten für den Live-Betrieb haben, legen Sie ein PayPal-Händlerkonto neu an.
#. Speichern Sie Ihre Einstellungen.


|result|

Die PayPal API-Anmeldeinformationen werden eingefügt.

Das Modul :productname:`PayPal Checkout` ist aktiv und steht für Bestellungen Ihrer Kunden bereit.



.. Intern: oxdajr, Status: