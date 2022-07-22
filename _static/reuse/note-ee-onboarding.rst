.. attention::

   **Operating PayPal Checkout in subshops with the OXID eShop Enterprise Edition**

   You have the OXID eShop Enterprise Edition and run subshops for different countries?

   In this case, note the :emphasis:`order` of the subshops for which you connect to PayPal (onboarding).

   |background|

   For technical reasons restrictions of the onboarding in the first subshop apply to the onboarding in all further subshops.

   |example|

   * You have both a German and a Swiss PayPal merchant account.

     You perform the onboarding first for your Swiss subshop with your Swiss PayPal merchant account.

     This makes the :productname:`PayPal Checkout` payment methods available to you that PayPal offers worldwide (see :ref:`introduction:Market coverage by country`).

     Then you perform the onboarding for your German subshop using your German PayPal merchant account.

     In this case, the :productname:`PayPal Checkout` payment method :productname:`Pay upon Invoice` will :emphasis:`not` be available for your German subshop.

     Reason: You can only offer the :productname:`PayPal Checkout` payment method :productname:`Pay upon Invoice` if you have a German PayPal merchant account.

   * You only have a German PayPal merchant account.

     You perform the onboarding first for your German subshop and then for your Swiss subshop.

     During onboarding, it appears that the :productname:`PayPal Checkout` payment method :productname:`Pay upon Invoice` is also available for your Swiss subshop.

     But this is not the case. Your customers with a Swiss billing address will not be offered :productname:`Pay upon Invoice`.

   |procedure|

   Proceed as follows:

   * You have a German PayPal merchant account?

     Perform the onboarding for your :emphasis:`German` subshop first even if you have a non-German main store.

     This will ensure that PayPal will also enable those :productname:`PayPal Checkout` payment methods for your German subshop that are not available for non-German PayPal merchant accounts. |br|

   * You only have a non-German PayPal merchant account? |br|

     1. Perform the onboarding for your subshops.
     #. For each subshop, check how important the restriction of :productname:`PayPal Checkout` payment methods for non-German PayPal merchant accounts is for you in that particular market.
     #. If the restriction is critical for your business model, contact PayPal support to get an activation for the required :productname:`PayPal Checkout` payment method.