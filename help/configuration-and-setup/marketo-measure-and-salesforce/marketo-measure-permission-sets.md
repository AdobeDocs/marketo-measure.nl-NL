---
unique-page-id: 18874789
description: "[!DNL Marketo Measure] Machtigingssets - [!DNL Marketo Measure]"
title: "[!DNL Marketo Measure] Machtigingssets"
exl-id: 84b7aa24-3934-4584-af05-02e804d00a98
feature: Salesforce
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '245'
ht-degree: 0%

---

# [!DNL Marketo Measure] Machtigingssets {#marketo-measure-permission-sets}

Leer hoe u toegang krijgt tot en hoe u toewijst [!DNL Marketo Measure] Machtigingssets in Salesforce.

## [!DNL Marketo Measure] Machtigingssets {#marketo-measure-permission-sets-1}

Drie rechtensets worden opgenomen in de [!DNL Marketo Measure] Salesforce-pakket. Deze rechtensets bieden toegang tot [!DNL Marketo Measure] voor Admins, Marketers en Standard Users.

Om tot de Reeksen van de Toestemming in Salesforce toegang te hebben en toe te wijzen:

1. Klik op **[!UICONTROL Setup]**.
1. Klik in de linkermarge op **[!UICONTROL Users]** vervolgens **[!UICONTROL Permission Sets]**.
1. Selecteer de [!DNL Marketo Measure] Machtigingsset die u wilt toewijzen.
1. Klikken **[!UICONTROL Manage Assignments]** vervolgens **[!UICONTROL Add Assignments]**.
1. Selecteer de gebruikers voor de rechtenset en klik op **[!UICONTROL Assign]**.

   ![](assets/1-5.png)

## [!DNL Marketo Measure] Machtigingssets beschreven {#marketo-measure-permission-sets-explained}

<table> 
 <tbody> 
  <tr> 
   <td><span><strong>[!DNL Marketo Measure] Beheerder</strong></span></td> 
   <td><span>Biedt een SFDC-beheerder de mogelijkheid om records te maken, lezen, schrijven, verwijderen uit [!DNL Marketo Measure] objecten. De vergunning waarbij [!DNL Marketo Measure] deze machtigingsset moet zijn ingeschakeld wanneer gegevens naar SFDC worden gestuurd. Bovendien wordt aangeraden dat deze licentie geconverteerde leads kan bewerken in de scenario's waarin de lead eerder wordt geconverteerd [!DNL Marketo Measure] gegevens toepassen op de record. Dit zorgt voor een juiste rapportage tussen Salesforce en [!DNL Marketo Measure]. <a href="https://help.salesforce.com/articleView?id=release-notes.rn_sales_leads_view_converted.htm&amp;type=5&amp;release=206&amp;language=en_us">Meer hier lezen</a>.</span></td> 
  </tr> 
  <tr> 
   <td><span><strong>[!DNL Marketo Measure] Gebruiker van marketing</strong></span></td> 
   <td><span>Biedt een marketinggebruiker de mogelijkheid om records te lezen en te schrijven van [!DNL Marketo Measure] objecten. Alle leden van het marketingteam moeten de [!DNL Marketo Measure] Licentieset voor marketinggebruiker ingeschakeld. <br></span></td> 
  </tr> 
  <tr> 
   <td><span><strong>[!DNL Marketo Measure] Standaardgebruiker</strong></span></td> 
   <td><span>Biedt een gebruiker de mogelijkheid om records te lezen van [!DNL Marketo Measure] objecten.</span></td> 
  </tr> 
 </tbody> 
</table>

Binnenkomende verkoopontwikkelingsteams en accountmanagers kunnen profiteren van [!DNL Marketo Measure] gegevens. Als deze rollen zouden willen gebruiken [!DNL Marketo Measure] gegevens in de rapportage, [!DNL Marketo Measure] Standaardrechtenset van gebruiker.

>[!NOTE]
>
>Bovendien moet de gebruiker waarmee we verbinding hebben de &quot;Marketing User&quot; hebben [!DNL Salesforce] Profiel dat op gebruikersniveau is ingeschakeld voor toegang tot het Campagneobject. Klik op **[!UICONTROL Setup]** > **[!UICONTROL Manage Users]** > **[!UICONTROL Profiles]** > **[!UICONTROL Marketing User]** > **Toegewezen gebruikers**.
