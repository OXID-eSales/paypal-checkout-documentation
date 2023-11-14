Consent Management-Platformen (CMPs) integrieren
================================================

Implementieren Sie bei Bedarf ein Zustimmungsverfahren, beispielsweise mit Usercentrics.

Den Besuchern des Shops wird damit beim ersten Aufruf ein Banner „Privatsphären-Einstellungen“ angezeigt, das darüber informiert, dass Website-Tracking-Technologien von Drittanbietern verwendet werden.

Am Beispiel der Consent Management-Plattform (CMP) Usercentrics finden Sie weitere Informationen in der Dokumentation unseres Moduls :productname:`OXID Cookie Management powered by usercentrics` unter `Funktionsbeschreibung <https://docs.oxid-esales.com/modules/usercentrics/de/latest/funktionsbeschreibung.html>`_.

.. todo: #tbd: Querverweis von Usercentrics auf diese Seite.

Hintergrund
-----------

:productname:`PayPal Checkout` fällt in der Definition von Consent Management-Plattformen unter die Kategorie „Dienste von
Drittanbietern“. Denn die Funktion von :productname:`PayPal Checkout` müssen Ressourcen (konkret: Javascript-Dateien)
von Fremdservern (Drittanbietern) geladen werden.

Problem
^^^^^^^

Bezahlbuttons, wie sie bei :productname:`PayPal Checkout` verwendet werden, sind elementare und funktionale Bestandteile eines Shops, weil sie Bezahlvorgänge schnell und unkompliziert zu ermöglichen.

Für besonders datenschutzsensible Kunden stellen Bezahlbuttons jedoch möglicherweise ein Datenschutzproblem dar. Solche Kunden bevorzugen eventuell andere Bezahlfunktionen.

Denn Drittanbieter sind theoretisch in der Lage, anhand von Drittanbieter-Zugriffs-Logs den Besuch des Kunden auf der Shop-Webseite
nachzuvollziehen.

Als Shopbetreiber müssen Sie daher abwägen zwischen

* der Funktionalität Ihrer Webseite

  und

* dem Datenschutz Ihrer Kunden

Lösung
^^^^^^

Wenn Datenschutz bei Ihren Kunden ein Problem sein könnte, bietet sich als Lösung die Nutzung eines Zustimmungsverfahrens an, so wie es Consent Management-Plattformen wie beispielsweise UserCentrics bieten.

Beispiel: Usercentrics in :productname:`PayPal Checkout` integrieren
--------------------------------------------------------------------

Nutzen Sie die folgende Anleitung zur Integration von Usercentrics in :productname:`PayPal Checkout` als Muster, das Sie in abgewandelter Form mit jeder anderen CMP ebenfalls umsetzen können, um ein Zustimmungsverfahren zu implementieren.

|prerequisites|

* Sie sind als Shopbetreiber bei Usercentrics registriert und haben ein für Ihren OXID eShop passendes Paket gebucht.

  Weitere Informationen finden Sie in der Dokumentation unseres Moduls :productname:`OXID Cookie Management powered by Usercentrics` unter `Usercentrics-Paket buchen <https://docs.oxid-esales.com/modules/Usercentrics/de/latest/einfuehrung.html#usercentrics-paket-buchen>`_.

* Sie haben :productname:`OXID Cookie Management powered by Usercentrics` installiert.

  Weitere Informationen finden Sie in der Dokumentation unseres Moduls :productname:`OXID Cookie Management powered by Usercentrics` unter `Usercentrics installieren <https://docs.oxid-esales.com/modules/usercentrics/de/latest/installation.html>`_.

|procedure|

1. Überschreiben Sie das :productname:`PayPal Checkout`-Module-Template.

   **Hintergrund**: Das „PayPal Checkout“-Modul ist so vorbereitet, dass alle Templates durch individuelle Anpassungen überschrieben werden können.
   |br|
   Dazu kopieren Sie eine oder mehrere Dateien aus dem Modul in Ihr Theme-Template.
   |br|
   Ihr OID eShop nimmt zuerst die Module-Templates, überschreibt diese aber mit Theme-Templates, wenn er identisch definierte Templates im Shop-Theme findet.

   Kopieren sie dazu die Datei :file:`/source/modules/osc/paypal/views/tpl/shared/layout/base_js.tpl` in das Verzeichnis :file:`/source/Application/views/<Theme des OXID eShops>/tpl/modules/osc/paypal/`.

   Wenn das Template-Verzeichnis :file:`/tpl/modules/osc/paypal/` noch nicht existiert, legen Sie es an.

   .. _Datenverarbeitungsdienst-anlegen:

#. Legen Sie einen Datenverarbeitungsdienst für :productname:`PayPal Checkout` an.

   Wenn Sie wie in unserem Beispiel Usercentrics benutzen, tun Sie Folgendes:

   a. Starten Sie das Usercentrics-Dashboard.
   #. Wählen Sie :menuselection:`Service Settings --> Data Processing Services` (:ref:`oxdajv01`, Pos. 1, 2).
   #. Um einen Service für :productname:`PayPal Checkout` anzulegen, wählen Sie :guilabel:`Create Custom DPS` (:ref:`oxdajv01`, Pos. 3).
      Unter :guilabel:`Custom Data Processing Services` (:ref:`oxdajv01`, Pos. 4) wird der Name des Datenverarbeitungsdienstes angezeigt (:ref:`oxdajv01`, Pos. 5).

      .. todo: #tbd: screenshot EN

      .. _oxdajv01:

      .. figure:: /media/screenshots/oxdajv01.png
         :alt: Datenverarbeitungsdienst im Usercentrics Admin Interface anlegen

         Abb.: Datenverarbeitungsdienst im Usercentrics Admin Interface anlegen

#. Passen Sie alle bestehenden :productname:`PayPal Checkout`-Skripte in der Datei :file:`/source/Application/views/<Theme des OXID eShops>/tpl/modules/osc/paypal/base_js.tpl` an.

   Hintergrund: Sie wollen sicherstellen, dass :emphasis:`alle` Skripte nur nach einer Zustimmung ausgeführt werden.

   Tun Sie Folgendes:

   a. Ergänzen Sie in Ihren Skripten den Typ :code:`type="text/plain"`.

      Hintergrund: Sie stellen damit sicher, dass das Skript beim Aufruf der Seite nicht automatisch vom Browser interpretiert und ausgeführt wird.

      Suchen Sie dazu nach dem Ausdruck :code:`<script ` und ergänzen Sie :code:`<script type="text/plain"` (siehe :ref:`Beispiel: Anpassen der PayPal Checkout-Skripte <Skripte-anpassen>`).

   #. Weisen Sie den Skripten der Datenverarbeitungsdienste, die Sie verwenden, ein benutzerdefiniertes Datenattribut zu.

      Hintergrund: Das Datenattribut wird zur Verbindung mit der CMP und zum Abfragen der Einwilligungen verwendet.

      Die Syntax dieses Datenattributs lautet :code:`data-usercentrics="<Name des Datenverarbeitungsdienstes>"`.

      Dabei entspricht :code:`<Name des Datenverarbeitungsdienst>` dem genauen Namen des Datenverarbeitungsdienstes, den Sie im Schritt :ref:`Datenverarbeitungsdienst anlegen <Datenverarbeitungsdienst-anlegen>` angelegt haben.

      Achten Sie beim Kopieren des Namens auf die Groß- und Kleinschreibung und eventuelle Leerzeichen.

      In unserem Beispiel (:ref:`oxdajv01`, Pos. 5) ist das Datenattribut also :code:`data-usercentrics="PayPal Checkout"` (siehe :ref:`Beispiel: Anpassen der PayPal Checkout-Skripte <Skripte-anpassen>`).

   .. _Skripte-anpassen:

   Beispiel: Anpassen der :productname:`PayPal Checkout`-Skripte

   Das Original-Template :file:`/source/modules/osc/paypal/views/tpl/shared/layout/base_js.tpl` sieht in unserem Beispiel aus wie folgt:

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


   Nach dem Anpassen der Skripte sieht Ihr Template :file:`/source/Application/views/<Theme des OXID eShops>/tpl/modules/osc/paypal/base_js.tpl` wie folgt aus:

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

|result|

Die :productname:`PayPal Checkout`-Skripte werden beim Laden der Seite nur dann ausgeführt, wenn Ihr Kunde :productname:`PayPal Checkout` seine Zustimmung gegeben hat.

.. Intern: oxdajv, Status: