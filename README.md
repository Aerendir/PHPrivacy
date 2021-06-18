# PHP-Privacy
A component to implement privacy by design in your PHP project.

This component follows a discussion on [Symfony](https://github.com/symfony/symfony) in [#26231](https://github.com/symfony/symfony/issues/26231).

EU Law
------

To ease the development consequences of the privacy regulations and directives, **we provide a condesed version of the GDPR regulation and of the Privacy Cookie Directive**.

Those two documents are the same as the ones provided by the EU but without all the *legalese*.

Also if **they not make the law** (the Law always is the one you can find in the official documents of the EU), they are **useful tools to understand which are the implications** on our lives as developers and **on our apps as wrote following the "Privacy by Design" principles**.

Here's the list of available documents:

- [General Data Protection Regulation (GDPR)](EU-law/GDPR-for-devs.md).

----------------------

PRIVACY COMPONENT

1. deve permettere di creare una pagina che elenca i servizi usati e i cookie che installano
2. Da questa pagina deve essere possibile selezionare e deselezionare i servizi
3. La scelta va memorizzata nel cookie
4. Quando un utente accede alla pagina controllo se il cookie esiste: se non esiste, allora mostro l’informativa breve
5. Quando clicca su accetto, creo il cookie e memorizzo l’accettazione.
6. Posso decidere di abilitare o disabilitare tutti i cookie di default
7. C’è un metodo ‘consentedTo()’ che permette di verificare se l’utente corrente ha acconsentito o meno

Officer = Workflow
PolicyBuilder = DefinitionBuilder
Policy = Definition
Consent = contiene i consensi dati dall’utente

PolicyBuilder = new PolicyBuilder()
Policy = PolicyBuilder->addConsentRequest(‘google_analytics’)
->addConsentRequest(‘facebook’)
->drawUp(); (redigi)

Officer = new Officer(Policy, Consents)
Officer->consentedTo(‘google_analytics’)
Officer->getPolicy()
Officer->getConsents()
Officer->getWithholds()
Officer->setConsentTo(‘google_analytics)
Officer->getConsents() : Consents

http://eur-lex.europa.eu/legal-content/EN/TXT/?uri=uriserv:OJ.L_.2016.119.01.0001.01.ENG&toc=OJ:L:2016:119:FULL

