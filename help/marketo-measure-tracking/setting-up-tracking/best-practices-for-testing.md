---
unique-page-id: 18874722
description: Beste praktijken voor het Testen - [!DNL Marketo Measure] - Productdocumentatie
title: Aanbevolen procedures voor het testen
exl-id: ff95a1a9-d324-47f5-b47d-39014dff77e4
source-git-commit: 993a326c377b3b6ff48c4e0114b59297f9ca2ca6
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 1%

---

# Aanbevolen procedures voor het testen {#best-practices-for-testing}

U moet alle verschillende typen formulieren testen om te controleren of de [!DNL Marketo Measure] JavaScript werkt goed.

## Aanbevolen testproces {#recommended-test-process}

1. Gebruik een incognitobrowser of wis uw cookies tussen elke formulierverzendingstest _en_ gebruik telkens een ander e-mailadres.

   >[!TIP]
   >
   >De beste manier is om een nep-e-mail te gebruiken die iets bevat dat aangeeft dat het een test is, en de tijd van de dag. Bijvoorbeeld: `testing830am@test.com`.

1. Begin uw onderzoek bij een onderzoeksmotor (b.v., `google.com`) of rechtstreeks naar een formulier navigeren.

1. Verzend het formulier op uw website met een uniek e-mailadres.

1. Registreer de URL van de pagina waarop u het formulier verzendt en het gebruikte e-mailadres.

1. Zoek de record die is gemaakt in uw CRM (lead of contact) voor het verzenden van het formulier en controleer of een aanraakpunt op de juiste wijze is gemaakt.

>[!NOTE]
>
>U kunt een [!DNL Marketo Measure] voorraadrapport zoals Leads met [!DNL Marketo Measure] Aanraakpunten of bekijk de lay-out van de pagina Regelafstand/Contactpersoon als u uw paginalay-outs wilt bijwerken met [!DNL Marketo Measure] details. Dit kan enige tijd duren voordat de gegevens zijn verwerkt.
