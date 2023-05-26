Konfiguration
=============

Machen Sie das Modul :productname:`PayPal Checkout` für Ihren OXID eShop betriebsbereit.

Sie haben bereits PayPal oder PayPal Plus?
------------------------------------------

Sorgen Sie für einen reibungslosen Übergang zum neuen Modul :productname:`PayPal Checkout`.

Beachten Sie dazu die beiden folgenden Einschränkungen:

* Sie können :productname:`PayPal Checkout` nicht mit Ihren :productname:`PayPal Plus`-Zugangsdaten betreiben.
  |br|
  Folgen Sie den Anweisungen unter :ref:`konfiguration:PayPal-Registrierung für PayPal Checkout neu durchlaufen`.
* Um bereits existierende Bestellungen verwalten zu können, müssen beide Module, beispielsweise :productname:`PayPal Checkout` und :productname:`PayPal`, gleichzeitig aktiv sein.
  |br|
  Folgen Sie den Anweisungen unter :ref:`konfiguration:Existierende PayPal- oder PayPal Plus-Bestellungen verwalten`.

PayPal-Registrierung für PayPal Checkout neu durchlaufen
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Wenn Sie :productname:`PayPal Plus` haben, beachten Sie Folgendes:

Die Zugangsdaten und der Anmeldeprozess von :productname:`PayPal Checkout` sind äußerlich ähnlich wie bei :productname:`PayPal Plus`.

Lassen Sie sich dadurch jedoch nicht dazu verleiten, die Zugangsdaten von :productname:`PayPal Plus` wiederzuverwenden.

Dies würde zu den folgenden unerwünschten Verhalten führen:

* Die Webhooks werden nicht korrekt aktiviert, Informationen werden nicht korrekt übermittelt, ohne dass jedoch die Fehler sofort erkennbar sind.
* Zahlungsarten wie Ratenkauf stehen nicht zur Verfügung, die Zahlung mit Kreditkarte wird nicht freigeschaltet.

|procedure|

Tun Sie Folgendes:

1. Testen Sie :productname:`PayPal Checkout` in der PayPal-Sandbox mit :emphasis:`Test`-Konten wie beschrieben unter :ref:`konfiguration:PayPal Checkout konfigurieren`.
#. Generieren Sie für das Freischalten Ihres :emphasis:`Live`-Systems die Zugangsdaten neu.
   |br|
   Durchlaufen Sie dazu den PayPal-Registrierungs-Prozess mit Ihren PayPal-Händlerkonto-Daten erneut.


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

.. include:: /_static/reuse/note-ee-onboarding.rst


1. Aktivieren Sie das Modul.
   |br|
   Die wichtigsten Zahlungsmethoden sind damit automatisch aktiviert.
#. Stellen Sie über einen Webhook die Verbindung zu PayPal her.

   .. attention::

      * Benutzen Sie zum Herstellen der Verbindung nicht die Zugangsdaten für :productname:`PayPal Plus`.
      * Testen Sie :productname:`PayPal Plus` zunächst in der PayPal-Sandbox.

#. Optional: Deaktivieren Sie bei Bedarf die Express-Checkout-Funktion von :productname:`PayPal Checkout`.
#. Optional: Legen Sie fest, ob Sie Ihren Kunden die PayPal-Ratenzahlung anbieten wollen (siehe :ref:`oxdajr08`).
#. Kontaktieren Sie bei Bedarf den PayPal-Kundenservice, um das für Ihren Fall optimale Verfahren festzulegen, wie PayPal mit der 3D Secure-Authentifizierung umgeht (siehe :ref:`oxdajr11`).
#. Konfigurieren Sie die von :productname:`PayPal Checkout` bereitgestellten Zahlungsmethoden als Zahlungsarten in Ihrem eShop:

   * Aktivieren Sie die Länder, die Sie abdecken wollen.
   * Verknüpfen Sie die Zahlungsarten mit Ihren Versandarten und Versandkostenregeln.

#. Führen Sie Testzahlungen in der :productname:`PayPal Checkout`-Sandbox aus. und passen Sie die Konfiguration an, bis alle Zahlungsprozess nach Ihren Vorstellungen funktionieren.
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

.. note::

   Um das Modul konfigurieren zu können, muss dieses zunächst aktiviert werden.
   Nach der Aktivierung erscheint links in der Navigation der neue Menüpunkt **PayPal**.


API-Anmeldeinformationen
^^^^^^^^^^^^^^^^^^^^^^^^

Registrieren Sie einen Webhook, um Ihren eShop mit PayPal zu verbinden.

Der Webhook erlaubt es PayPal, Ihren OXID eShop zu kontaktieren und in Echtzeit Statusmeldungen beispielsweise über abgeschlossene Transaktionen zu liefern.

.. hint::

  .. todo: #tbd: gehört zu x.2 *und* x.3: also als separaten branch anlegen
        **#tbd: Überschrift**
        Prüfen: Hinweis in EN vorhanden?
        Beispiel: etwas funktioniert nicht: debug einschalten: standard $this->sLogLevel = 'error';; wenn PP support fragt, OXD eshop log

  Wenn die Webhooks des Moduls geprüft werden müssen, dann bietet es sich an, den Parameter `$this->sLogLevel` in der Datei `config.inc.php` auf den Wert `debug` zu setzen.

  Auf diese Weise werden die an den Shop gesendeten Webhook Calls von PayPal im Log `oxideshop.log` aufgezeichnet.

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

.. include:: /_static/reuse/note-ee-onboarding.rst


.. hint::

   **Verfügbarkeit aller Zahlungsarten**

   Damit Ihnen :emphasis:`alle` PayPal-Zahlungsarten zur Verfügung stehen, generieren Sie den Webhook wie im Folgenden beschrieben mit der Schaltfläche :guilabel:`Anmeldung Händler PayPal-Integration (Sandbox)`.

   Hintergrund: Technisch ist es auch möglich, bereits existierende Anmeldeinformationen :emphasis:`manuell` einzugeben, statt sie neu zu generieren. Aber das würde zu Enischränkungen führen (siehe :ref:`troubleshooting:"Kreditkarte" und "Rechnungskauf" nicht verfügbar`).



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

   Die Client-ID und die Webhook-ID werden angezeigt (:ref:`oxdajr05`, Pos. 1, 2).

   .. todo: #tbd: Bild neu en; oxdajr06 entfällt

   .. _oxdajr05:

   .. figure:: /media/screenshots/oxdajr05.png
      :alt: Webhook erzeugt
      :width: 650
      :class: with-shadow

      Abb.: Webhook erzeugt

   .. _freischaltung-kreditkarte:

#. Wenn Sie Ihren Kunden die Zahlungsmethoden Rechnungskauf oder Kreditkarte anbieten wollen, prüfen Sie unter :guilabel:`Freischaltung für besondere Zahlarten erfolgt` (:ref:`oxdajr05`, Pos. 3), ob die Freischaltung erfolgt ist.

   .. todo: #tbd: Fallback-Lösung einbauen EN

   .. hint::

      **Zahlungsmethode Fallback-Kreditkarte**

      Wenn die Freischaltung :emphasis:`nicht` automatisch erfolgt ist (:guilabel:`Kreditkarte: Nein`), wenden Sie sich an Ihren Ansprechpartner bei PayPal.

      Ist die Freischaltung erfolgt, steht die Zahlungsart Kreditkarte im Checkout-Schritt Versand & Zahlungsart zur Verfügung (:ref:`oxdajr02`, Pos. 1).

      Wenn eine Freischaltung nicht möglich ist, steht alternativ eine Fallback-Lösung bereit (:ref:`oxdajr02`, Pos. 2).

      .. _oxdajr02:

      .. figure:: media/screenshots/oxdajr02.png
         :alt: Kreditkarten-Optionen und SEPA
         :width: 650
         :class: with-shadow

         Abb.: Kreditkarten-Optionen und SEPA


   .. hint::

      **Zahlungsmethode Rechnungskauf**

      Die Zahlungsmethode Rechnungskauf bietet PayPal nur Shop-Betreibern aus Deutschland an.


|result|

Sobald Sie PayPal die Genehmigung erteilt haben, Ihr Sandbox-Konto mit dem PayPal-Test Store zu verbinden, werden die API-Anmeldeinformationen angezeigt, und das Modul ist aktiv :ref:`oxdajr05`.

Unter :menuselection:`Shopeinstellungen --> Zahlungsarten` ist die Zahlungsart :guilabel:`PayPal` (technischer Name :technicalname:`oscpaypal`) aktiv (:ref:`oxdajr07`).

   .. _oxdajr07:

   .. figure:: /media/screenshots/oxdajr07.png
      :alt: Zahlungsart PayPal aktiv

      Abb.: Zahlungsart PayPal aktiv

Die Zahlungsarten "Kreditkarte" und "Rechnungskauf" stehen nicht zur Verfügung? Folgen Sie den Anweisungen unter :ref:`troubleshooting:"Kreditkarte" und "Rechnungskauf" nicht verfügbar`.

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

1. Um die Schnellkauf-Funktion von :productname:`PayPal Checkout` zu deaktivieren, deaktivieren Sie die Kontrollkästchen :guilabel:`Produktdetailseite`, :guilabel:`Warenkorb` und :guilabel:`Mini-Warenkorb` (:ref:`oxdajr10`, Pos. 1).
#. Speichern Sie Ihre Einstellungen.

.. _oxdajr10:

.. figure:: /media/screenshots/oxdajr10.png
   :alt: Anzeige der PayPal-Buttons steuern

   Abb.: Anzeige der PayPal-Buttons steuern

|Result|

Die PayPal-Schaltfläche erscheint nur auf der Checkout-Seite.

Einstellungen für die Buttonplatzierung: Später Bezahlen
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Entscheiden Sie, ob Sie die Später Bezahlen-Funktion (:ref:`oxdajr09`, Pos. 2) anbieten wollen

Später Bezahlen bedeutet beispielsweise, dass PayPal Kunden in Deutschland die Option "Bezahlung nach 30 Tagen" oder PayPal-Ratenzahlung anbietet.

Weitere Informationen über Länder-Abdeckung und landesspezifische Funktionen der Später Bezahlen-Funktion finden Sie unter `developer.paypal.com/docs/checkout/pay-later/de <https://developer.paypal.com/docs/checkout/pay-later/de/>`_.


|procedure|

1. Um Ihren Kunden Später Bezahlen-Funktionen anzubieten, aktivieren Sie das Kontrollkästchen :guilabel:`"Später Bezahlen"-Button anzeigen?` (:ref:`oxdajr10`, Pos. 2).
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

Geldeinzug festlegen
^^^^^^^^^^^^^^^^^^^^

Legen Sie für die Zahlungsart :guilabel:`PayPal` fest, ob Zahlungen sofort eingezogen werden sollen, oder ob die Zahlungen für maximal 30 Tage aufgeschoben werden sollen.


|example|

Typischerweise wird der Rechnungsbetrag sofort eingezogen.

In bestimmten Fällen ist es jedoch sinnvoll, dass die Zahlung erst durch die Auslieferung ausgelöst wird:

* Sie vertreiben bestimmte individualisierte Produkte, die Sie erst nach Eingang der Bestellung herstellen, in Auftrag geben oder bestellen.
* Sie haben einen eShop für Geschäftskunden. Hier sind die Liefermengen und Zahlungsbeträge größer als bei Privatkunden.
  |br|
  Im Fall eines Fehlers wäre das Retourenmanagement entsprechend schwieriger.
  |br|
  Deshalb wollen Sie sicherstellen, dass die Zahlung nur ausgelöst wird, wenn die Ware da oder auf dem Weg zum Versand ist.

.. important::

   Sie müssen das Produkt innerhalb von 30 Tagen liefern und die Transaktion beenden oder mit dem Kunden gemeinsam eine Lösung finden.

   Hintergrund: Durch das Bestellen ist PayPal initial für 3 Tage autorisiert, das Geld bei Ihrem Kunden einzuziehen. Die Autorisierung wird bis maximal 29 Tage nach Bestellung automatisch verlängert.

   Nach dreißig Tagen verfällt die Autorisierung, und PayPal kann den Rechnungsbetrag nicht mehr einziehen.


|procedure|

1. Sie haben unter :guilabel:`PayPal Standard - Geldeinzug` (:ref:`oxdajr12`) folgende Möglichkeiten:

   * Damit Zahlungen immer direkt ausgelöst werden, wählen Sie :guilabel:`Direkt`.
   * Um die Zahlung nur zu reservieren und später auszulösen, haben Sie folgende Möglichkeiten:

     * :guilabel:`automatisch bei Lieferung`: Die Zahlung wird ausgelöst, sobald Sie in Ihrem eShop den bestellten Artikel auf den Status :technicalname:`Geliefert` gesetzt haben.
     * :guilabel:`manuell`: Die Zahlung wird ausgelöst, wenn Sie unter :menuselection:`Bestellungen verwalten --> Bestellungen` die Bestellung wählen und auf der Registerkarte :guilabel:`PayPal Checkout` die Schaltfläche :guilabel:`Einziehen` wählen.

#. Speichern Sie Ihre Einstellungen.
#. Stellen Sie sicher, dass Sie die den individualisierten Produkten in Ihrem eShop nur die Zahlungsart :guilabel:`PayPal` zugeordnet haben.

   Die verzögerte Zahlung für Zahlungen mit :productname:`PayPal Checkout` greift für alle Artikel in Ihrem eShop, denen Sie diese Zahlungsart zugeordnet haben.

   .. todo: #ES/#ML: Wie ordne ich eine Zahlungsart/Versandkostenregel  exklusiv einem Artikel zu?

   Für die :emphasis:`Schnellkauf`-Funktion von :productname:`PayPal Checkout` (Zahlungsart :guilabel:`PayPal Express`) ist das Reservieren nicht möglich. Der Rechnungsbetrag wird bei der Zahlungsart :guilabel:`PayPal Express` immer sofort eingezogen.

.. _oxdajr12:

.. figure:: /media/screenshots/oxdajr12.png
   :alt: Verzögerte Zahlung konfigurieren
   :width: 650
   :class: with-shadow

   Abb.: Verzögerte Zahlung konfigurieren

.. todo: #tbd: EN: result erg.:

|result|

Unter :menuselection:`Bestellungen verwalten --> Bestellungen` können Sie den Rechnungsbeträge manuell einziehen (siehe :ref:`betrieb:Reservierte Zahlung auslösen`.


3D Secure für Debit- und Kreditkarten konfigurieren
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Um die gesetzlichen Anforderungen an Online-Zahlungen mit Kreditkarte zu erfüllen, nutzen Sie die 3D Secure-Authentifizierung.

Dabei wird der Kunde während der Transaktion von der ausstellenden Bank aufgefordert, sich durch Eingabe eines Passworts als rechtmäßiger Karteninhaber zu identifizieren.

Diese Authentifizierung durch die ausstellende Bank ist in bestimmten Situationen europaweit vorgeschrieben – etwa beim Hinterlegen einer Kreditkarte in ein E-Wallet (z.B. PayPal) oder bei riskanten Transaktionen.

Weitere Informationen über die die 3D Secure-Authentifizierung finden Sie unter `paypal.com/de/webapps/mpp/3dsecure-faqs <https://www.paypal.com/de/webapps/mpp/3dsecure-faqs>`_.

Sie haben folgende Möglichkeiten:

* Um die höchstmögliche Sicherheit zu erreichen, erzwingen Sie eine 3D Secure-Abfrage für jede Kreditkartentransaktion.
* Lassen Sie PayPal sicherstellen, dass 3D Secure nur im Bedarfsfall eingesetzt wird.
  |br|
  PayPal sorgt dafür, dass der Großteil Ihrer Kunden ungestört einkaufen kann.
* 3D Secure-Ergebnis ignorieren: Um zu erfahren, in welchen Fällen diese Einstellung für Sie sinnvoll sein kann, wenden Sie sich an den PayPal-Kundenservice unter `paypal.com/de/webapps/helpcenter/helphub/home/ <https://www.paypal.com/de/webapps/helpcenter/helphub/home/>`_.

|procedure|

1. Bei Bedarf: Um die für Ihre Zwecke optimale Einstellung zu bestimmen, kontaktieren Sie den PayPal-Kundenservice unter `paypal.com/de/webapps/helpcenter/helphub/home/ <https://www.paypal.com/de/webapps/helpcenter/helphub/home/>`_.
#. Wählen Sie die gewünschte Einstellung (:ref:`oxdajr11`).
#. Speichern Sie Ihre Einstellungen.

.. _oxdajr11:

.. figure:: /media/screenshots/oxdajr11.png
   :alt: 3D Secure-Authentifizierung konfigurieren

   Abb.: 3D Secure-Authentifizierung konfigurieren


Behandlung nicht beendeter Bestellungen festlegen
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Legen Sie fest, ob Sie unvollständige Bestellungen automatisch oder manuell löschen wollen.


-----------------------------------------------------------


|background|

Aus technischen Gründen erzeugt PayPal Bestellungen, auch wenn die Bestellungen am Ende nicht abgeschlossen werden.

Das ist der Fall, wenn der Kunde im Checkout die Schaltfläche :guilabel:`Zahlungspflichtig bestellen` wählt, sich dann aber nicht bei PayPal anmeldet und den Bezahlvorgang abschließt.

Weitere Informationen finden Sie unter :ref:`betrieb:Unvollständige Bestellungen manuell löschen`.

-----------------------------------------------------------

* Das :emphasis:`automatische` Löschen ist beispielsweise empfohlen, wenn Sie beispielsweise niedrigpreisige Massenartikel vertreiben.
  |br|
  Es wäre unbequem für Sie, zahlreiche unabgeschlossene Bestellungen einzeln manuell zu löschen.
* Das :emphasis:`manuelle` Löschen kann beispielsweise sinnvoll sein, wenn Sie hochpreisige Waren mit kleinen Absatzzahlen vertreiben.

  Springen Kunden während des Bestellprozesses ab, können Sie durch das manuelle Löschen feststellen, ob es eventuell Schwierigkeiten bei bestimmten PayPal-Zahlungsarten gibt.

|procedure|

.. todo: #tbd: EN: :guilabel:`Automatically delete not finished orders?`

1. Wenn das System unvollständige Bestellungen automatisch löschen soll, markieren Sie das Kontrollkästchen :guilabel:`Nicht beendete Bestellungen automatisch löschen?` (:ref:`oxdajr13`, Pos. 1).

   Passen Sie bei Bedarf die standardmäßige Rückhaltezeit von 60 Minuten an :ref:`oxdajr13`, Pos. 2).

#. Speichern Sie Ihre Einstellungen.

|result|

.. todo: #ML: Was ist das erwartete Ergebnis? Bestellungen mit Bezahlt = 0000-00-00 00:00:00 werden bei mir nicht gelöscht.

Wenn Sie das automatische Löschen deaktiviert lassen, müssen Sie unvollständige Bestellungen regelmäßig manuell löschen.

Weitere Informationen finden Sie unter :ref:`betrieb:Unvollständige Bestellungen manuell löschen`.

.. _oxdajr13:

.. figure:: /media/screenshots/oxdajr13.png
   :alt: Automatisches Löschen unvollständiger Bestellungen konfigurieren
   :width: 650
   :class: with-shadow

   Abb.: Automatisches Löschen unvollständiger Bestellungen konfigurieren


Banner-Einstellungen übernehmen
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Optional: Wenn Sie bereits das Modul :productname:`PayPal` nutzen, übernehmen Sie bequem die Bannereinstellungen für :productname:`PayPal Checkout`.

Alternativ: Legen Sie die Bannereinstellungen manuell fest wie beschrieben unter :ref:`konfiguration:Banner-Einstellungen`.

|prerequisites|

:productname:`PayPal` ist aktiviert.


|procedure|

1. Um die bestehende Einstellungen für die PayPal-Bannerwerbung zu übernehmen, wählen Sie die Schaltfläche :guilabel:`Einstellungen` aus dem klassischen PayPal-Modul übernehmen`.
   |br|
   Die Schaltfläche erscheint nur, wenn das Modul :productname:`PayPal` installiert ist.
#. Speichern Sie Ihre Einstellungen.


Banner-Einstellungen
^^^^^^^^^^^^^^^^^^^^

Legen Sie fest, ob Sie mit Bannern für die PayPal-Ratenzahlung (:ref:`oxdajr08`) werben wollen.

Wenn Sie die Vorteile des Werbens für die PayPal-Ratenzahlung nutzen wollen, legen Sie fest, wo die Banner erscheinen sollen, beispielsweise auf der Startseite, auf der Detailseite von Artikeln, auf den Kategorieseiten, in den Suchergebnissen und/oder im Bestellprozess.

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

Optional: Länderzuordnung von PayPal Checkout-Zahlungsmethoden konfigurieren
----------------------------------------------------------------------------

Stellen Sie sicher, dass bestimmte :productname:`PayPal Checkout`-Zahlungsmethoden ausschließlich in den von Ihnen gewünschten Ländern zur Verfügung stehen.

|background|

Bei der Erstinstallation sind den :productname:`PayPal Checkout`-Zahlungsmethoden automatisch die entsprechenden Länder zugeordnet.

Die meisten :productname:`PayPal Checkout`-Zahlungsmethoden decken mehrere Länder ab. Die Zahlungsmethode :productname:`Kreditkarte` beispielsweise ist Kunden weltweit zugänglich, die Zahlungsmethode :productname:`Pay Later` steht Ihren Kunden beispielsweise in Ländern in Europa, den USA und Australien zur Verfügung.

Weitere Informationen über die Länderabdeckung der einzelnen :productname:`PayPal Checkout`-Zahlungsmethoden finden Sie unter :ref:`einfuehrung:Marktabdeckung nach Zahlungsmethoden`.


Grundsätzlich gilt dabei: Die :emphasis:`Rechnungsadresse` und nicht die Lieferadresse eines Kunden bestimmt, ob eine :productname:`PayPal Checkout`-Zahlungsmethode dem Kunden zur Auswahl steht.
|br|
Beispiel: Nur Kunden mit einer Rechnungsadresse in Polen erhalten die Zahlungsmethode :productname:`Przelewy24` angeboten.


|procedure|

Um bei Bedarf die Zugänglichkeit einer :productname:`PayPal Checkout`-Zahlungsmethode auf bestimmte Länder einzuschränken, wählen Sie :menuselection:`Shopeinstellungen --> Zahlungsarten --> <Zahlungsart> --> Länder --> Länder zuordnen`.



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

   Weitere Informationen finden Sie unter `Zahlungsarten <https://docs.oxid-esales.com/eshop/de/latest/einrichtung/zahlungsarten/zahlungsarten.html>`_ der Anwenderdokumentation des OXID eShop.
   |br|
   Ändern Sie ggf. den Einkaufswert (€) in 0 bis 99999.


PayPal Checkout freischalten
----------------------------

Schalten Sie :productname:`PayPal Checkout` nach dem Testen frei.

.. attention::

   **Keine PayPal Plus-Zugangsdaten verwenden**

   Sie haben bereits :productname:`PayPal Plus`? Verwenden Sie in diesem Fall **nicht** die Zugangsdaten für :productname:`PayPal Checkout`.

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
