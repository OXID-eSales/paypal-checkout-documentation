Konfiguration
=============


Machen Sie das PayPal Checkout-Modul für Ihren OXID eShop betriebsbereit.


.. include:: /_static/reuse/paypal-checkout-migration.rst

Grundsätzliches Vorgehen
------------------------


1. Aktivieren Sie das Modul.
   |br|
   Die wichtigsten Zahlungsmethoden sind damit automatisch aktiviert.
#. Stellen Sie die Verbindung zu Ihrem PayPal-Händlerkonto her.
   |br|
   Erstellen Sie zum Testen zunächst nur ein Testkonto (PayPal Sandbox).
#. Optional: Deaktivieren Sie bei Bedarf die Express-Checkout-Funktion von PayPal Checkout.
#. Optional: Legen Sie fest, ob Sie Ihren Kunden die PayPal-Ratenzahlung anbieten wollen.
#. Konfigurieren Sie die von PayPal Checkout bereitgestellten Zahlungsmethoden als Zahlungsarten in Ihrem eShop:

   * Aktivieren Sie die Länder, die Sie abdecken wollen.
   * Verknüpfen Sie die Zahlungsarten mit Ihren Versandarten und Versandkostenregeln.

#. Führen Sie Testzahlungen in der PayPal Checkout-Sandbox aus.

   .. hint::

      Hinweis: Die Betriebsart :guilabel:`Sandbox` ist nach dem Aktivieren standardmäßig eingestellt.

.. todo: #tbd: Verifizieren: Die Betriebsart :guilabel:`Sandbox` ist nach dem Aktivieren standardmäßig eingestellt.

8. Testen Sie PayPal Checkout in der PayPal-Sandbox und passen Sie die Konfiguration an, bis alle Zahlungsprozess nach Ihren Vorstellungen funktionieren.
#. Wenn Sie vom Modul PayPal oder PayPal PLUS zu PayPal Checkout umsteigen wollen, tun Sie Folgendes:

   a. Stellen Sie sicher, dass es keine offenen Bestellungen gibt.
   b. Deaktivieren Sie das Modul PayPal oder PayPal PLUS.
#. Schalten Sie PayPal Checkout frei:

   a. Wenn Sie noch kein Händlerkonto haben, legen Sie für den Livebetrieb eins an.
   b. Wechseln Sie in den Betriebsmodus :guilabel:`Live`.


PayPal Checkout aktivieren
--------------------------

Aktivieren Sie PayPal Checkout in jedem Subshop, in dem Sie das Modul nutzen wollen.

|procedure|

1. Wählen Sie :menuselection:`Erweiterungen --> Module`. 
2. Wählen Sie das Modul :guilabel:`OSC :: PayPal - Online-Bezahldienst` und wählen Sie :menuselection:`Stamm --> Aktivieren`.


|result|

Unter :menuselection:`Shopeinstellungen --> Zahlungsarten` sind die Zahlungsarten :guilabel:`PayPal v2` sowie wichtige weitere Zahlungsarten, als aktiv gekennzeichnet.

Um eine bestimmte länderspezifische Zahlungsart tatsächlich nutzen zu können, müssen Sie unter :menuselection:`Stammdaten --> Länder` das betreffende Land als aktiv markiert haben.

|example|

Um iDEAL anbieten zu können, müssen Sie sichergestellt haben, dass Sie unter :menuselection:`Stammdaten --> Länder` die Niederlande aktiv gesetzt haben.


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

Im ersten Durchgang testen Sie die mit PayPal Checkout bereitgestellten Zahlungsarten mit Test-Zugangsdaten in einer *Sandbox*.

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

.. todo: Bild ergänzen; #Mario: PayPal v2` aktiv: so ist es korrekt, oder?

.. hint::

   **Neuen Webhook generieren**

   Manchmal kann es nötig sein, den bestehenden Webhook zu löschen und einen neuen zu generieren.

   Um einen Webhook zu löschen, löschen Sie die Anmeldedaten und wählen :guilabel:`Speichern`.

   Die Schaltfläche :guilabel:`Anmeldung Händler PayPal-Integration` erscheint, und Sie können den Webhook neu generieren.


.. _Einstellungen-fuer-die-Buttonplatzierung:

Einstellungen für die Buttonplatzierung
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. todo: #Mario: ist das Anwendungsfall?:

Entscheiden Sie, ob Sie die Express-Checkout-Funktion von PayPal Checkout anbieten wollen.

Legen Sie dazu fest,

* ob die Kunden Ihren Checkout-Prozess durchlaufen und sich in Ihrem eShop registrieren müssen

  oder

* ob die Kunden ohne Registrierung mit ihrem PayPal-Konto die Bestellung direkt auslösen können (PayPal Checkout).

.. todo: #Mario: Ist das die Definition von "Express-Checkout", PayPal Checkout scheint der offizielle Name der Funktion zu sein?

**Standardmäßig** ist die Express-Checkout-Funktion aktiv.

Die PayPal-Schaltfläche erscheint auf folgenden Seiten.

* auf der Produkt-Detailseite
* im Warenkorb
* auf der Checkout-Seite

Ihre Kunden können also jederzeit mit ihrem PayPal-Konto die Bestellung auslösen.

Wenn Sie wollen, dass Ihre Kunden sich in Ihrem eShop registrieren müssen, deaktivieren Sie die Express-Checkout-Funktion.

|procedure|

1. Um die Express-Checkout-Funktion zu deaktivieren, deaktivieren Sie die Kontrollkästchen :guilabel:`Produktdetailseite` und :guilabel:`Warenkorb`.
2. Speichern Sie Ihre Einstellungen.

|Result|

Die PayPal-Schaltfläche erscheint nur auf der Checkout-Seite.

.. todo: #Mario: dieses erwartete Ergebnis ist nicht der Fall, der Button erscheint auf der Zahlungsart-Seite. Ich hätte da aber einen Radiobutton erwartet.

.. todo: #Mario: Was hat es mit dem 2. PayPal-Button "Später bezahlen" auf sich?


Login mit PayPal
^^^^^^^^^^^^^^^^

.. todo: #Mario: ist das Anwendungsfall? Was kann schiefgehen?

Legen Sie fest, dass Kunden automatisch in Ihrem OXID eShop angemeldet sind,

* wenn die E-Mail-Adresse des PayPal-Kontos und des eShop-Kontos identisch sind

und

* sobald Ihr Kunde in seinem PayPal-Konto angemeldet ist

Vorteil: Sie gestalten den Anmeldeprozess für Ihre Kunden bequemer, sie überspringen damit den Anmeldemechanismus. Er meldet sich damit ohne Passwort in Ihrem OXID an.

.. todo: #Mario: das setzt aber voraus, dass der Kunde bereits sein eShop-Konto eingerichtet hat, es wird nicht autmatisch angelegt, korrekt?

.. todo: #Mario: was genau kann schlimmstenfalls schiefgehen?

Nachteil: Oft nutzen beispielsweise Ehepaare dasselbe PayPal-Konto. Einer der Partner könnte
dadurch die Bestellhistorie oder andere Kundendaten des Partner im OXID eShop einsehen.

Potentiell besteht also ein Datenschutz-Risiko. Deshalb ist die Einstellung standardmäßig deaktiviert.

|procedure|

1. Prüfen Sie, was im schlimmsten Fall schiefgehen kann, wenn mehrere Benutzer dasselbe PayPal-Konto nutzen und in Ihrem eShop die Daten der anderen Benutzer einsehen können.
2. Es besteht kein ernstes Risiko darin besteht, wenn Ihre Kunden sich in Ihrem eShop bequem automatisch mit ihren PayPal-Konten anmelden?
   |br|
   Dann markieren Sie das Kontrollkästchen :guilabel:`Im Shop beim Kauf automatisch einloggen`.
3. Speichern Sie Ihre Einstellungen.


.. todo: Mario: "Banner-Einstellungen" entfallen, da sie sich alle auf Ratenzahlung = Abo-Optionen beziehen?
   Oder aktiviere ich Ratenzahlung, indem ich "Ratenzahlung-Banner aktivieren" aktiviere?
   Muss ich vorher den PayPal,Beantragungsprozess durchlaufen haben: "Bieten Sie Ihren Kunden PayPal Ratenzahlung mit 0% effektiven Jahreszins an. Erfahren Sie hier mehr."


Banner-Einstellungen
^^^^^^^^^^^^^^^^^^^^

Optional: Legen Sie fest, ob Sie Ihren Kunden die PayPal-Ratenzahlung anbieten wollen.

Die Paypal-Ratenzahlung ist standardmäßig ausgeschaltet.

Wenn Sie Ratenzahlung anbieten, weisen mit Bannern auf diese Option hin.

.. todo: Screenshot ergänzen

Legen Sie fest, wo die Banner erscheinen sollen, beispielsweise auf der Startseite, auf der Detailseite von Artikeln, auf den Kategorieseiten, in den Suchergebnissen und/oder im Bestellprozess.

|procedure|

1. Um Ihren Kunden die Paypal-Ratenzahlung anbieten zu können, markieren Sie das Kontrollkästchen :guilabel:`Ratenzahlung-Banner aktivieren`.
   |br|
   Die Paypal-Ratenzahlung ist standardmäßig ausgeschaltet.
#. Legen Sie fest, auf welchen Seiten das Banner erscheinen soll, indem Sie das entsprechende Kontrollkästchen markieren.
#. Wenn Sie ein individuelles Theme oder ein angepasstes OXID-Theme verwenden, tun Sie Folgendes:
   a. Identifizieren Sie den CSS-Selektor der Seite, hinter dem Sie den Banner platzieren wollen.
   b. Geben Sie den CSS-Selektor in entsprechende Eingabefeld ein.
#. Legen Sie unter :guilabel:`Farbe des Ratenzahlung-Banners auswählen` die gewünschte Farbe des Banners fest.
#. Speichern Sie Ihre Einstellungen.


PayPal Checkout testen
----------------------

Konfigurieren Sie PayPal Checkout nach Ihren Wünschen und testen Sie das Ergebnis.

|procedure|

.. todo: #Mario: Wie schalte ich Logging ein? Sollten einmal Probleme auftauchen, kann für eine intensive Fehlersuche das Logging eingeschaltet werden.

.. todo: #Mario: Stimmt die folgende Aussage mit der Standardversandart?  Wie genau geht es, was meinen wir?


1. Stellen Sie sicher, dass unter :menuselection:`Stammdaten --> Länder` die Märkte aktiv sind, die Sie abdecken wollen.
#. Weisen Sie unter :menuselection:`Shopeinstellungen --> Zahlungsarten` den gewünschten PayPal Checkout-Zahlungsarten (beispielsweise :guilabel:`iDEAL (über PayPal)` jeweils mindestens eine Benutzergruppen zu.
#. Tun Sie unter :menuselection:`Shopeinstellungen --> Versandarten` Folgendes:

   a. Weisen Sie die gewünschten PayPal Checkout-Zahlungsarten den jeweiligen Versandarten zu.
   b. Stellen Sie sicher, dass eine Versandart als Standard für die Bezahlung mit der PayPal Checkout-Zahlungsart `PayPal v2` angelegt ist.
      |br|
      Diese Standard-Versandart ist nötig, damit Ihre Kunden mit einem mobilen Endgerät in Ihrem Shop bestellen können.

.. todo: #Mario: Was heißt das: "Die entsprechende Option finden Sie auf der Registerkarte :guilabel:`Stamm` der Versandarten.
   Weitere Informationen finden Sie unter `Zahlungsarten <https://docs.oxid-esales.com/eshop/de/6.0/einrichtung/zahlungsarten/zahlungsarten.html>`_ der Anwenderdokumentation des OXID eShop. Ändern Sie ggf. den Einkaufswert (€) in 0 bis 99999.

.. todo: #Mario: Stimmt das: "Diese Standard-Versandart ist nötig, damit Ihre Kunden mit einem mobilen Endgerät in Ihrem Shop bestellen können."

PayPal Checkout freischalten
----------------------------

Schalten Sie PayPal Checkout nach dem Testen frei.

|prerequisites|

Sie haben die gewünschten Zahlungsarten konfiguriert und mit Testzahlungen in der PayPal-Sandbox erfolgreich getestet.

|procedure|

1. Wählen Sie unter :guilabel:`API-Anmeldeinformationen` den Betriebsmodus :guilabel:`Live`.
#. Wählen Sie die Schaltfläche :guilabel:`Anmeldung Händler PayPal-Integration (Live)`.
   |br|
   Sie gelangen in ein Dialogfenster zum Anmelden bei PayPal.
#. Melden Sie sich mit Ihrem bestehenden PayPal-Händlerkonto an oder legen Sie ein PayPal-Händlerkonto neu an.


|result|

Die PayPal API-Anmeldeinformationen werden eingefügt.

Das Modul PayPal Checkout ist aktiv und steht für Bestellungen Ihrer Kunden bereit.



..  todo: #Mario: Ist Folgendes alles obsolet?
   Integration von PayPal
   ^^^^^^^^^^^^^^^^^^^^^^
   In diesem Bereich finden Sie einige Einstellungen, wie das Bezahlen mit PayPal in den OXID eShop integriert wird. Mit PayPal Basis wird PayPal am Ende des Bestellprozesses als Zahlungsart angeboten. Wählt der Kunde diese Zahlungsart, bestätigt er auf der PayPal-Zahlungsseite den Kauf und wird anschließend in den Shop zurückgeleitet. PayPal Express bietet die Möglichkeit, dass der Kunde schon im ersten Bestellschritt direkt zur PayPal-Zahlungsseite wechseln kann. Dort bestätigt er den Kauf und gelangt wieder in den Shop zurück. Der Shop übernimmt dabei die für den Kauf relevanten Kundendaten. Auch für den Mini-Warenkorb und die Artikel-Detailseite kann die Schaltfläche für PayPal Express aktiviert werden.

   Anzeige auf PayPal-Zahlungsseite
   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
   Geben Sie hier den Namen des Shops an, der auf der PayPal-Zahlungsseite angezeigt werden soll. Eine weitere Einstellung ermöglicht es, ein Logo des Shops anstatt des Namens auf der PayPal-Zahlungsseite anzuzeigen. Die Grafik dafür sollte eine maximale Größe (Breite*Höhe) von 190px*60px haben und im Verzeichnis :file:`/out/{theme}/img` gespeichert sein. Für jedes verwendete Theme muss die Datei im jeweiligen Verzeichnis existieren. Das Shop-Logo kann das standardmäßig im Shop verwendete sein. Dieses wird mit dem Parameter "sShopLogo" in der Konfigurationsdatei :file:`config.inc.php` definiert. Es kann aber auch ein spezielles Shop-Logo auf der PayPal-Zahlungsseite angezeigt werden, dessen Dateiname hier angegeben wird.

   Warenkorb auf PayPal-Zahlungsseite
   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
   Artikel, die sich im Warenkorb befinden, lassen sich auf der PayPal-Zahlungsseite mit Titel, Artikelnummer und Artikelpreis anzeigen. Dies ist eine generelle Einstellung, welcher der Kunde jedoch bei der Bestellung zustimmen muss. Ob er dabei explizit ein Häkchen setzen muss oder ob die Option zur Anzeige des Warenkorbs auf der PayPal-Zahlungsseite bereits aktiviert ist, kann ebenfalls festgelegt werden. Wir empfehlen, dass der Warenkorb zu PayPal zu übertragen wird und die Option zur Zustimmung des Kunden standardmäßig aktiviert ist.

   #Mario: müsste ich nicht konfigurieren können, ob der Button "Später bezahlen" erscheint oder nicht?

   Geldeinzug
   ^^^^^^^^^^
   Für den Zeitpunkt, zu dem das Geld eingezogen wird, gibt es grundsätzlich zwei Methoden. PayPal kann den Betrag zum einen sofort beim Kauf vom Kundenkonto einziehen (SALE). Zum anderen wird das Kundenkonto bei Kauf geprüft und die Zahlung wird autorisiert (AUTH). Der Shopbetreiber kann innerhalb von 29 Tagen, beispielsweise vor Versand der Ware, den reservierten Betrag manuell einziehen. Versenden Sie die Ware immer erst dann, wenn der PayPal-Status "Completed" ist.

   Der OXID eShop kann darüber hinaus den Zeitpunkt des Geldtransfers automatisch wählen (AUTOMATIC). Grundlage dafür ist der Lagerbestand der bestellten Artikel und ein definierter Restlagerbestand. Es wird geprüft, ob nach einer Bestellung der Lagerbestand eines der Artikel kleiner als der definierte Restlagerbestand ist. In diesem Fall wird AUTH als Methode des Geldtransfers verwendet, ansonsten SALE.



.. Intern: oxdaac, Status: