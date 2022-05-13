Konfiguration
=============


Machen Sie das Modul :productname:`PayPal Checkout` für Ihren OXID eShop betriebsbereit.


PayPal- oder PayPal Plus-Bestellungen verwalten
-----------------------------------------------

Wenn Sie bereits das Modul :productname:`PayPal` oder :productname:`PayPal Plus` nutzen, beachten Sie folgende Einschränkung:

Um bereits existierende Bestellungen verwalten zu können, müssen beide Module, beispielsweise :productname:`PayPal Checkout` und :productname:`PayPal` gleichzeitig aktiv sein.

Damit jedoch in unserem Beispiel die Zahlungsart PayPal im Frontend nicht redundant angezeigt wird, müssen Sie die :emphasis:`Zahlungsart` :guilabel:`PayPal` deaktivieren.

Wir empfehlen folgendes Vorgehen.

|procedure|

.. tip::

   **Downtime einplanen**

   Planen Sie für den Schritt des Deaktivierens der zu :productname:`PayPal`- oder :productname:`PayPal Plus` gehörenden Zahlungsart eine kurze Downtime ein.

1. Installieren Sie :productname:`PayPal Checkout`.
#. Aktivieren und konfigurieren Sie :productname:`PayPal Checkout` wie im Folgenden unter :ref:`konfiguration:Grundsätzliches Vorgehen` beschrieben.
   |br|
   Resultat: Um Ihre Bestellungen zu verwalten, finden Sie unter :menuselection:`Bestellungen verwalten --> Bestellungen` separate Registerkarten für die Module :productname:`PayPal Checkout` und :productname:`PayPal` oder :productname:`PayPal Plus`.
   |br|
   Die Bestellungen Ihres jeweiligen bereits genutzten Moduls, beispielsweise :productname:`PayPal`, können Sie auf der Registerkarte :guilabel:`PayPal Checkout` jedoch nur :emphasis:`anzeigen`.
   |br|
   :emphasis:`Aktionen` zur Bestellverwaltung, beispielsweise Rückerstattung, sind nur auf der Registerarte des Zahlungsmoduls möglich, das Sie bisher genutzt haben, beispielsweise :productname:`PayPal`.
#. Schalten Sie :productname:`PayPal Checkout` für den Live-Betrieb frei wie unter :ref:`konfiguration:PayPal Checkout freischalten`.
#. Wählen Sie :menuselection:`Shopeinstellungen --> Zahlungsarten`.
#. Identifizieren Sie die Zahlungsarten, die zu :productname:`PayPal` oder :productname:`PayPal Plus` gehören:

   * :guilabel:`PayPal` (ID: :technicalname:`oxidpaypal`)
   * :guilabel:`PayPal Plus` (ID: :technicalname:`payppaypalplus`)

   .. hint::

      Die ID wird in der linken unteren Ecke des Fensters angezeigt, wenn Sie mit der Maus über den Namen der Zahlungsart fahren.

#. Deaktivieren Sie die zu :productname:`PayPal` oder :productname:`PayPal Plus` gehörende Zahlungsart.
   |br|
   Dazu deaktivieren Sie auf der Registerkarte :guilabel:`Stamm` das Kontrollkästchen :guilabel:`Aktiv`.
   |br|
   Resultat: Das Modul :productname:`PayPal` oder :productname:`PayPal Plus` ist noch aktiv, aber die zugehörigen Zahlungsarten werden Ihren Kunden nicht mehr angeboten. Nur die Zahlungsarten von :productname:`PayPal Checkout` werden angeboten.
   |br|
   Sie können bereits existierende Bestellungen unter :menuselection:`Bestellungen verwalten --> Bestellungen` auf der betreffenden Registerkarte weiterhin wie gewohnt bearbeiten.
#. Empfohlen: Sobald Sie sicher sind, dass bei bestehenden Bestellungen keine Aktionen (beispielsweise Rückerstattung) mehr nötig sein werden, deaktivieren Sie :productname:`PayPal` oder :productname:`PayPal Plus` unter :menuselection:`Erweiterungen --> Module`.

   .. hint::

      **Bestellungen im PayPal-Händlerkonto verwalten**

      Schiefgehen kann nichts, wenn Sie :productname:`PayPal` oder :productname:`PayPal Plus` deaktivieren.

      Sie können Bestellungen jederzeit in Ihrem PayPal-Händlerkonto verwalten.


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
#. Schalten Sie :productname:`PayPal Checkout` frei:

   a. Wenn Sie noch kein Händlerkonto haben, legen Sie für den Livebetrieb eins an.
   b. Wechseln Sie in den Betriebsmodus :guilabel:`Live`.


PayPal Checkout aktivieren
--------------------------

Aktivieren Sie :productname:`PayPal Checkout` in jedem Subshop, in dem Sie das Modul nutzen wollen.

|procedure|

1. Wählen Sie :menuselection:`Erweiterungen --> Module`. 
2. Wählen Sie das Modul :guilabel:`PayPal Checkout für OXID` und wählen Sie :menuselection:`Stamm --> Aktivieren`.


|result|

Unter :menuselection:`Shopeinstellungen --> Zahlungsarten` sind die Zahlungsarten :guilabel:`PayPal v2` sowie wichtige weitere Zahlungsarten als aktiv gekennzeichnet.

Um eine bestimmte länderspezifische Zahlungsart tatsächlich nutzen zu können, müssen Sie unter :menuselection:`Stammdaten --> Länder` das betreffende Land als aktiv markiert haben.

|example|

Um iDEAL anbieten zu können, müssen Sie sichergestellt haben, dass Sie unter :menuselection:`Stammdaten --> Länder` die Niederlande aktiv gesetzt haben.




.. todo: #Bild ergänzen;
   .. image:: media/screenshots/oxdajr01.png
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
#. Durchlaufen Sie den Registrierungs-Prozess.
#. Wenn Sie die Zahlungsmethoden Rechnungskauf oder Kreditkarte nutzen wollen, prüfen Sie unter :guilabel:`Freischaltung für besondere Zahlarten erfolgt`, ob die Freischaltung erfolgt ist.
   |br|
   Wenn die Freischaltung nicht automatisch erfolgt ist, wenden Sie sich an Ihren Ansprechpartner bei PayPal.

.. todo: #ML: :guilabel:`Kreditkarte` bei Ablehnung

.. hint::

   **Zahlungsmethode Kreditkarte**

   Wenn die Freischaltung für die Zahlungsmethode Kreditkarte nicht automatisch erfolgt ist, dann erscheint die Zahlungsmethode als separate Schaltfläche :guilabel:`Kreditkarte` unter der PayPal-Schaltfläche.

   .. image:: media/screenshots/oxdajr02.png
       :alt: Zahlungsmethode Kreditkarte
       :class: no-shadow


.. hint::

   **Zahlungsmethode Rechnungskauf**

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

:emphasis:`Standardmäßig` ist die Schnellkauf-Funktion :emphasis:`aktiv`, und die PayPal-Schaltfläche erscheint auf folgenden Seiten:

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

Ihre Kunden überspringen damit den Anmeldemechanismus. Ihre Kunden melden sich in Ihrem OXID eShop an, :emphasis:`ohne ihr Passwort eingeben zu müssen`.


Nachteile:

* Oft nutzen beispielsweise Ehepartner dasselbe PayPal-Konto.
  |br|
  Einer der Partner könnte dadurch die Bestellhistorie oder andere Kundendaten des Partner im OXID eShop einsehen.
  |br|
  Potenziell besteht also ein Datenschutz-Risiko.
* Müssen sich Ihre Kunden nicht in Ihrem eShop anmelden, gehen Ihnen Daten zur Bestellhistorie der Kunden verloren.
  |br|
  Solche Daten könnten Sie andernfalls für statistische Auswertungen zur gezielten Ansprache Ihrer Kunden nutzen.


Wenn Sie :guilabel:`Login mit PayPal` :emphasis:`nicht` aktivieren, passiert Folgendes:

* Wenn die PayPal-E-Mail-Adresse des Kunden :emphasis:`bekannt` ist, wird der PayPal-Bezahlvorgang unterbrochen, und der Kunde muss sich in Ihrem eShop anmelden.
  |br|
  Die PayPal-Session ist erstellt, und Ihr Kunde ist in Ihrem eShop angemeldet.
  |br|
  Die Identität des Kunden steht eindeutig fest, und die aktuelle Bestellung wird zur Bestellhistorie des Kunden hinzugefügt.
* Wenn die PayPal-E-Mail-Adresse des Kunden :emphasis:`nicht` bekannt ist, führt Ihr Kunde die Bestellung mit einem Gast-Konto aus.
  |br|
  Ihr Kunde landet mit den PayPal-Adressdaten auf der Checkout-Seite. Die Daten werden nur für die aktuelle Bestellung einmalig gespeichert, es wird kein Kundenkonto im eShop angelegt.

.. todo: #tbd: Funktionsbeschreibung: Aspekt Bestellhistorie hinzufügen

|procedure|

.. ATTENTION::

   Die Funktion :guilabel:`Login mit PayPal` ist standardmäßig **aktiviert**.

1. Prüfen Sie, was im schlimmsten Fall schiefgehen kann, wenn mehrere Benutzer dasselbe PayPal-Konto nutzen und in Ihrem eShop die Daten der anderen Benutzer einsehen können.
2. Es besteht kein ernstes Risiko darin, wenn Ihre Kunden sich in Ihrem eShop bequem automatisch mit ihren PayPal-Konten anmelden?
   |br|
   Dann lassen Sie das Kontrollkästchen :guilabel:`Im Shop beim Kauf automatisch einloggen` aktiviert.
   |br|
   Andernfalls deaktivieren Sie das Kontrollkästchen.
3. Speichern Sie Ihre Einstellungen.


Banner-Einstellungen übernehmen
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Optional: Wenn Sie bereits das Modul :productname:`PayPal` nutzen, übernehmen Sie bequem die Bannereinstellungen für :productname:`PayPal Checkout`.

Alternativ: Legen Sie die Bannereinstellungen manuell fest wie beschrieben unter :ref:`konfiguration:Banner-Einstellungen festlegen`.

|prerequisites|

:productname:`PayPal` ist aktiviert.


|procedure|

1. Um die bestehende Einstellungen für die PayPal-Bannerwerbung zu übernehmen, wählen Sie die Schaltfläche :guilabel:`Einstellungen` aus dem klassischen PayPal-Modul übernehmen`.
   |br|
   Die Schaltfläche erscheint nur, wenn das Modul :productname:`PayPal` installiert ist.
#. Speichern Sie Ihre Einstellungen.


Banner-Einstellungen festlegen
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Legen Sie fest, ob Sie mit Bannern für die PayPal-Ratenzahlung werben wollen.

Wenn Sie die Vorteile des Werbens für die PayPal-Ratenzahlung nutzen wollen, legen Sie fest, wo die Banner erscheinen sollen, beispielsweise auf der Startseite, auf der Detailseite von Artikeln, auf den Kategorieseiten, in den Suchergebnissen und/oder im Bestellprozess.

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
   b. Stellen Sie sicher, dass Sie für die :productname:`PayPal Checkout`-Zahlungsarten auf der Registerkarte :guilabel:`Stamm` den jeweils gewünschten minimalen und maximalen Einkaufswert festgelegt haben.
      |br|
      Beispiel: Der maximale Einkaufswert für die Zahlungsart :guilabel:`PayPal v2` ist standardmäßig auf 10.000 € begrenzt. Der Mindest-Einkaufswert ist 10 €.
#. Tun Sie unter :menuselection:`Shopeinstellungen --> Versandarten` Folgendes:

   a. Weisen Sie die gewünschten :productname:`PayPal Checkout`-Zahlungsarten den jeweiligen Versandarten zu.
   b. Stellen Sie sicher, dass mindestens eine Versandart für die Bezahlung mit der Zahlungsart :guilabel:`PayPal v2` angelegt ist.
      |br|
      Typischerweise ist das die Standard-Zahlungsart.

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
#. Wenn Sie :productname:`PayPal` oder :productname:`PayPal Plus` nutzen, folgen Sie den Empfehlungen unter :ref:`konfiguration:PayPal- oder PayPal Plus-Bestellungen verwalten`.

|result|

Die PayPal API-Anmeldeinformationen werden eingefügt.

Das Modul :productname:`PayPal Checkout` ist aktiv und steht für Bestellungen Ihrer Kunden bereit.



.. Intern: oxdajr, Status: