Certificati digitali emessi all’interno di domini di interoperabilità specifici
==================================================================================

Nell’ambito di un dominio di interoperabilità i soggetti afferenti, in 
alternativa a quanto indicato al precedente paragrafo, possono individuare 
tra essi uno o più soggetti abilitati all’emissione di certificati digitali 
(di seguito CA del dominio di interoperabilità).

La costituzione del trust è formalizza dalle regole del dominio di 
interoperabilità in cui sono definite:

- Il dettaglio implementativo dei processi di quanto indicato ai successivi 
  paragrafi :ref:`emissione-certificati`, :ref:`gestione-revoca` e 
  :ref:`gestione-distribuzione`;
- Le modalità con cui i soggetti afferenti al dominio di interoperabilità 
  (di seguito soggetto richiedente) inoltrano alla CA del dominio di 
  interoperabilità la richiesta di emissione di un certificato;
- Le verifiche in carico alla CA del dominio di interoperabilità per 
  dare seguito all’identificazione del soggetto richiedente l'emissione 
  di un certificato digitale;
- Le modalità con cui la CA del dominio di interoperabilità inoltra il 
  certificato emesso al soggetto richiedente e, più in generale, le 
  modalità con cui i certificati digitali emessi sono distribuiti ai 
  soggetti afferenti il dominio di interoperabilità.

  .. list-table:: 
   :widths: 15 40
   :header-rows: 0

   * - **[API_SIC_07]** 
     - I soggetti afferenti ad un dominio di interoperabilità che rendono 
       disponibili API DEVONO accettare i certificati digitali emessi 
       da una CA del dominio di interoperabilità per autenticare gli 
       altri soggetti utilizzatori delle stesse API.

   * - **[API_SIC_08]** 
     - I soggetti che rendono disponibili API DEVONO verificare la 
       validità dei certificati digitali emessi da una CA del dominio 
       di interoperabilità, compresa l’eventuale revoca degli stessi, 
       per ogni invocazione da parte di soggetti delle stesse API per 
       cui è abilitato l’accesso.

.. _`emissione-certificati`:

Gestione dell'emissione dei certificati digitali
------------------------------------------------

Il processo di emissione di certificati digitali da parte di una CA del 
dominio di interoperabilità è caratterizzato dai seguenti passi:

1. Il soggetto richiedente provvede, in autonomia, alla generazione di 
   una coppia di chiavi asimmetriche nel rispetto delle regole definite 
   nel dominio di interoperabilità;
2. Il soggetto richiedente inoltra nei modi definiti nelle regole del 
   dominio di interoperabilità alla CA del dominio di interoperabilità 
   la richiesta di certificazione CSR, in formato PKCS#10;
3. La CA del dominio di interoperabilità identifica il soggetto richiedente 
   e, in caso di identificazione positiva, provvede a generare il certificato 
   e a fornirlo al soggetto richiedente.

.. _`gestione-revoca`:

Gestione della revoca dei certificati digitali
----------------------------------------------

La CA del dominio di interoperabilità assicura la disponibilità dei 
necessari servizi per permettere, per ogni invocazione alle proprie 
API, ai soggetti afferenti ad un dominio di interoperabilità di 
verificare l’eventuale revoca di certificati digitali emessi.

A tal fine si DOVREBBE utilizzare la Online Certificate 
Status Protocol (OCSP) [1]_ o la Certificate Revocation List (CRL) 
[2]_.


.. _`gestione-distribuzione`:

Gestione della distribuzione dei certificati digitali della CA
--------------------------------------------------------------

La CA del dominio di interoperabilità, nelle modalità indicate nelle 
regole del dominio di interoperabilità, inoltra al soggetto richiedente 
il certificato firmato e/o assicura la distribuzione dei certificati 
digitali emessi ai soggetti afferenti al dominio di interoperabilità.


.. [1]
   Cf.
   https://tools.ietf.org/html/rfc6960

.. [2]
   Cf.
   https://tools.ietf.org/html/rfc5280


.. forum_italia::
  :topic_id: 22266
  :scope: document
