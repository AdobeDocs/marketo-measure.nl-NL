---
description: Beste praktijken voor het Testen -  [!DNL Marketo Measure]
title: Aanbevolen procedures voor het testen
exl-id: ff95a1a9-d324-47f5-b47d-39014dff77e4
feature: Tracking
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 0%

---


# Aanbevolen procedures voor het testen {#best-practices-for-testing}

Test alle verschillende typen formulieren die u nodig hebt om te controleren of de [!DNL Marketo Measure] JavaScript goed werkt.

## Aanbevolen testproces {#recommended-test-process}

1. Gebruik een incognitobrowser of ontruim uw koekjes tussen elke test van de vormvoorlegging _en_ gebruik telkens een verschillend e-mailadres.

   >[!TIP]
   >De beste manier is om een nep-e-mail te gebruiken die iets bevat dat aangeeft dat het een test is, en de tijd van de dag. Bijvoorbeeld: `testing830am@test.com` .

1. Start de zoekopdracht bij een zoekprogramma (bijvoorbeeld `google.com` ) of navigeer rechtstreeks naar een formulier.

1. Verzend het formulier op uw website met een uniek e-mailadres.

1. Registreer de URL van de pagina waarop u het formulier verzendt en het gebruikte e-mailadres.

1. Zoek de record die is gemaakt in uw CRM (lead of contact) voor het verzenden van het formulier en controleer of een aanraakpunt op de juiste wijze is gemaakt.

>[!NOTE]
>U kunt een [!DNL Marketo Measure] -voorraadrapport gebruiken, zoals Leads met [!DNL Marketo Measure] aanraakpunten, of de pagina-indeling Lead/Contact weergeven als u uw paginalay-outs wilt bijwerken met [!DNL Marketo Measure] -gegevens. Dit kan enige tijd duren voordat de gegevens zijn verwerkt.
