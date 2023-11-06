Consent Management Platforms (CMP) integrieren
==============================================

Holen Sie für Implementieren Sie bei Bedarf ein Zustimmungsverfahren, beispielsweise mit UserCentrics.



Den Besuchern des Shops wird damit beim ersten Aufruf ein Banner „Privatsphären-Einstellungen“ angezeigt, das darüber informiert, dass Website-Tracking-Technologien von Drittanbietern verwendet werden.

Am Beispiel der Consent Management Platform (CMP) Usercentrics finden Sie weitere Informationen in der Dokumentation unseres Moduls :productname:`OXID Cookie Management powered by usercentrics` unter `Funktionsbeschreibung <https://docs.oxid-esales.com/modules/usercentrics/de/latest/funktionsbeschreibung.html>`_.

.. todo: #ML: Wie sieht das Ergebnis für den Endkunden im Shop aus?

Hintergrund
-----------

„PayPal Checkout“ fällt in der Definition von Consent Management Platformen (CMPs) unter die Kategorie „Dienste von
Drittanbietern“, weil für die Funktion von „PayPal Checkout“ Resourcen (konkret: Javascript-Dateien)
von Fremdservern (Drittanbietern) geladen werden müssen.

Als Shopbetreiber müssen Sie abwägen zwischen

* der Funktionalität Ihrer Webseite

  und

* dem Datenschutz Ihrer Kunden.

Bezahlbuttons, wie sie u.a. bei „PayPal Checkout“ verwendet werden, sind
elementare und funktionale Bestandteile eines Shops, um einen Bezahlvorgang schnell und
unkompliziert zu ermöglichen.

Für Kunden, die andere Bezahlfunktionen bevorzugen, stellen Bezahlbuttons jedoch möglicherweise ein Datenschutzproblem dar.

Denn Drittanbieter sind theoretisch in der Lage, anhand von Drittanbieter-Zugriffs-Logs den Besuch des Kunden auf der Shopwebseite
nachzuvollziehen.

.. todo: #ML: In welchem Fall **will/muss** ich das tun? Wann **kann** ich darauf verzichten?

Lösung
------

Eine mögliche Lösung des Problems ist die Nutzung eines Zustimmungsverfahrens, so wie es
Consent Management Platforms (kurz CMPs) wie UserCentrics bieten.

Die folgende Anleitung zur Integration von UserCentrics in „PayPal Checkout“ lässt sich in abgewandelter Form mit jeder
anderen CMP auch lösen.

Voraussetzungen
---------------

* Sie sind als Shopbetreiber bei Usercentrics registriert und haben ein für Ihren OXID eShop passendes Paket gebucht.

  Weitere Informationen finden Sie in der Dokumentation unseres Moduls :productname:`OXID Cookie Management powered by usercentrics` unter `Usercentrics-Paket buchen <https://docs.oxid-esales.com/modules/usercentrics/de/latest/einfuehrung.html#usercentrics-paket-buchen>`_.

  .. todo: #ML: Verweis auf Modul-Doku sollte sinnvoll sein, oder?

Vorgehen
--------

1. Überschreiben Sie das :productname:`PayPal Checkout`-Module-Templates.

   Hintergrund: Das „PayPal Checkout“-Modul ist so vorbereitet, das alle Templates durch individuelle Anpassungen überschrieben werden können.
   |br|
   Dazu werden eine oder mehrere Dateien aus dem Modul im Template des Shopbetreibers kopiert.
   |br|
   Der Shop nimmt zuerst die Module-Templates, überschreibt diese aber mit Theme-Templates, wenn er identisch definierte Templates im Shop- Theme findet.

   Kopieren sie dazu die Datei :file:`/source/modules/osc/paypal/views/tpl/shared/layout/base_js.tpl` in das Verzeichnis :file:`/source/Application/views/TEMPLATE_DES_SHOPS/modules/osc/paypal/`.

   .. todo: #ML: Das Zielverzeichnis  /source/Application/views/TEMPLATE_DES_SHOPS/modules/osc/paypal/base_js.tpl existiert bei mir nicht

   .. _Datenverarbeitungsdienst-anlegen:

#. Legen Sie einen Datenverarbeitungsdienst an.

   Beispiel: Wenn Sie Usercentrics benutzen, tun Sie Folgendes:

   a. Starten Sie das UserCentrics-Dashboard.
   #. Wählen Sie :menuselection:`Service Settings --> Data Processing Services` (:ref:`oxdajv01`, Pos. 1, 2).
   #. Um einen Service für :productname:`PayPal Checkout`anzulegen, wählen Sie Create Custom DPS` (:ref:`oxdajv01`, Pos. 3).
      Unter :guilabel:`Custom Data Processing Services` (:ref:`oxdajv01`, Pos. 4) wird der Name des Datenverarbeitungsdienstes angezeigt (:ref:`oxdajv01`, Pos. 5).

      .. todo: #tbd: screenshot EN

      .. _oxdajv01:

      .. figure:: /media/screenshots/oxdajv01.png
         :alt: Datenverarbeitungsdienst im Usercentrics Admin Interface anlegen

         Abb.: Datenverarbeitungsdienst im Usercentrics Admin Interface anlegen




Ermitteln Sie den Namen des Datenverarbeitungsdienstes im UserCentrics-Dashboard mit den
Schritten (1-5). Achten Sie beim Kopieren des Namens auf die Groß- und Kleinschreibung und
eventuelle Lehrzeichen.



#. Passen Sie alle bestehenden :productname:`PayPal Checkout`-Skripte an.

   .. todo: #ML: Was bedeutet alle? Skripten in Subshops?

   Hintergrund: Sie müssen sicherstellen, dass die Skripte nur nach einer Zustimmung ausgeführt werden.

   .. todo: #ML: Zustimmung durch den Endkunden? Kommt da ein Meldung, oder wie geht das?

   Tun Sie Folgendes:

   a. Ergänzen Sie in Ihren Skripten den Typ :code:`type="text/plain"`.

      Hintergrund: Sie stellen damit sicher, dass das Skript beim Aufruf der Seite nicht automatisch vom Browser interpretiert und ausgeführt wird.

      Suchen Sie dazu nach nach dem Ausdruck :code:`<script ` und ergänzen Sie :code:`<script type="text/plain"` (siehe :ref:`Beispiel: Anpassen der PayPal Checkout-Skripte <Skripte-anpassen>`).

   #. Weisen Sie den Skripten der Datenverarbeitungsdienste, die Sie verwenden, ein benutzerdefiniertes Datenattribut zu.

      Hintergrund: Das Datenattribut wird zur Verbindung mit der CMP und zum Abfragen von Einwilligungen verwendet.

      Die Syntax dieses Datenattributs lautet :code:`data-usercentrics="<Name des Datenverarbeitungsdienst>"`.

      Dabei entspricht :code:`<Name des Datenverarbeitungsdienst>` dem genauen Namen des Datenverarbeitungsdienstes, den Sie im Schritt :ref:`Datenverarbeitungsdienst anlegen <Datenverarbeitungsdienst-anlegen>` angelegt haben.

      .. todo: #ML: Wieso Plural "Namen der Datenverarbeitungsdienste"? Waren PaPal und Amazon gemeint?

      In unserem Beispiel (:ref:`oxdajv01`, Pos. 5) also :code:`data-usercentrics="PayPal Checkout"` (siehe :ref:`Beispiel: Anpassen der PayPal Checkout-Skripte <Skripte-anpassen>`).

   .. _Skripte-anpassen:

   Beispiel: Anpassen der :productname:`PayPal Checkout`-Skripte

   Das Original-Skript sieht aus wir folgt:

   .. code::

       ...
       <script src="[{$oViewConf->getPayPalJsSdkUrl()}]" data-partner-attribution-id="[{$oViewConf-
       >getPayPalPartnerAttributionIdForBanner()}]"></script>
       ...
       <script src="[{$oViewConf->getPayPalJsSdkUrlForACDC()}]" data-client-
       token="[{$oViewConf→getDataClientToken()}]"></script>
       ...
       <script src="[{$oViewConf->getPayPalJsSdkUrlForButtonPayments()}]" data-partner-attribution-
       id="[{$oViewConf→getPayPalPartnerAttributionIdForBanner()}]}]"></script>
       ...
       <script src="[{$oViewConf->getPayPalApiBannerUrl()}]" data-partner-attribution-
       id="[{$oViewConf->getPayPalPartnerAttributionIdForBanner()}]"></script>
       ...


   Nach dem Anpassen sieht Ihr Skript wie folgt aus:

   .. code::

       ...
       <script type="text/plain" data-usercentrics="PayPal Checkout" src="[{$oViewConf-
       >getPayPalJsSdkUrl()}]" data-partner-attribution-id="[{$oViewConf-
       >getPayPalPartnerAttributionIdForBanner()}]"></script>
       ...
       <script type="text/plain" data-usercentrics="PayPal Checkout" src="[{$oViewConf-
       >getPayPalJsSdkUrlForACDC()}]" data-client-
       token="[{$oViewConf→getDataClientToken()}]"></script>
       ...
       <script type="text/plain" data-usercentrics="PayPal Checkout" src="[{$oViewConf-
       >getPayPalJsSdkUrlForButtonPayments()}]" data-partner-attribution-
       id="[{$oViewConf→getPayPalPartnerAttributionIdForBanner()}]}]"></script>
       ...
       <script type="text/plain" data-usercentrics="PayPal Checkout" src="[{$oViewConf-
       >getPayPalApiBannerUrl()}]" data-partner-attribution-id="[{$oViewConf-
       >getPayPalPartnerAttributionIdForBanner()}]"></script>
       ...

Resultat
--------

Die :productname:`PayPal Checkout`-Skripte werden beim Laden der Seite nur dann ausgeführt, wenn Ihr Kunde :productname:`PayPal Checkout` seine Zustimmung gegeben hat.


.. Intern: oxdajv, Status: