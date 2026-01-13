---
description: '[!DNL Marketo Measure] Machtigingssets -  [!DNL Marketo Measure]'
title: '[!DNL Marketo Measure] Machtigingssets'
exl-id: 84b7aa24-3934-4584-af05-02e804d00a98
feature: Salesforce
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 0%

---


# [!DNL Marketo Measure] Machtigingssets {#marketo-measure-permission-sets}

Leer hoe u [!DNL Marketo Measure] Machtigingssets in Salesforce kunt openen en toewijzen.

## [!DNL Marketo Measure] Machtigingssets {#marketo-measure-permission-sets-1}

Het Salesforce-pakket [!DNL Marketo Measure] bevat drie rechtensets. Deze rechtensets bieden toegang tot [!DNL Marketo Measure] voor Admins, Marketers en Standaardgebruikers.

Machtigingen openen en toewijzen in Salesforce:

1. Klik op **[!UICONTROL Setup]**.
1. Klik in de linkermarge op **[!UICONTROL Users]** en vervolgens op **[!UICONTROL Permission Sets]** .
1. Selecteer de [!DNL Marketo Measure] machtigingsset die u wilt toewijzen.
1. Klik op **[!UICONTROL Manage Assignments]** en vervolgens op **[!UICONTROL Add Assignments]** .
1. Selecteer de gebruikers voor de rechtenset en klik op **[!UICONTROL Assign]** .

   ![ 5 ](assets/1-5.png)

## [!DNL Marketo Measure] Verklaarde machtigingssets {#marketo-measure-permission-sets-explained}

<table>
 <tbody>
  <tr>
   <td><span><strong>[!DNL Marketo Measure] Beheerder</strong></span></td>
   <td><span>Hiermee kan een SFDC-beheerder records maken, lezen, schrijven en verwijderen uit [!DNL Marketo Measure] -objecten. Voor de licentie waaronder [!DNL Marketo Measure] gegevens naar SFDC verzendt, moet deze machtiging zijn ingeschakeld. Bovendien wordt aangeraden dat deze licentie geconverteerde leads kan bewerken in de scenario's waarin de lead wordt geconverteerd voordat [!DNL Marketo Measure] gegevens op de record toepast. Dit zorgt voor een juiste rapportage tussen Salesforce en [!DNL Marketo Measure] . <a href="https://help.salesforce.com/articleView?id=release-notes.rn_sales_leads_view_converted.htm&amp;type=5&amp;release=206&amp;language=en_us"> hier gelezen meer </a>.</span></td>
  </tr>
  <tr>
   <td><span><strong>[!DNL Marketo Measure] Gebruiker van marketing</strong></span></td>
   <td><span>Biedt een marketinggebruiker de mogelijkheid om records van [!DNL Marketo Measure] -objecten te lezen en te schrijven. Voor alle leden van het marketingteam moet de machtiging [!DNL Marketo Measure] Gebruiker voor het in de handel brengen zijn ingeschakeld. <br></span></td>
  </tr>
  <tr>
   <td><span><strong>[!DNL Marketo Measure] Standaardgebruiker</strong></span></td>
   <td><span>Biedt de gebruiker de mogelijkheid om records van [!DNL Marketo Measure] -objecten te lezen.</span></td>
  </tr>
 </tbody>
</table>

Binnenkomende verkoopontwikkelingsteams en accountmanagers kunnen profiteren van [!DNL Marketo Measure] -gegevens. Als deze rollen [!DNL Marketo Measure] -gegevens willen gebruiken voor rapportage, schakelt u de [!DNL Marketo Measure] Standard User-rechtenset in.

>[!NOTE]
>Bovendien moet het profiel &quot;Gebruiker in de handel brengen&quot; [!DNL Salesforce] van de gebruiker waarmee wij verbinding hebben, op gebruikersniveau zijn ingeschakeld om toegang te krijgen tot het Campagneobject. Om dit te controleren, klik in **[!UICONTROL Setup]** > **[!UICONTROL Manage Users]** > **[!UICONTROL Profiles]** > **[!UICONTROL Marketing User]** > **Toegewezen Gebruikers**.
