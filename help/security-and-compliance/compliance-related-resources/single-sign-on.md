---
unique-page-id: 18874761
description: Single Sign On -  [!DNL Marketo Measure]
title: Single Sign On
exl-id: a328e9cb-8352-4693-8a44-533e08f1a29c
source-git-commit: 666812e8bf095170d611cd694b5d0ac5151d8fdd
workflow-type: tm+mt
source-wordcount: '1257'
ht-degree: 0%

---

# Single Sign On {#single-sign-on}

Met SAML (security assertion markup language) voor SSO (Single Sign-On) kunnen gebruikers zich via de identiteitsprovider van een bedrijf verifiëren wanneer ze zich aanmelden bij de [!DNL Marketo Measure] -app. Met SSO kan een gebruiker één keer verifiëren, zonder dat aparte apps hoeven te worden geverifieerd. SAML is een vereiste voor zakelijke klanten omdat niet alle gebruikers een [!DNL Salesforce] - of [!DNL Google] -account binnen hun organisatie hebben. Om te schrapen, heeft [!DNL Marketo Measure] een oplossing van SAML ontwikkeld die de leveranciers van de bedrijfsidentiteit kan steunen.

>[!CAUTION]
>
>In dit artikel worden Single Sign On (SSO) en het geavanceerde CRM-gebruikersbeheer beschreven. Als uw rekening **na 9/10/2020** werd voorzien, negeert dit artikel, aangezien SSO en Identity Management binnen [&#x200B; Adobe Admin Console voor uw  [!DNL Marketo Measure]  integratie &#x200B;](/help/configuration-and-setup/getting-started-with-marketo-measure/marketo-measure-quick-start.md) zullen worden geplaatst.

>[!NOTE]
>
>Het is waarschijnlijk dat bedrijven verschillende identiteitsproviders gebruiken (bijvoorbeeld Ping Identity, Okta). De termen die worden gebruikt in de volgende instellingsinstructies en in de gebruikersinterface komen mogelijk niet direct overeen met de termen die worden gebruikt door uw identiteitsprovider.

## Vereisten {#requirements}

* Gebruiker met AccountAdmin-machtigingen in de [!DNL Marketo Measure] -app
* Gebruiker met administratieve toegang tot de Identiteitsprovider van de klant

## Aan de slag {#getting-started}

Ga om aan de slag te gaan naar Instellingen > Beveiliging > Verificatie in de [!DNL Marketo Measure] -toepassing. Dan schakelaar het Login Type aan Douane SSO om de configuratieopties te zien. De wijzigingen worden van kracht voordat u de verificatie test en onder aan de pagina op de knop **[!UICONTROL Save]** klikt.

![](assets/single-sign-on-1.png)

## Proces {#process}

[!DNL Marketo Measure] Single Sign On vereist dat u de verificatie-instellingen in een aantal stappen configureert, zodat u het risico hebt dat u niet uit uw [!DNL Marketo Measure] -account wordt vergrendeld.

Stel de [!DNL Marketo Measure] -toepassing in uw identiteitsprovider in. Zie externe documentatie die hieronder voor analyses wordt vermeld.

     a. Wanneer ertoe aangezet voor Enig Teken op URL of Ontvanger URL of Doel, de Dienst van de Klant van de Bevestiging van SAML (ACS) URL, gebruik [https://apps.bizible.com/BizibleSAML2/ReceiveSSORequest] (https://apps.bizible.com/BizibleSAML2/ReceiveSSORequest) 
    
     b. Wanneer ertoe aangezet voor de URL van de Beperking van het publiek of toepassing-bepaalde unieke herkenningsteken, gebruik [https://BizibleLPM] (https://biziblelpm/) 

Overschakelen naar Aangepaste SSO in de [!DNL Marketo Measure] -toepassing

     a. Zodra de Facturerende Groep voor uw Rekening is toegelaten, kunt u aan [!UICONTROL Settings] nu navigeren >> [!UICONTROL Security] >> [!UICONTROL Authentication]
    
     b. Door gebrek, zal uw Login Type aan &quot;Gebruikers van CRM worden geplaatst.&quot;
    
     c. Schakelaar het Type van Login aan &quot;Douane SSO&quot;om met het configuratieproces te beginnen.

De verbindingsinstellingen voor de configuratie van uw identiteitsprovider invullen

     a. Uw Identiteitsprovider kan een .xml-document met IDP-metagegevens geven waarmee de vereiste configuratievelden worden verwijderd. Laad de inhoud van het XML-document of vul de drie onderstaande velden in uit de uitvoer die is verkregen tijdens het configuratieproces van Identiteitsprovider. **U hoeft beide niet in te vullen.**
    
     i. IdP URL: URL die  [!DNL Marketo Measure]  moet richten om uw gebruikers in de  [!DNL Marketo Measure]  toepassing voor authentiek te verklaren. Wordt ook wel de &quot;Redirect URL&quot; genoemd.
     ii. IdP-uitgever: Een unieke id van de identiteitsprovider. Wordt ook wel de externe sleutel genoemd.
     iii. IdP Certificaat: Een openbare sleutel die  [!DNL Marketo Measure]  toestaat om de handtekening van alle reacties van de Leverancier van de Identiteit te verifiëren en te bevestigen.

Stel de vervaldatum van het token voor uw gebruikers in minuten in.

     a. [!DNL Marketo Measure]  staat een geheel aantal van 1 tot 1440 minuten toe. Nadat de de zittingstijd van een gebruiker is overschreden, zal de gebruiker het programma worden geopend zodra zij aan een nieuwe pagina navigeren.

Stel uw gebruikerskenmerkinstellingen in en wijs deze toe aan de respectievelijke voornaam, achternaam en e-mailadres.

     a. Door de attributen van SAML in te gaan,  [!DNL Marketo Measure]  zal uw gebruikers door de informatie kunnen erkennen die door wordt overgegaan.
    
     i. E-mailkenmerk: geef de kenmerknaam op die uw identiteitsprovider gebruikt voor het e-mailadres van de gebruiker.
     ii. Kenmerk voornaam: geef de kenmerknaam op die uw identiteitsprovider gebruikt voor de voornaam van de gebruiker.
     iii. Attribuut achternaam: geef de kenmerknaam op die uw identiteitsprovider gebruikt voor de achternaam van de gebruiker.
    
     b. Tip: Als u uw configuratie van SAML nu test, zullen wij uit de attributen e-mail, Voornaam, en Achternaam parseren die u voor deze sectie kunt gebruiken.

![](assets/single-sign-on-2.png)

Opstelling en kaart uw montages van de Rol van de Gebruiker aan de respectieve rollen of de groepen die van uw IdP worden geclassificeerd.

     a. De klanten hebben de optie om  [!DNL Marketo Measure]  gebruikersrollen toe te wijzen die op groepen worden gebaseerd die in hun Leverancier van de Identiteit worden bepaald. Door uw attributen van SAML in te gaan,  [!DNL Marketo Measure]  zal de rollen en de groepen van uw gebruiker aan  [!DNL Marketo Measure]  gebruikerstoestemmingen in kaart kunnen brengen. Wij adviseren hoogst dat u opstelling deze rollen zodat uw  [!DNL Marketo Measure]  beheerder voldoende rechten heeft om uw rekening bij te werken.
    
     b. Als er geen rollen of groepen zijn toegewezen, is de standaardinstelling dat alle werknemers in de Identiteitsprovider standaard gebruikerstoegang hebben.
    
     i. [!DNL Marketo Measure]  StandaardGebruiker: Verstrek de rol of groepswaarde (van uw leverancier SSO) voor gebruikers die read-only toegang tot de  [!DNL Marketo Measure]  toepassing zouden moeten hebben.
     ii. [!DNL Marketo Measure]  Gebruiker Admin van de Rekening: Verstrek de rol of groepswaarde (van uw leverancier SSO) voor gebruikers die administratieve toegang tot de  [!DNL Marketo Measure]  toepassing zouden moeten hebben. Dit betekent dat de rol toegang heeft tot configuraties en instellingen voor wijzigingen die betrekking hebben op uw account.
     iii. U moet een attribuut in uw IdP met de nauwkeurige naam van &quot;groepen&quot;hebben die de waarden bevat u in de &quot;Bizible Standard User&quot;of &quot;Bizible Account Admin User&quot;attributen plaatst.
    
     c. Als de veelvoudige rollen of de groepen aan een rol zouden moeten worden in kaart gebracht, ga elke waarde in die door een komma wordt gescheiden.

![](assets/single-sign-on-3.png)

Test de Single Sign On configuratie

     a. Voordat u op Opslaan kunt klikken, moet u op de knop [!UICONTROL Test SAML Authentication] klikken om te controleren of de instellingen correct zijn geconfigureerd.
    
     b. Als u een fout ziet &quot;mislukken&quot;, volgt u het bericht en probeert u het opnieuw.

![](assets/single-sign-on-4.png)

Sla uw instellingen op en geef uw collega&#39;s de opdracht om [!UICONTROL Single Sign On] te gebruiken met de nieuwe aangepaste URL voor aanmelden.

     a. Belangrijk: Zodra u uw nieuwe montages van de Authentificatie opslaat, is het mogelijk uw zitting zal eindigen zodra u aan een nieuwe pagina navigeert omdat u login door de Gebruikers van CRM en toegelaten Douane SSO hebt onbruikbaar gemaakt.

![](assets/single-sign-on-5.png)

Probeer het uit!

     a. Gebruik uw nieuw douanelogin URL van het Teken en poging om terug binnen aan de  [!DNL Marketo Measure]  Toepassing met uw geloofsbrieven van de Leverancier van de Identiteit te registreren.
    
     b. Het formaat zal als &quot;https://apps.adobe.com/business/[accountName] &grave; kijken 
    
     c. Gefeliciteerd! U hebt met succes opstelling het Enige Teken in de  [!DNL Marketo Measure]  Toepassing voor uw rekening!

![](assets/single-sign-on-6.png)

>[!NOTE]
>
>Nadat u SSO hebt geconfigureerd, hoeft u geen gebruikers meer toe te voegen binnen de [!DNL Marketo Measure] -toepassing. De levering van de gebruiker zou direct binnen uw Leverancier van de Identiteit moeten worden behandeld.

## CRM-gebruikers (Geavanceerde instellingen) {#crm-users-advanced-setup}

Standaard hebben alle accounts toegang tot de toepassing [!DNL Marketo Measure] met behulp van hun CRM-referenties. Soms moeten eigenaars van accounts de toegang tot bepaalde rollen beperken en deze niet openen voor alle gebruikers met een actieve CRM-licentie. Met de Geavanceerde instellingen kunt u uw CRM-rollen en -groepen toewijzen aan [!DNL Marketo Measure] -gebruikersmachtigingen.

Als geen rollen of groepen in kaart worden gebracht, is het gebrek dat plaatst dat alle actieve vergunningen in uw CRM Standaardgebruikerstoegang hebben.

* [!DNL Marketo Measure] Standaardgebruiker: geef de rol of groepswaarde op voor gebruikers die alleen-lezen toegang moeten hebben tot de [!DNL Marketo Measure] -toepassing.
* [!DNL Marketo Measure] Accountbeheerder gebruiker: geef de rol of groepswaarde op voor gebruikers die beheerdersrechten moeten hebben tot de [!DNL Marketo Measure] -toepassing. Dit betekent dat de rol toegang heeft tot configuraties en instellingen voor wijzigingen die betrekking hebben op uw account.

Als meerdere rollen of groepen moeten worden toegewezen aan een rol, voert u elke waarde in, gescheiden door een komma.

**Rollen van Salesforce**

Gebruik voor [!DNL Salesforce] Rollen de naam van elke rol. Alle rollen kunnen onder [!UICONTROL Setup] worden gevonden > [!UICONTROL Manage Users] > [!UICONTROL Roles] menu.

![](assets/6.png)

**Rollen van de Dynamiek**

Gebruik voor [!DNL Dynamics] Rollen de naam van elke beveiligingsrol. Alle Rollen van de Veiligheid kunnen onder [!UICONTROL Settings] worden gevonden > [!UICONTROL Security] > [!UICONTROL Security Roles] menu.

![](assets/7.png)

![](assets/8.png)

**de Gebruikers van Google**

Zodra de aangepaste SSO is ingesteld, wordt de pagina [!UICONTROL Users] bijgewerkt zodat alleen externe gebruikers worden weergegeven die zijn toegevoegd met Google-aanmeldingen. Omdat alle gebruikers met toegang door de configuratie worden bepaald SSO, zijn de extra externe gebruikers hier vermeld.

![](assets/9.png)

Alleen geldige [!DNL Google] -accounts kunnen worden toegevoegd en er moet een gebruikersrol zijn gedefinieerd.

## Externe koppelingen {#external-links}

* [&#x200B; Okta &#x200B;](https://developer.okta.com/standards/SAML/setting_up_a_saml_application_in_okta)
* [&#x200B; pingelt Identiteit &#x200B;](https://docs.pingidentity.com:443/bundle/p1_enterpriseConfigSsoSaml_cas/page/enableAppWithoutURL.html)
* [&#x200B; OneLogin &#x200B;](https://onelogin.service-now.com/support?id=kb_article&sys_id=b2c91143db109700d5505eea4b9619d5)
* [&#x200B; Actieve Folder &#x200B;](https://docs.microsoft.com/en-us/azure/active-directory/active-directory-saas-custom-apps)
