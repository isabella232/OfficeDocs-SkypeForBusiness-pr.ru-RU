---
title: Управление номерами телефонов организации
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: davlick, roykuntz, jastark
ms.topic: conceptual
ms.assetid: 6b61cb3c-361c-48a8-a9ef-d81bddde27bb
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.voice.phonenumbers.overview
- ms.teamsadmincenter.voice.searchandacquire.PSTNpartner
- ms.lync.lac.NewNumberManualAcquisitionOpenSupportTicket
- ms.lync.lac.VASAMissingGeoCodes
- Calling Plans
- seo-marvel-apr2020
description: Узнайте, как получить и управлять пользовательскими (абонентами) и номерами телефонов служб (платных и бесплатных) для Microsoft Teams организации.
ms.openlocfilehash: d29781e16c881c9b0e00e39c6e57314c6696d8bb
ms.sourcegitcommit: 9364f4fdf3dcd5ab6805360ff913d4e2e7ca9cfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2021
ms.locfileid: "59432808"
---
# <a name="manage-telephone-numbers-for-your-organization"></a>Управление телефонными номерами для организации

В настоящее время корпорация Майкрософт поддерживает два типа номеров телефонов: 

- [**Номера пользователей**](#user-telephone-numbers), также называемые номерами подписчиков, которые можно на назначены пользователям в вашей организации.

- [**Номера служб,**](#service-telephone-numbers)которые назначены таким службам, как аудиоконференция, автоотчеты или [](deploy-audio-conferencing-teams-landing-page.md) [очереди вызовов.](plan-auto-attendant-call-queue.md) [](plan-auto-attendant-call-queue.md)

Корпорация Майкрософт работает над упрощением типов номеров, но в настоящее время необходимо решить:

- В каких расположениях нужны новые телефонные номера от Майкрософт?
- Какой тип номера телефона (абонент или служба) мне нужен?
- Как перенос существующих телефонных номеров в Teams?

Способ приобретения номеров телефонов и управление ими зависит от варианта подключения к ННП.

- Сведения об управлении телефонными номерами для плана звонков Майкрософт см. в этой [теме.](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

- Сведения об управлении телефонными номерами для операторов Подключение см. в этой [Подключение.](operator-connect-configure.md#set-up-phone-numbers)

- Сведения об управлении телефонными номерами для прямой маршрутии см. в настройках телефонного номера и в том, как включить корпоративную [голосовую и голосовую почту.](direct-routing-enable-users.md#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail-online)

Если вам нужны дополнительные или другие типы номеров, кроме тех, которые видны в Центре администрирования Microsoft Teams, вы можете отправить запрос на номер телефона в центр обслуживания номеров Телефон [номеров](https://pstnsd.powerappsportals.com/).

## <a name="user-telephone-numbers"></a>Номера телефонов пользователей

Существует два типа телефонных номеров пользователей, которые можно на назначены пользователям в организации:  
    
- **Географические числа** имеют отношение к географической области и являются наиболее распространенными. Например, географические телефонные номера в большинстве случаев могут использоваться только в пределах определенного адреса, города, области или региона.
    
- **Не географические номера** называются национальными номерами или номерами VoIP. Эти числа не имеют отношения к географическим областям в стране или регионе. Например, не географические номера часто имеют одинаковые затраты при вызове номера из любой точки страны или региона. Кроме того, в некоторых странах, например в Дания, доступны только не географическое число.


## <a name="service-telephone-numbers"></a>Номера телефонов служб  

В этом разделе описаны номера служб, доступные корпорацией Майкрософт, которые включены в ваш лицензирование. Для получения сведений о номерах служб, предоставляемых оператором Подключение или Прямой маршрутией, обратитесь к поставщику услуг. 

Существует два типа номеров телефонов служб, предоставляемых корпорацией Майкрософт: платные и бесплатные, которые можно на назначены таким службам, как аудиоконференция, автоотчеты или очереди вызовов. Номера служб имеют более высокую пропускную способность при одновременном вызове, чем номера пользователей. Доступность номера службы зависит от страны или региона и типа номера (как платный, так и бесплатный). Лицензии Майкрософт на телефонию в каждой стране или регионе определяют, для какого номера можно использовать этот номер.
    
 - **Платные номера служб.** Существует два типа платных номеров служб, которые могут оказаться платными для вызываемого звонка:
    
   - **Географические числа** Географические числа имеют отношение к географической области. Например, географические телефонные номера в большинстве случаев могут использоваться только в пределах определенного адреса, города, области или региона.
        
   - **Не географическое число** Не географическое число — это национальные номера, которые не имеют отношения к географическому региону в стране или регионе. Например, не географические номера часто имеют одинаковые затраты при вызове номера из любой точки страны или региона.
   
- **Бесплатные номера служб.** Как правило, эти номера служб не являются платными для вызываемого звонка. Teams предоставляет бесплатные номера национальных номеров в более чем 60 странах и регионах.
    
    > [!CAUTION]
    > Некоторые страны и регионы и типы номеров, например звонки с мобильных телефонов, в некоторых случаях могут понести платные затраты для вызываемого звонка. 


    
  
> [!NOTE]
> Если вам нужно получить больше номеров телефонов, обратитесь в центр обслуживания Телефон [номеров.](https://pstnsd.powerappsportals.com/)