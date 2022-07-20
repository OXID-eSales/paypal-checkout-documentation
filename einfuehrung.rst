Wofür/Wofür nicht?
==================

Nutzen Sie :productname:`PayPal Checkout`,

* wenn Sie die Zahlungsart PayPal in Ihrem OXID eShop bisher noch nicht anbieten
* wenn Sie PayPal bereits nutzen, aber vor allem internationalen Kunden ein breites Spektrum beliebter Zahlungsmethoden einschließlich Rechnungskauf anbieten wollen

:productname:`PayPal Checkout` prüft und bestätigt Ihre Zahlungsanforderung in Echtzeit. Als Shop-Betreiber sind Sie deshalb gegen Zahlungsausfälle geschützt.

Zahlungsarten in PayPal Checkout
--------------------------------

.. image:: media/paypal-logo.png
    :alt: PayPal-Logo
    :class: no-shadow
    :height: 38
    :width: 150

Einschränkung bei B2B-Shops
^^^^^^^^^^^^^^^^^^^^^^^^^^^

Wenn Sie eingestellt haben, dass die Preise Netto-Preise sind (typischerweise in B2B-Shops), dann steht die Zahlungsart Rechnungskauf nicht zur Verfügung.

Im typischen Fall geben Sie in Ihrem OXID eShop alle Preise als Bruttopreise an, und Sie können Ihren Privatkunden können die Zahlungsart Rechnungskauf anbieten.

Marktabdeckung nach Ländern
^^^^^^^^^^^^^^^^^^^^^^^^^^^

Bieten Sie mit dem :productname:`PayPal Checkout`-Modul für OXID die in folgenden Märkten beliebten Zahlungsmethoden an.

Beachten Sie jeweils die Währungsabdeckung der einzelnen Zahlungsmethoden (siehe :ref:`einfuehrung:Währungsabdeckung nach Zahlungsmethode`).

==================  ==========================
Markt               Zahlungsmethoden
==================  ==========================
Weltweit	        PayPal
Weltweit	        PayPal Express
Belgien	            Bancontact
Belgien	            Sofort (Klarna Pay now)
Deutschland	        GiroPay
Deutschland	        Kreditkarte
Deutschland	        PayPal - Später bezahlen
Deutschland	        Rechnungskauf
Deutschland	        Sofort (Klarna Pay now)
Frankreich	        Kreditkarte
Frankreich	        PayPal - Später bezahlen
Großbritannien      Kreditkarte
Großbritannien      PayPal - Später bezahlen
Großbritannien	    Sofort (Klarna Pay now)
Italien 	        Kreditkarte
Italien	            MyBank
Italien	            Sofort (Klarna Pay now)
Italien             PayPal - Später bezahlen
Kanada  	        Kreditkarte
Niederlande	        iDEAL
Niederlande	        Sofort (Klarna Pay now)
Österreich	        eps
Österreich	        Kreditkarte
Österreich 	        PayPal - Später bezahlen
Österreich	        Sofort (Klarna Pay now)
Polen	            BLIK
Polen	            Przelewy24
Spanien 	        Kreditkarte
Spanien 	        PayPal - Später bezahlen
Spanien	            Sofort (Klarna Pay now)
Vereinigte Staaten  Kreditkarte
Vereinigte Staaten  PayPal - Später bezahlen
==================  ==========================

Marktabdeckung nach Zahlungsmethoden
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Beachten Sie jeweils die Währungsabdeckung der einzelnen Zahlungsmethoden (siehe :ref:`einfuehrung:Währungsabdeckung nach Zahlungsmethode`).

