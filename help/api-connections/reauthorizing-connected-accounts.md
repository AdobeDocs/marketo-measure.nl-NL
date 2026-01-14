---
description: Richtlijnen voor verbonden accounts opnieuw autoriseren voor Marketo Measure-gebruikers
title: Verbonden accounts opnieuw autoriseren
exl-id: 7abd1d67-5bed-45bb-844f-0ffd23c3d7f8
feature: APIs, Integration
hidefromtoc: true
source-git-commit: 0299ef68139df574bd1571a749baf1380a84319b
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 0%

---

# Verbonden accounts opnieuw autoriseren {#reauthorizing-connected-accounts}

Wanneer een account wordt losgekoppeld van uw [!DNL Marketo Measure] -account, wordt de status van het platform gewijzigd in &#39;Autorisatie vereist&#39; en wordt een rood sleutelpictogram weergegeven.

Als de verbinding met uw advertentieplatform wordt verbroken, kan [!DNL Marketo Measure] geen kostengegevens downloaden of, als u Automatisch inschakelen hebt ingeschakeld, de [!DNL Marketo Measure] UTM-parameters toevoegen aan nieuwe advertenties. [!DNL Marketo Measure] kan de UTM-parameters niet retroactief toevoegen aan aanraakpunten die vanaf het advertentieplatform zijn gemaakt terwijl de account is losgekoppeld.

Als de verbinding met uw CRM-platform wordt verbroken, kan [!DNL Marketo Measure] [!DNL Marketo Measure] -gegevens niet bijwerken of nieuwe aanraakpunten op uw org plaatsen. Nadat de CRM-verbinding opnieuw tot stand is gebracht, stuurt [!DNL Marketo Measure] alle gegevens die tijdens het verbreken van de verbinding zijn overgeslagen.

![](assets/utilizing-connections-7.png)

## Ongekoppelde accounts opnieuw autoriseren {#re-authorizing-disconnected-accounts}

1. Ga naar [ experience.adobe.com/marketo-measure ](https://experience.adobe.com/marketo-measure){target="_blank"} en login.
1. Selecteer **[!UICONTROL Settings]** onder het tabblad [!UICONTROL My Account] in de linkerbovenhoek.
1. Zoek de sectie Integraties aan de linkerkant en klik op **[!UICONTROL Connections]** .
1. Selecteer het symbool Rode sleutel naast het account dat opnieuw moet worden verbonden.
1. Er wordt een pop-upvenster weergegeven met de vraag of u de aanmeldingsgegevens voor de account wilt opgeven.
