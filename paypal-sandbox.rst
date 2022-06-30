:orphan:
PayPal Checkout in der PayPal-Sandbox testen
============================================

Um :productname:`PayPal Checkout` in der PayPal-Sandbox zu testen, legen Sie Sandbox-Konten an.

Wenn Sie :productname:`PayPal Checkout` in einem lokalen System ohne SSL testen, richten Sie dafür temporär SSL ein.


PayPal-Sandbox-Accounts generieren
----------------------------------

Um die Sandbox zu nutzen, tun Sie Folgendes:

* Zeigen Sie im PayPal-Entwickler-Portal die automatisch generierten Zugangsdaten für Ihre Personal- und Business-Sandbox-Konten an.
  |br|
  Mit dem Business-Konto (Sandbox-Händlerkonto) erzeugen Sie den Webhook und testen Sie Zahlungseingänge.
  |br|
  Mit dem Personal-Konto (Sandbox-Kundenkonto) führen Sie Testzahlungen aus.
* Optional: Testen Sie die PayPal-Sandbox-Accounts.

Zugangsdaten für Sandbox-Kunden- und Händler-Konto anzeigen
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Zeigen Sie die Zugangsdaten für Ihre Sandbox-Test-Konten im PayPal-Entwickler-Portal an.

|procedure|

1. Rufen Sie das PayPal-Entwickler-Portal unter `developer.paypal.com <https://developer.paypal.com/home>`_ auf.
#. Wählen Sie :guilabel:`Log Into Dashboard`.
#. Melden Sie sich mit den Zugangsdaten Ihres echten PayPal-Kontos an
   |br|
   Ihr PayPal-Konto kann ein Händler- oder Kunden-Konto sein. Nur für das Freischalten des Live-Betriebs werden Sie ein Händlerkonto brauchen.
#. Wählen Sie :menuselection:`Sandbox --> Accounts`.

|result|


Zwei Sandbox-Test-Konten werden angezeigt, ein Business-Sandbox-Konto (Händler-Konto) und ein Personal-Sandbox-Konto (Kunden-Konto) (:ref:`oxdaju01`).

.. _oxdaju01:

.. figure:: /media/screenshots/oxdaju01.png
   :alt: Business- und Personal-Sandbox-Konten anzeigen

   Abb.: Business- und Personal-Sandbox-Konto anzeigen


Legen Sie bei Bedarf weitere Sandbox-Konten zum Testen an.

Ändern Sie bei Bedarf unter :guilabel:`View/edit account` die Passwörter.

Optional: PayPal-Sandbox-Accounts testen
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Melden Sie sich mit den beiden Accounts auf dem PayPal-“Spiegel”-System, der Sandbox-Plattform, an.

|procedure|

Wählen Sie `sandbox.paypal.com <https://sandbox.paypal.com>`_. und melden Sie sich an.

|result|

Die Sandbox-Plattform ``sandbox.paypal.com`` wird angezeigt (in unserem Beispiel :ref:`oxdaju02` ein Sandbox-Händler-Konto).

Die Sandbox-Plattform ist technisch identisch mit dem Live-PayPal-System ``https://www.paypal.com``.

Beide Konten sind mit Sandbox-Geld-Guthaben, Sandbox-Kreditkarten und so weiter ausgestattet.

Wenn Sie im Modul den Sandbox-Onboarding-Prozess mit dem Sandbox-Händler-Konto (beispielsweise ``sb-abcde12345678@business.example.com``) starten, dann verbinden Sie Ihren Test-Shop mit diesem Business-Account.

Das heißt, Sie finden beispielsweise den angelegten Webhook des Moduls in diesem Sandbox-Händler-Konto auf ``sandbox.paypal.com``.

Wenn Sie im Frontend Zahlungen ausführen, nehmen Sie zum Bezahlen das Sandbox-Kunden-Konto (beispielsweise ``sb-fghijklm876544@personal.example.com``).

Nach dem Bezahlen sehen Sie in Ihrem Sandbox-Kunden-Konto (auf ``sandbox.paypal.com``) die Zahlungsabgänge und im Sandbox-Händler-Konto (auf ``sandbox.paypal.com``) die Zahlungszuflüsse.

Da ``sandbox.paypal.com`` ein Spiegelsystem ist, sind alle Funktionen und die API identisch.

D.h., jeden Fehler, den Sie hier erzeugen können, wird es im Live-System auch geben.

Umgekehrt: Jeder nicht erzeugte Fehler tritt auch im Live-System nicht auf.

Deshalb empfehlen wir dringend, die Integration zuerst mit einem Sandbox-System zu testen (siehe :ref:`konfiguration:PayPal Checkout testen`).

Erst wenn alles klappt, wiederholen Sie den Onboarding-Prozess im Live-System mit Ihrem PayPal-Händlerkonto (siehe :ref:`konfiguration:PayPal Checkout freischalten`).


.. _oxdaju02:

.. figure:: /media/screenshots/oxdaju02.png
   :alt: Business-Sandbox-Konto anzeigen

   Abb.: Business-Sandbox-Konto anzeigen

Temporäres SSL einrichten
-------------------------

Ihr Test-System hat kein SSL?

Benutzen Sie beispielsweise NGROK, um für das Testen in der PayPal-Sandbox eine lokale OXID eShop-URL mit SSL und Webzugriff auszustatten.

Wie Sie die temporäre URL generieren, hängt von Ihrem System ab. Wir beschreiben folgende Beispiele mit NGROK:

* Sie haben ein Alias unterhalb von ``localhost``.
  |br|
  Beispiel: ``http://localhost/meinprojekt/``
* Sie haben einen virtuellen Host.
  |br|
  Beispiel: ``http://meinprojekt.local``

|procedure|

1. Legen Sie unter `ngrok.com <https://ngrok.com/>`_ ein Konto an.
#. Folgen Sie den Anweisungen für das Installieren und Einrichten von NGROK.
#. Starten Sie NGROK.
#. Geben Sie einen der folgenden Befehle ein:

   * Wenn Sie einen Alias haben, geben Sie :command:`ngrok http 80` ein.
     |br|
     Die temporäre URL wird angezeigt, beispielsweise ``https://6f62-2003-c7-cf2e-9900-d19c-904a-e54c-64fe.eu.ngrok.io``.
     |br|
     Ihren Shop werden Sie damit über eine URL nach folgendem Schema erreichen:
     |br|
     ``https://6f62-2003-c7-cf2e-9900-d19c-904a-e54c-64fe.eu.ngrok.io/meinprojekt/``
   * Wenn Sie einen virtuellen Host haben, geben Sie einen Befehl nach folgendem Schema ein: :command:`ngrok http --host-header=meinprojekt.local 80` .
     |br|
     Beispiel: :command:`ngrok http --host-header=localhost.local 80` (:ref:`oxdaju03`)

     .. _oxdaju03:

     .. figure:: /media/screenshots/oxdaju03.png
        :alt: URL mit NGROK generieren

        Abb.: URL mit NGROK generieren

     Die temporäre URL wird unter :guilabel:`Forwarding`angezeigt, in unserem Beispiel ``https://60a6-2001-9e8-4739-1e00-1d18-1876-eae4-2f5d.eu.ngrok.io`` (:ref:`oxdaju04`).

     .. _oxdaju04:

     .. figure:: /media/screenshots/oxdaju04.png
        :alt: Temporäre URL anzeigen

        Abb.: Temporäre URL anzeigen

#. Stellen Sie sicher, dass Ihr Test-Shop läuft.
#. Geben Sie die temporäre URL in Ihren Browser ein.
   |br|
   Sie gelangen auf eine Weiterleitungsseite (:ref:`oxdaju05`).

   .. _oxdaju05:

   .. figure:: /media/screenshots/oxdaju05.png
      :alt: NGROK-Weiterleitungsseite

      Abb.: NGROK-Weiterleitungsseite

#. Wählen Sie :guilabel:`Visit Site`.
   |br|
   Ihr Shop wird nur mit den Elementen angezeigt, die ohne SSL erreichbar sind (:ref:`oxdaju06`).

   .. _oxdaju06:

   .. figure:: /media/screenshots/oxdaju06.png
      :alt: OXID eShop ohne SSL

      Abb.: OXID eShop ohne SSL

#. Öffnen Sie im Verzeichnis :file:`<Rootverzeichnis des eShops>/source` die Datei :file:`config.inc.php`.
#. Ändern Sie Ihr für die Dauer Ihrer Sitzung den Wert des Parameters :technicalname:`$this->sShopURL` von Ihrem Standard auf die temporäre NGROK-URL (:ref:`oxdaju07`).

   .. _oxdaju07:

   .. figure:: /media/screenshots/oxdaju07.png
      :alt: config.inc.php anpassen

      Abb.: config.inc.php anpassen

#. Laden Sie die temporäre URL Ihres Shops erneut.

|result|

Sie können den Webhook für das Testen von :productname:`PayPal Checkout` in der PayPal-Sandbox generieren (siehe :ref:`konfiguration:API-Anmeldeinformationen`).

Sobald Sie das NGROK-Fenster schließen, ist der temporäre Kanal beendet, und Sie müssen eine neue temporäre URL generieren.

.. note::

   **Webhook in der Sandbox generieren**

   Wenn Sie mit der temporären URL den Webhook für das Testen von :productname:`PayPal Checkout` in der PayPal-Sandbox (wie unter :ref:`konfiguration:API-Anmeldeinformationen` beschrieben) generieren, dann sind Sie mit dem Prozess vertraut.
   |br|
   Denn der Onboarding-Prozess funktioniert in der Live-Umgebung mit dem Live-Account genau wie in der Testumgebung mit der temporären URL.

   **Beispiel**: Sie sind OXID-Partner und wollen Ihrem Kunden beim Wechsel zu :productname:`PayPal Checkout` unterstützen.
   |br|
   Bitten Sie Ihren Kunden, eine Screen-Sharing-Session zu starten, bei der Sie ihm über die Schulter schauen.
   |br|
   Die Passwörter bleiben verborgen, aber Sie können unterstützen, wenn Ihr Kunde beim Erzeugen und Eingeben seiner PayPal-Anmeldedaten auf Fragen stößt.

.. Intern: oxdaju, Status:
