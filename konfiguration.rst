Konfiguration
=============

Machen Sie das Modul :productname:`PayPal Checkout` für Ihren OXID eShop betriebsbereit.

Sie haben bereits PayPal oder PayPal Plus?
------------------------------------------

Sorgen Sie für einen reibungslosen beim Übergang zum neuen Modul :productname:`PayPal Checkout`.

Beachten Sie dazu die beiden folgenden Einschränkungen:

* Sie können :productname:`PayPal Checkout` nicht mit Ihren :productname:`PayPal Plus`-Zugangsdaten betreiben.
  |br|
  Folgen Sie den Anweisungen unter :ref:`konfiguration:Registrierung für PayPal Checkout neu durchlaufen`.
* Um bereits existierende Bestellungen verwalten zu können, müssen beide Module, beispielsweise :productname:`PayPal Checkout` und :productname:`PayPal`, gleichzeitig aktiv sein.
  |br|
  Folgen Sie den Anweisungen unter :ref:`konfiguration:Existierende PayPal- oder PayPal Plus-Bestellungen verwalten`.

Registrierung für PayPal Checkout neu durchlaufen
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Wenn Sie :productname:`PayPal Plus` haben, beachten Sie Folgendes:

Die Zugangsdaten und der Anmeldeprozess von :productname:`PayPal Checkout` sind äußerlich ähnlich wie bei :productname:`PayPal Plus`.

Lassen Sie sich dadurch jedoch nicht dazu verleiten, die Zugangsdaten von :productname:`PayPal Plus` wiederzuverwenden.

Dies würde zu folgenden Enttäuschungen führen:

* Die Webhooks werden nicht korrekt aktiviert, Informationen werden nicht korrekt übermittelt, ohne dass jedoch die Fehler sofort erkennbar sind.
* Zahlungsarten wie Ratenkauf stehen nicht zur Verfügung, die Zahlung mit Kreditkarte wird nicht freigeschaltet.

|procedure|

Tun Sie Folgendes:

1. Testen Sie :productname:`PayPal Checkout` in der PayPal-Sandbox mit :emphasis:`Test`-Konten wie beschrieben unter :ref:`konfiguration:PayPal Checkout konfigurieren`.
#. Generieren Sie für das Freischalten Ihres :emphasis:`Live`-Systems die Zugangsdaten neu.
   |br|
   Durchlaufen Sie dazu den PayPal-Registrierungs-Prozess mit Ihren PayPal-Geschäftskontodaten erneut.

Existierende PayPal- oder PayPal Plus-Bestellungen verwalten
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Wenn Sie bereits das Modul :productname:`PayPal` oder :productname:`PayPal Plus` nutzen, beachten Sie folgende Einschränkung:

Um bereits existierende Bestellungen verwalten zu können, müssen beide Module, beispielsweise :productname:`PayPal Checkout` und :productname:`PayPal` gleichzeitig aktiv sein.

Damit jedoch in unserem Beispiel die Zahlungsart PayPal im Frontend nicht redundant angezeigt wird, müssen Sie die :emphasis:`Zahlungsart` :guilabel:`PayPal` deaktivieren.

|procedure|

Wir empfehlen folgendes Vorgehen.

.. tip::

   **Downtime einplanen**

   Planen Sie für den Schritt des Deaktivierens der zu :productname:`PayPal` oder :productname:`PayPal Plus` gehörenden Zahlungsart eine kurze Downtime ein.

1. Installieren Sie :productname:`PayPal Checkout`.
#. Aktivieren und konfigurieren Sie :productname:`PayPal Checkout` wie im Folgenden unter :ref:`konfiguration:Grundsätzliches Vorgehen` beschrieben.
   |br|
   Resultat: Um Ihre Bestellungen zu verwalten, finden Sie unter :menuselection:`Bestellungen verwalten --> Bestellungen` separate Registerkarten für die Module :productname:`PayPal Checkout` sowie für :productname:`PayPal` oder :productname:`PayPal Plus` (je nach dem, welches der beiden Module Sie nutzen).

   ..  note::

       **Bestellungen im PayPal-Händlerkonto verwalten**

       Schiefgehen kann nichts, wenn Sie wie im Folgenden beschrieben :productname:`PayPal` oder :productname:`PayPal Plus` deaktivieren.

       Sie können Bestellungen jederzeit in Ihrem PayPal-Händlerkonto verwalten.

       **Technische Abhängigkeiten**

       Auf der separaten Registerkarte für :productname:`PayPal` oder :productname:`PayPal Plus` können Sie Ihre alten Bestellungen so lange :emphasis:`bearbeiten`, bis Sie Ihr bisher genutztes Modul deaktivieren.

       Sobald Sie Ihr bisher genutztes Modul deaktivieren, können Sie Ihre alten Bestellungen auf der Registerkarte :guilabel:`PayPal Checkout` noch :emphasis:`anzeigen`, aber :emphasis:`nicht` bearbeiten.

       Wenn Sie nach dem Deaktivieren Ihres bisher genutzten Moduls Ihr System aufräumen und deshalb auch die Datenbank des Moduls löschen, werden Ihre alten Bestellungen auch auf der Registerkarte :guilabel:`PayPal Checkout` nicht mehr angezeigt.

       Nach dem Löschen der Datenbank können Sie Ihre alten Bestellungen weiterhin im PayPal-Händlerkonto anzeigen und verwalten.

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




Grundsätzliches Vorgehen
------------------------

1. Aktivieren Sie das Modul.
   |br|
   Die wichtigsten Zahlungsmethoden sind damit automatisch aktiviert.
#. Stellen Sie über einen Webhook die Verbindung zu PayPal her.

   .. attention::

      * Benutzen Sie zum Herstellen der Verbindung nicht die Zugangsdaten für :productname:`PayPal Plus`.
      * Testen Sie :productname:`PayPal Plus` zunächst in der PayPal-Sandbox.

#. Optional: Deaktivieren Sie bei Bedarf die Express-Checkout-Funktion von :productname:`PayPal Checkout`.
#. Optional: Legen Sie fest, ob Sie Ihren Kunden die PayPal-Ratenzahlung anbieten wollen.
#. Konfigurieren Sie die von :productname:`PayPal Checkout` bereitgestellten Zahlungsmethoden als Zahlungsarten in Ihrem eShop:

   * Aktivieren Sie die Länder, die Sie abdecken wollen.
   * Verknüpfen Sie die Zahlungsarten mit Ihren Versandarten und Versandkostenregeln.

#. Führen Sie Testzahlungen in der :productname:`PayPal Checkout`-Sandbox aus.
#. Testen Sie :productname:`PayPal Checkout` in der PayPal-Sandbox und passen Sie die Konfiguration an, bis alle Zahlungsprozess nach Ihren Vorstellungen funktionieren.
#. Schalten Sie :productname:`PayPal Checkout` frei:

   a. Wenn Sie noch kein Händlerkonto haben, legen Sie für den Livebetrieb eins an.
   b. Wechseln Sie in den Betriebsmodus :guilabel:`Live`.


PayPal Checkout aktivieren
--------------------------

Stellen Sie sicher, dass :productname:`PayPal Checkout` in jedem Subshop aktiviert ist, in dem Sie das Modul nutzen wollen.

|procedure|

1. Wählen Sie :menuselection:`Erweiterungen --> Module`. 
2. Wählen Sie das Modul :guilabel:`PayPal Checkout für OXID` und wählen Sie :menuselection:`Stamm --> Aktivieren`.


|result|

Unter :menuselection:`Shopeinstellungen --> Zahlungsarten` sind die Zahlungsarten :guilabel:`PayPal` sowie wichtige weitere Zahlungsarten als aktiv gekennzeichnet.

Um eine bestimmte länderspezifische Zahlungsart tatsächlich nutzen zu können, müssen Sie unter :menuselection:`Stammdaten --> Länder` das betreffende Land als aktiv markiert haben.

|example|

Um iDEAL anbieten zu können, müssen Sie sichergestellt haben, dass Sie unter :menuselection:`Stammdaten --> Länder` die Niederlande aktiv gesetzt haben.


PayPal Checkout konfigurieren
-----------------------------

Um die Konfiguration zu starten, wählen Sie :menuselection:`PayPal --> Konfiguration`. 



API-Anmeldeinformationen
^^^^^^^^^^^^^^^^^^^^^^^^

Registrieren Sie einen Webhook, um Ihren eShop mit PayPal zu verbinden.

Der Webhook erlaubt es PayPal, Ihren OXID eShop zu kontaktieren und in Echtzeit Statusmeldungen beispielsweise über abgeschlossene Transaktionen zu liefern.

