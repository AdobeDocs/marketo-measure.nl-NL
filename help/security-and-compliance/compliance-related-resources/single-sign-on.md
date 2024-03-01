---
unique-page-id: 18874761
description: Single Sign On - [!DNL Marketo Measure]
title: Single Sign On
exl-id: a328e9cb-8352-4693-8a44-533e08f1a29c
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '1267'
ht-degree: 0%

---

# Single Sign On {#single-sign-on}

SAML (de taal van de prijsverhoging van de veiligheidsbewering) voor SSO (enig teken-op) maakt het voor gebruikers mogelijk om door de identiteitsleverancier van een bedrijf voor authentiek te verklaren wanneer zij login aan het bedrijf [!DNL Marketo Measure] app. SSO stelt een gebruiker in staat om slechts eenmaal te verifiëren, zonder afzonderlijke apps te hoeven verifiëren. SAML is een noodzaak voor zakelijke klanten omdat niet alle gebruikers een [!DNL Salesforce] of [!DNL Google] binnen hun organisatie. Om te schalen, [!DNL Marketo Measure] heeft een oplossing van SAML ontwikkeld die de leveranciers van de bedrijfsidentiteit kan steunen.

>[!CAUTION]
>
>In dit artikel worden Single Sign On (SSO) en het geavanceerde CRM-gebruikersbeheer beschreven. Als uw account is ingericht **na 10-9-2020**, dit artikel buiten beschouwing laten, aangezien SSO en Identity Management binnen de [Adobe Admin Console voor je [!DNL Marketo Measure] integratie](/help/configuration-and-setup/getting-started-with-marketo-measure/marketo-measure-quick-start.md).

>[!NOTE]
>
>Het is waarschijnlijk dat bedrijven verschillende identiteitsproviders gebruiken (bijvoorbeeld Ping Identity, Okta). De termen die worden gebruikt in de volgende instellingsinstructies en in de gebruikersinterface komen mogelijk niet direct overeen met de termen die worden gebruikt door uw identiteitsprovider.

## Vereisten {#requirements}

* Gebruiker met AccountAdmin-machtigingen in het dialoogvenster [!DNL Marketo Measure] App
* Gebruiker met administratieve toegang tot de Identiteitsprovider van de klant

## Aan de slag {#getting-started}

Ga om aan de slag te gaan naar Instellingen > Beveiliging > Verificatie op de pagina [!DNL Marketo Measure] toepassing. Dan schakelaar het Login Type aan Douane SSO om de configuratieopties te zien. De wijzigingen worden pas van kracht als u uw verificatie test en op de knop **[!UICONTROL Save]** onder aan de pagina.

![](assets/single-sign-on-1.png)

## Proces {#process}

[!DNL Marketo Measure] Voor Single Sign On is het nodig dat u de verificatie-instellingen configureert in een reeks stappen die u moet volgen, zodat u niet het risico loopt dat u zich buiten uw [!DNL Marketo Measure] account.

Stel de [!DNL Marketo Measure] Toepassing in uw identiteitsprovider. Zie externe documentatie die hieronder voor analyses wordt vermeld.

    a. Gebruik [https://apps.bizible.com/BizibleSAML2/ReceiveSSORequest] (https://apps.bizible.com/BizibleSAML2/ReceiveSSORequest) wanneer u wordt gevraagd om de URL voor Single Sign On of de URL voor Ontvanger of de bestemmings-URL, de URL voor SAML Assertion Customer Service (ACS).
    
    b. Gebruik [https://BizibleLPM] (https://biziblelpm/) wanneer u wordt gevraagd om de URL voor de audioberichting of de door de toepassing gedefinieerde unieke id.

Schakel over naar Aangepaste SSO in het dialoogvenster [!DNL Marketo Measure] Toepassing

    a. Nadat de Factureringsgroep is ingeschakeld voor uw account, kunt u nu naar [!UICONTROL Settings] >>[!UICONTROL Security] >> [!UICONTROL Authentication]
    
    b. Door gebrek, zal uw Login Type aan &quot;Gebruikers van CRM worden geplaatst.&quot;
    
    c. Schakelaar het Login Type aan &quot;Douane SSO&quot;om met het configuratieproces te beginnen.

De verbindingsinstellingen voor de configuratie van uw identiteitsprovider invullen

    a. Uw identiteitsprovider kan een XML-document met IDP-metagegevens geven waarmee de vereiste configuratievelden worden verwijderd. Laad de inhoud van het XML-document of vul de drie onderstaande velden in uit de uitvoer die is verkregen tijdens het configuratieproces van Identiteitsprovider. **U hoeft beide niet in te vullen.**
    
    i. IdP URL: De URL die [!DNL Marketo Measure] moet worden aangeroepen om uw gebruikers te verifiëren voor de [!DNL Marketo Measure] toepassing. Wordt ook wel de &quot;Redirect URL&quot; genoemd.
    ii. IdP-uitgever: Een unieke id van de identiteitsprovider. Wordt ook wel de externe sleutel genoemd.
    iii. IdP-certificaat: een openbare sleutel die [!DNL Marketo Measure] om de handtekening van alle reacties van de identiteitsprovider te verifiëren en te valideren.

Stel de vervaldatum van het token voor uw gebruikers in minuten in.

    a. [!DNL Marketo Measure] Hiermee wordt een geheel getal van 1 tot en met 1440 minuten toegestaan. Nadat de sessietijd van een gebruiker is overschreden, wordt de gebruiker afgemeld zodra deze naar een nieuwe pagina navigeert.

Stel uw gebruikerskenmerkinstellingen in en wijs deze toe aan de respectievelijke voornaam, achternaam en e-mailadres.

    a. Door de SAML-kenmerken in te voeren, [!DNL Marketo Measure] kan uw gebruikers herkennen aan de hand van de doorgegeven informatie.
    
    i. E-mailkenmerk: geef de kenmerknaam op die uw identiteitsprovider gebruikt voor het e-mailadres van de gebruiker.
    ii. Kenmerk voornaam: geef de kenmerknaam op die uw identiteitsprovider gebruikt voor de voornaam van de gebruiker.
    iii. Attribuut achternaam: geef de kenmerknaam op die uw identiteitsprovider gebruikt voor de achternaam van de gebruiker.
    
    b. Tip: Als u uw SAML-configuratie nu test, parseren we de kenmerken E-mail, Voornaam en Achternaam die u voor deze sectie kunt gebruiken.

![](assets/single-sign-on-2.png)

Opstelling en kaart uw montages van de Rol van de Gebruiker aan de respectieve rollen of de groepen die van uw IdP worden geclassificeerd.

    a. Klanten kunnen desgewenst [!DNL Marketo Measure] gebruikersrollen op basis van groepen die zijn gedefinieerd in hun identiteitsprovider. Door uw SAML-kenmerken in te voeren, [!DNL Marketo Measure] kan de rollen en groepen van uw gebruiker toewijzen aan [!DNL Marketo Measure] gebruikersmachtigingen. Wij adviseren hoogst u opstelling deze rollen zodat uw [!DNL Marketo Measure] beheerder heeft voldoende rechten om uw account bij te werken.
    
    b. Als er geen rollen of groepen worden toegewezen, is de standaardinstelling dat alle werknemers in de Identiteitsprovider standaard gebruikerstoegang hebben.
    
    i. [!DNL Marketo Measure] Standaardgebruiker: geef de rol of groepswaarde op (van uw SSO-provider) voor gebruikers die alleen-lezen toegang moeten hebben tot de [!DNL Marketo Measure] toepassing.
    ii. [!DNL Marketo Measure] Account Admin-gebruiker: geef de rol of groepswaarde (van uw SSO-provider) op voor gebruikers die beheertoegang moeten hebben tot de [!DNL Marketo Measure] toepassing. Dit betekent dat de rol toegang heeft tot configuraties en instellingen voor wijzigingen die betrekking hebben op uw account.
    iii. U moet een attribuut in uw IdP met de nauwkeurige naam van &quot;groepen&quot;hebben die de waarden bevat u in de &quot;Bizible Standard User&quot;of &quot;Bizible Account Admin User&quot;attributen plaatst.
    
    c. Als meerdere rollen of groepen moeten worden toegewezen aan een rol, voert u elke waarde in, gescheiden door een komma.

![](assets/single-sign-on-3.png)

Test de Single Sign On configuratie

    a. Voordat u op Opslaan kunt klikken, moet u op de knop [!UICONTROL Test SAML Authentication] om te controleren of uw instellingen correct zijn geconfigureerd.
    
    b. Als er een fout optreedt, volgt u het bericht en probeert u het opnieuw.

![](assets/single-sign-on-4.png)

Sla uw instellingen op en geef uw collega&#39;s de opdracht deze te gebruiken [!UICONTROL Single Sign On] met uw nieuwe aangepaste aanmeldings-URL.

    a. Belangrijk: Zodra u uw nieuwe montages van de Authentificatie bewaart, is het mogelijk uw zitting zal eindigen zodra u aan een nieuwe pagina navigeert omdat u login door de Gebruikers van CRM en toegelaten Douane SSO hebt onbruikbaar gemaakt.

![](assets/single-sign-on-5.png)

Probeer het uit!

    a. Gebruik uw nieuwe aangepaste URL voor aanmelden en probeer u opnieuw aan te melden bij de [!DNL Marketo Measure] Toepassing met uw aanmeldingsgegevens van de identiteitsprovider.
    
    b. Het formaat ziet er als volgt uit: https://apps.adobe.com/business/[naamRekening]&quot;
    
    c. Gefeliciteerd! U hebt Single Sign On ingesteld bij [!DNL Marketo Measure] Toepassing voor uw account!

![](assets/single-sign-on-6.png)

>[!NOTE]
>
>Nadat u SSO vormt, zult u niet meer gebruikers binnen moeten toevoegen [!DNL Marketo Measure] toepassing. De levering van de gebruiker zou direct binnen uw Leverancier van de Identiteit moeten worden behandeld.

## CRM-gebruikers (Geavanceerde instellingen) {#crm-users-advanced-setup}

Standaard hebben alle accounts toegang tot de [!DNL Marketo Measure] toepassing die hun geloofsbrieven van CRM gebruikt. Soms moeten eigenaars van accounts de toegang tot bepaalde rollen beperken en deze niet openen voor alle gebruikers met een actieve CRM-licentie. De Geavanceerde opstelling zal u toestaan om uw rollen en groepen van CRM aan in kaart te brengen [!DNL Marketo Measure] gebruikersmachtigingen.

Als geen rollen of groepen in kaart worden gebracht, is het gebrek dat plaatst dat alle actieve vergunningen in uw CRM Standaard gebruikerstoegang zullen hebben.

* [!DNL Marketo Measure] Standaardgebruiker: geef de rol of groepswaarde op voor gebruikers die alleen-lezen toegang moeten hebben tot de [!DNL Marketo Measure] toepassing.
* [!DNL Marketo Measure] Gebruiker van accountbeheerder: geef de rol of groepswaarde op voor gebruikers die beheertoegang moeten hebben tot de [!DNL Marketo Measure] toepassing. Dit betekent dat de rol toegang heeft tot configuraties en instellingen voor wijzigingen die betrekking hebben op uw account.

Als meerdere rollen of groepen moeten worden toegewezen aan een rol, voert u elke waarde in, gescheiden door een komma.

**Salesforce Roles**

Voor [!DNL Salesforce] Rollen, gebruik de naam van elke Rol. Alle rollen zijn te vinden onder de [!UICONTROL Setup] >[!UICONTROL Manage Users] >[!UICONTROL Roles] -menu.

![](assets/6.png)

**Dynamische rollen**

Voor [!DNL Dynamics] Rollen, gebruik de naam van elke Rol van de Veiligheid. Alle beveiligingsrollen vindt u onder de [!UICONTROL Settings] >[!UICONTROL Security] >[!UICONTROL Security Roles] -menu.

![](assets/7.png)

![](assets/8.png)

**Google-gebruikers**

Als de aangepaste SSO is ingesteld, wordt de [!UICONTROL Users] Deze pagina wordt alleen bijgewerkt om externe gebruikers weer te geven die zijn toegevoegd met Google-aanmeldingen. Omdat alle gebruikers met toegang door de configuratie worden bepaald SSO, zijn de extra externe gebruikers hier vermeld.

![](assets/9.png)

Alleen geldig [!DNL Google] accounts kunnen worden toegevoegd en er moet een gebruikersrol zijn gedefinieerd.

## Externe koppelingen {#external-links}

* [Okta](http://developer.okta.com/standards/SAML/setting_up_a_saml_application_in_okta)
* [Identiteit pingel](http://docs.pingidentity.com/bundle/p1_enterpriseConfigSsoSaml_cas/page/enableAppWithoutURL.html)
* [OneLogin](http://onelogin.service-now.com/support?id=kb_article&amp;sys_id=b2c91143db109700d5505eea4b9619d5)
* [Active Directory](http://docs.microsoft.com/en-us/azure/active-directory/active-directory-saas-custom-apps)