========================== ===============
Zahlungsmethoden           Märkte
========================== ===============
Bancontact	               Belgien
BLIK	                   Polen
eps	                       Österreich
GiroPay	                   Deutschland
iDEAL 	                   Niederlande
Kreditkarte                Deutschland
Kreditkarte                Frankreich
Kreditkarte                Großbritannien
Kreditkarte                Italien
Kreditkarte                Österreich
Kreditkarte                Spanien
Kreditkarte                Vereinigte Staaten
MyBank	                   Italien
PayPal	                   Weltweit
PayPal Express             Weltweit
PayPal - Später bezahlen   Deutschland
PayPal - Später bezahlen   Frankreich
PayPal - Später bezahlen   Großbritannien
PayPal - Später bezahlen   Italien
PayPal - Später bezahlen   Österreich
PayPal - Später bezahlen   Spanien
PayPal - Später bezahlen   Vereinigte Staaten
Przelewy24	               Polen
Rechnungskauf	           Deutschland
Sofort (Klarna Pay now)	   Belgien
Sofort (Klarna Pay now)	   Deutschland
Sofort (Klarna Pay now)	   Großbritannien
Sofort (Klarna Pay now)    Italien
Sofort (Klarna Pay now)	   Niederlande
Sofort (Klarna Pay now)	   Österreich
Sofort (Klarna Pay now)	   Spanien
========================== ===============

Währungsabdeckung nach Zahlungsmethode
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

=============================== ===============
Payment methods                 Currencies
=============================== ===============
PayPal                          AUD, BRL, CAD, CNY, CZK, DKK, EUR, HKD, HUF, ILS, JPY, MYR, MXN, TWD, NZD, NOK, PHP, PLN, GBP, RUB, SGD, SEK, CHF, THB, USD
PayPal Express                  AUD, BRL, CAD, CNY, CZK, DKK, EUR, HKD, HUF, ILS, JPY, MYR, MXN, TWD, NZD, NOK, PHP, PLN, GBP, RUB, SGD, SEK, CHF, THB, USD
PayPal - Später bezahlen        AUD, EUR, GBP, USD
Rechnungskauf                   EUR
Kreditkarte                     AUD, CAD, CHF, CZK, DKK, EUR, GBP, HKD, HUF, JPY, NOK, NZD, PLN, SEK, SGD, USD
Bancontact                      EUR
BLIK                            PLN
EPS                             EUR
GiroPay                         EUR
Ideal                           EUR
MyBank                          EUR
Przelewy24                      EUR, PLN
Sofort (Klarna Pay now)         EUR, GBP
=============================== ===============


Sie haben das Modul PayPal?
---------------------------

Wechseln Sie zu :productname:`PayPal Checkout`, um Ihren Kunden zusätzliche Zahlungsmethoden einschließlich Rechnungskauf anbieten zu können, die in internationalen Märkten beliebt sind.

Weitere Informationen finden Sie unter `developer.paypal.com/docs/checkout/apm/ <https://developer.paypal.com/docs/checkout/apm/>`_.


Sie haben das Modul PayPal Plus?
--------------------------------

Die API von :productname:`PayPal Plus` ist veraltet. PayPal entwickelt die API nicht weiter und bietet keine neuen Verträge dafür an.

Wechseln Sie zu :productname:`PayPal Checkout`, wenn es für Sie wichtig ist, Ihren Kunden die Schnellkauf-Funktion oder die Später Bezahlen-Funktion von :productname:`PayPal Checkout` anzubieten:

* Mit der Schnellkauf-Funktion können Ihre Kunden den Anmeldeprozess in Ihrem eShop überspringen und direkt beispielsweise auf der Produkt-Detailseite die Bestellung und Bezahlung starten (siehe :ref:`konfiguration:Einstellungen für die Buttonplatzierung: Schnellkauf-Funktion`).
* Mit der Später Bezahlen-Funktion können Kunden in Deutschland beispielsweise mit 30 Tagen Aufschub oder per PayPal Ratenzahlung bezahlen (siehe :ref:`konfiguration:Einstellungen für die Buttonplatzierung: Später Bezahlen`).
  |br|
  Weitere Informationen über Länder-Abdeckung und landesspezifische Funktionen der Später Bezahlen-Funktion finden Sie unter `developer.paypal.com/docs/checkout/pay-later/de/ <https://developer.paypal.com/docs/checkout/pay-later/de/>`_.

.. Intern: oxdajp, Status: