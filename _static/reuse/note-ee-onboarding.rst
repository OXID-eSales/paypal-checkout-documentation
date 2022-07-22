.. attention::

   **PayPal Checkout mit der OXID eShop Enterprise Edition in Subshops betreiben**

   Sie haben die OXID eShop Enterprise Edition und betreiben damit Subshops für verschiedene Länder?

   Beachten Sie in diesem Fall die :emphasis:`Reihenfolge` der Subshops, für die Sie die Verbindung zu PayPal herstellen (Onboarding).

   |background|

   Aus technischen Gründen gelten Einschränkungen des Onboarding im ersten Subshop für das Onboarding in allen weiteren Subshops.

   |example|

   * Sie haben sowohl ein deutsches als auch ein schweizerisches PayPal-Händler-Konto.

     Sie führen das Onboarding zuerst für Ihren schweizerischen Subshop mit Ihrem schweizerischen PayPal-Händler-Konto aus.

     Damit stehen Ihnen die :productname:`PayPal Checkout`-Zahlungsmethoden zur Verfügung, die PayPal weltweit anbietet (siehe :ref:`einfuehrung:Marktabdeckung nach Ländern`).

     Anschließend führen Sie das Onboarding für Ihren deutschen Subshop mit Ihrem deutschen PayPal-Händler-Konto durch.

     In diesem Fall steht Ihnen die :productname:`PayPal Checkout`-Zahlungsmethode :productname:`Rechnungskauf` für Ihren deutschen Subshop :emphasis:`nicht` zur Verfügung.

     Grund: Die :productname:`PayPal Checkout`-Zahlungsmethode :productname:`Rechnungskauf` können Sie nur anbieten, wenn Sie ein deutsches PayPal-Händler-Konto haben.

   * Sie haben ausschließlich ein deutsches PayPal-Händler-Konto.

     Sie führen das Onboarding zuerst für Ihren deutschen Subshop und anschließend für Ihren schweizerischen Subshop aus.

     Beim Onboarding hat es den Anschein, als stünde die die :productname:`PayPal Checkout`-Zahlungsmethode :productname:`Rechnungskauf` auch für Ihren schweizerischen Subshop zur Verfügung.

     Das ist aber nicht der Fall. Ihren Kunden mit schweizerischer Rechnungsadresse wird :productname:`Rechnungskauf` nicht angeboten.

   |procedure|

   Gehen Sie wie folgt vor:

   * Sie haben ein deutsches PayPal-Händler-Konto?

     Führen Sie das Onboarding auch dann zuerst für Ihren :emphasis:`deutschen` Subshop durch, wenn Sie einen nicht-deutschen Haupt-Shop haben.

     Damit stellen Sie sicher, dass PayPal für Ihren deutschen Subshop auch diejenigen :productname:`PayPal Checkout`-Zahlungsmethoden freischaltet, die für nicht-deutsche PayPal-Händler-Konten nicht zur Verfügung stehen. |br|

   * Sie haben ausschließlich ein nicht-deutsches PayPal-Händler-Konto? |br|

     1. Führen Sie das Onboarding für Ihre Subshops aus.
     #. Prüfen Sie für jeden Subshop, wie wichtig die Einschränkung der :productname:`PayPal Checkout`-Zahlungsmethoden bei nicht-deutschen PayPal-Händler-Konten für den jeweilen Markt für Sie ist.
     #. Wenn Sie die Einschränkung kritisch für Ihr Geschäftsmodell ist, wenden Sie sich an den Support von PayPal, um eine Freischaltung für die benötigte :productname:`PayPal Checkout`-Zahlungsmethode zu erhalten.