Im ersten Durchgang testen Sie die mit :productname:`PayPal Checkout` bereitgestellten Zahlungsarten mit Test-Zugangsdaten in einer *Sandbox*.

.. hint::

   **Was bringt mir das Testen in der Sandbox?**

   `sandbox.paypal.com` ist ein Spiegel-System.
   |br|
   Alle Funktionen und die API sind identisch zu `sandbox.paypal.com`.

   Das heißt: Jeden Fehler, den Sie hier erzeugen können, wird es auch im Live-System geben.
   |br|
   Umgekehrt: Jeder nicht erzeugte Fehler tritt auch im Produktions-System nicht auf.

   Testen Sie Ihre :productname:`PayPal Checkout`-Integration deshalb zuerst mit einem Sandbox-System.

   Es kann nichts schiefgehen:

   * Testzahlungen in der Sandbox kosten nichts.
   * Sie vermeiden Rückbuchungen wie sie bei Testzahlungen mit dem Live-Konto nötig wären.

Erst wenn alles nach Ihren Vorstellungen funktioniert, nutzen Sie die Zugangsdaten für den *Live*-betrieb.

|prerequisites|

* Sie haben auf der Entwickler-Seite von PayPal ein Sandbox-Händlerkonto und ein Sandbox-Kundenkonto eingerichtet.
  |br|
  Weitere Informationen finden Sie unter :ref:`paypal-sandbox:PayPal-Sandbox-Accounts generieren`.

* Ihre Testumgebung hat SSL.
  |br|
  Wenn Sie :productname:`PayPal Checkout` in einer lokalen Entwicklungs-Umgebung testen, die nur über :technicalname:`http://` erreichbar ist (also :emphasis:`ohne SSL` über :technicalname:`https://`), dann benutzen Sie beispielsweise NGROK, um Ihre Testumgebung mit temporärem SSL auszustatten.
  |br|
  Weitere Informationen finden Sie unter :ref:`paypal-sandbox:Temporäres SSL einrichten`.


|procedure|

Wir beschreiben den Prozess am Beispiel eines Sandbox-Kontos. Der Live-Prozess ist analog.

1. Um sich auf der Sandbox anzumelden, wählen Sie unter :guilabel:`API-Anmeldeinformationen` die Schaltfläche :guilabel:`Händler PayPal-Integration (Sandbox) im neuen Fenster starten`.
#. Wählen Sie :guilabel:`Anmeldung Händler PayPal-Integration (Sandbox)`.
#. Durchlaufen Sie den Registrierungs-Prozess mit der E-Mail-Adresse des Sandbox-Händlerkontos.

   a. Melden Sie sich an (:ref:`oxdajr01`), und bestätigen Sie die Abfragen.

      .. todo: #tbd: screenshot EN

      .. _oxdajr01:

      .. figure:: /media/screenshots/oxdajr01.png
         :alt: Registrierung des Sandbox-Händler-Kontos starten

         Abb.: Registrierung des Sandbox-Händler-Kontos starten

   #. Wählen Sie zum Abschluss :guilabel:`Zurück zu John Doe`s Test Store` (:ref:`oxdajr03`).

      .. _oxdajr03:

      .. figure:: /media/screenshots/oxdajr03.png
         :alt: Registrierung des Händlerkontos abschließen

         Abb.: Registrierung des Händlerkontos abschließen

      Eine Meldung zeigt den Erfolg an (:ref:`oxdajr04`).

      .. _oxdajr04:

      .. figure:: /media/screenshots/oxdajr04.png
         :alt: Meldung Onboarding erfolgreich

         Abb.: Meldung Onboarding erfolgreich

#. Wechseln Sie zurück in Ihren OXID eShop.

   Der Webhook ist erzeugt.

   Die Client-ID und die Webhook-ID werden angezeigt (:ref:`oxdajr05`).

   .. _oxdajr05:

   .. figure:: /media/screenshots/oxdajr05.png
      :alt: Webhook erzeugt

      Abb.: Webhook erzeugt


#. Wenn Sie die Zahlungsmethoden Rechnungskauf oder Kreditkarte nutzen wollen, prüfen Sie unter :guilabel:`Freischaltung für besondere Zahlarten erfolgt` (:ref:`oxdajr05`), ob die Freischaltung erfolgt ist.
   |br|
   Wenn die Freischaltung nicht automatisch erfolgt ist, wenden Sie sich an Ihren Ansprechpartner bei PayPal.

.. hint::

   **Zahlungsmethode Kreditkarte**

   Wenn die Freischaltung für die Zahlungsmethode Kreditkarte nicht automatisch erfolgt ist, dann erscheint die Zahlungsmethode als separate Schaltfläche :guilabel:`Kreditkarte` unter der PayPal-Schaltfläche.

   .. image:: media/screenshots/oxdajr02.png
       :alt: Zahlungsmethode Kreditkarte
       :class: no-shadow

   Ist die Freischaltung erfolgt, sieht Ihr Kunde die PayPal-Schalfläche, und die Zahlungsart Kreditkarte steht im Checkout-Schritt Versand & Zahlungsart zur Verfügung.

   .. image:: media/screenshots/oxdajr06.png
       :alt: Zahlungsmethode Kreditkarte
       :class: no-shadow

.. hint::

   **Zahlungsmethode Rechnungskauf**

   Die Zahlungsmethode Rechnungskauf bietet PayPal nur Shop-Betreibern aus Deutschland an.


|result|

Sobald Sie PayPal die Genehmigung erteilt haben, Ihr Sandbox-Konto mit dem
PayPal Test Store zu verbinden, werden die API-Anmeldeinformationen angezeigt, und das
Modul ist aktiv :ref:`oxdajr05`.

Unter :menuselection:`Shopeinstellungen --> Zahlungsarten` ist die Zahlungsart :guilabel:`PayPal` (technischer Name :technicalname:`oscpaypal`) aktiv (:ref:`oxdajr07`).

.

   .. _oxdajr07:

   .. figure:: /media/screenshots/oxdajr07.png
      :alt: Zahlungsart PayPal aktiv

      Abb.: Zahlungsart PayPal aktiv

.. hint::

   **Neuen Webhook generieren**

   Manchmal kann es nötig sein, den bestehenden Webhook zu löschen und einen neuen zu generieren.

   Um einen Webhook zu löschen, löschen Sie die Anmeldedaten und wählen :guilabel:`Speichern`.

   Die Schaltfläche :guilabel:`Anmeldung Händler PayPal-Integration` erscheint, und Sie können den Webhook neu generieren.


Einstellungen für die Buttonplatzierung: Schnellkauf-Funktion
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Entscheiden Sie, ob Sie die Schnellkauf-Funktion von :productname:`PayPal Checkout` anbieten wollen

Mit der Schnellkauf-Funktion überspringen Ihre Kunden die Anmeldung in Ihrem eShop.

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
* im Mini-Warenkorb (:ref:`oxdajr09`, Pos. 1)
* auf der Checkout-Seite

Ihre Kunden können also jederzeit mit ihrem PayPal-Konto die Bestellung auslösen.

Wenn Sie wollen, dass Ihre Kunden sich in Ihrem eShop registrieren müssen, deaktivieren Sie die Schnellkauf-Funktion.

.. todo: #tbd: Screenshot EN

.. _oxdajr09:

.. figure:: /media/screenshots/oxdajr09.png
   :alt: Mini-Warenkorb und Später bezahlen

   Abb.: Mini-Warenkorb und Später bezahlen

|procedure|

1. Um die Express-Checkout-Funktion zu deaktivieren, deaktivieren Sie die Kontrollkästchen :guilabel:`Produktdetailseite`, :guilabel:`Warenkorb` und :guilabel:`Warenkorb`.
#. Speichern Sie Ihre Einstellungen.

|Result|

Die PayPal-Schaltfläche erscheint nur auf der Checkout-Seite.

Einstellungen für die Buttonplatzierung: Später Bezahlen
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Entscheiden Sie, ob Sie die Später Bezahlen-Funktion (:ref:`oxdajr07`, Pos. 2) anbieten wollen

Später Bezahlen bedeutet beispielsweise, dass PayPal Kunden in Deutschland die Option "Bezahlung nach 30 Tagen" oder PayPal-Ratenzahlung anbietet.

Weitere Informationen über Länder-Abdeckung und landesspezifische Funktionen der Später Bezahlen-Funktion finden Sie unter `developer.paypal.com/docs/checkout/pay-later/de <https://developer.paypal.com/docs/checkout/pay-later/de/>`_.


|procedure|

1. Um Ihren Später Bezahlen-Funktionen anzubieten, aktivieren Sie das Kontrollkästchen :guilabel:`"Später Bezahlen"-Button anzeigen?`.
#. Speichern Sie Ihre Einstellungen.


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

Legen Sie fest, ob Sie mit Bannern für die PayPal-Ratenzahlung (:ref:`oxdajr08`) werben wollen.

Wenn Sie die Vorteile des Werbens für die PayPal-Ratenzahlung nutzen wollen, legen Sie fest, wo die Banner erscheinen sollen, beispielsweise auf der Startseite, auf der Detailseite von Artikeln, auf den Kategorieseiten, in den Suchergebnissen und/oder im Bestellprozess.

.. todo: #tbd: Screenshot EN

.. _oxdajr08:

.. figure:: /media/screenshots/oxdajr08.png
   :alt: Beispiel: Ratenzahlungs-Banner auf einer Kategorieseite

   Abb.: Beispiel: Ratenzahlungs-Banner auf einer Kategorieseite

.. attention::

   **Datenschutz**

   Um die Banner erscheinen zu lassen, ist eine permanente Kommunikation mit den Servern von PayPal nötig.

   Dazu werden bei jedem Seitenaufruf Skripte gestartet, die das Nutzerverhalten beobachten und die die für den PayPal-Bezahlprozess nötigen Informationen sammeln und an PayPal übermitteln.

   Diese Kommunikation kann unerwünscht sein, beispielsweise aus Gründen

      * des Datenschutzes
      * der Performance

   Stellen Sie in diesem Fall sicher, dass die Funktion deaktiviert ist.

   Standardmäßig ist die Funktion eingeschaltet.




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
      Beispiel: Der maximale Einkaufswert für die Zahlungsart :guilabel:`PayPal` ist standardmäßig auf 10.000 € begrenzt. Der Mindest-Einkaufswert ist 10 €.
#. Tun Sie unter :menuselection:`Shopeinstellungen --> Versandarten` Folgendes:

   a. Weisen Sie die gewünschten :productname:`PayPal Checkout`-Zahlungsarten den jeweiligen Versandarten zu.
   b. Stellen Sie sicher, dass mindestens eine Versandart für die Bezahlung mit der Zahlungsart :guilabel:`PayPal` angelegt ist.
      |br|
      Typischerweise ist das die Standard-Zahlungsart.

   Weitere Informationen finden Sie unter `Zahlungsarten <https://docs.oxid-esales.com/eshop/de/latest/einrichtung/zahlungsarten/zahlungsarten.html>`_ der Anwenderdokumentation des OXID eShop. Ändern Sie ggf. den Einkaufswert (€) in 0 bis 99999.

.. todo: #tbd: For more info... auf EN nachziehen

PayPal Checkout freischalten
----------------------------

Schalten Sie :productname:`PayPal Checkout` nach dem Testen frei.

.. attention::

   **Keine PayPal Plus-Zugangsdaten verwenden**

   Sie haben bereits :productname:`PayPal Plus`? Dann verwenden Sie die Zugangsdaten **nicht** für :productname:`PayPal Checkout`.

   Generieren Sie die Zugangsdaten für :productname:`PayPal Checkout` wie im Folgenden beschrieben mit Ihrem PayPal-Händlerkonto neu.

|prerequisites|

* Sie haben die gewünschten Zahlungsarten konfiguriert und mit Testzahlungen in der PayPal-Sandbox erfolgreich getestet (siehe :ref:`konfiguration:PayPal Checkout testen`).

|procedure|

1. Wählen Sie unter :guilabel:`API-Anmeldeinformationen` den Betriebsmodus :guilabel:`Live`.
#. Wählen Sie die Schaltfläche :guilabel:`Anmeldung Händler PayPal-Integration (Live)`.
   |br|
   Sie gelangen in ein Dialogfenster zum Anmelden bei PayPal.
#. Melden Sie sich mit Ihrem bestehenden PayPal-Händlerkonto an.
   |br|
   Wenn Sie noch keine Zugangsdaten für den Live-Betrieb haben, legen Sie ein PayPal-Händlerkonto neu an.
#. Speichern Sie Ihre Einstellungen.
#. Wenn Sie :productname:`PayPal` oder :productname:`PayPal Plus` nutzen, folgen Sie den Empfehlungen unter :ref:`konfiguration:Existierende PayPal- oder PayPal Plus-Bestellungen verwalten`.

|result|

Die PayPal API-Anmeldeinformationen werden eingefügt.

Das Modul :productname:`PayPal Checkout` ist aktiv und steht für Bestellungen Ihrer Kunden bereit.



.. Intern: oxdajr, Status: