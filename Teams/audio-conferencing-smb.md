---
title: Настройка голосовой конференции для малых и средних организаций
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: jonorton, tonysmit
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
description: 'Узнайте, как настроить голосовую конференцию в малых или средних организациях для пользователей, которые должны использовать телефон для звонков в собрании. '
ms.openlocfilehash: 648a6342adf0fc035dcd33c6eb11efb40b0d4eed
ms.sourcegitcommit: 739ffd5893abf6d181877d1110f9dc8230b3bfd2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328443"
---
# <a name="set-up-audio-conferencing-for-small-and-medium-businesses"></a>Настройка голосовой конференции для малых и средних организаций

Благодаря голосовой конференции пользователи могут звонить на собрания Teams с помощью телефона, а не с помощью приложения Teams на мобильном устройстве или с компьютера.  

Если вы используете не более 300 пользователей и не используете лицензий на голосовую связь, вы можете бесплатно подписаться на голосовую конференцию в течение одного года. Это бесплатное предложение доступно начиная с 1 октября 2020 г.

Лицензия на надстройку "звуковые конференции" может быть применена к пользователям, которые имеют лицензии Microsoft 365 Business Basic, Business E1, корпоративное и E3. Дополнительные сведения можно найти в разделе [лицензии на надстройки для Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)

> [!NOTE]
> Если у вас Корпоративная голосовая связь в корпоративной среде или Microsoft 365, вы не сможете использовать бесплатные видеоконференции, так как в этих лицензиях уже есть голосовые конференции.

В этой статье мы рассмотрим, как настроить голосовую конференцию. Вам нужно только настроить аудиоконференции для пользователей, планирующих или проводящих собрания. Участники собрания, вызывающие участие в собраниях, не нуждаются в лицензиях и других параметрах настройки. Дополнительные сведения можно найти в статье [звуковые конференции](audio-conferencing-in-office-365.md).

## <a name="step-1-get-audio-conferencing-licenses"></a>Действие 1: получение лицензий на голосовую конференцию

Получите одну лицензию на голосовую конференцию для каждого человека, который будет руководит собраниями. Для этого воспользуйтесь центром администрирования Microsoft 365.

1. В центре администрирования Microsoft 365 перейдите в раздел Услуги по **выставлению счетов**  >  **Purchase services**, а затем в нижней части страницы выберите пункт **надстройки**. 
2. Выберите **рекламный сведения о внедрении голосовой конференции Microsoft 365**  >  **Details**.
3. Введите число лицензий, необходимых для собрания, организаторов, а затем заполните свой заказ.

> [!NOTE]
> Снимите или установите флажок **автоматически назначать лицензии всем пользователям без лицензий**, в зависимости от того, хотите ли вы автоматически назначать лицензию на голосовую конференцию всем пользователям, у которых нет лицензии.

## <a name="step-2-assign-an-audio-conferencing-license-to-users-who-lead-meetings"></a>Шаг 2: назначение лицензии на голосовую конференцию пользователям, ведущим к собраниям

Назначьте лицензию каждому человеку, который будет руководить собраниями. Для этого воспользуйтесь центром администрирования Microsoft 365.

### <a name="assign-a-license-to-one-user"></a>Назначение лицензии одному пользователю

1. В центре администрирования Microsoft 365 перейдите в раздел **Users**  >  **Активные пользователи**пользователей.  
2. Выберите строку пользователя, которому нужно назначить лицензию, а затем в области выберите пункт **лицензии и приложения**.
3. Установите флажок **звуковые конференции Microsoft 365** и нажмите кнопку **сохранить изменения**. 

### <a name="assign-a-license-to-multiple-users"></a>Назначение лицензий нескольким пользователям

1. В центре администрирования Microsoft 365 перейдите в раздел **Users**  >  **Активные пользователи**пользователей.  
2. Выберите кружки рядом с пользователями, которым нужно назначить лицензию, а затем выберите **Управление лицензиями на продукты**.
3. В области **Управление лицензиями на продукты** нажмите кнопку **назначить больше**.
4. Установите флажок **звуковые конференции Microsoft 365** и нажмите кнопку **сохранить изменения**.  

## <a name="step-3-find-or-get-a-phone-number-for-your-conferencing-bridge"></a>Шаг 3: Поиск или получение номера телефона для моста конференц-связи

Для моста конференц-связи необходим номер телефона (номер службы), чтобы его можно было использовать в приглашениях на собрания. Вы можете выбрать использование **общего номера** или **специального номера**. Оба типа номеров могут использоваться любым вызывающим абонентом для присоединения к собранию.

### <a name="use-a-shared-number"></a>Использование общего числа

Общедоступный номер — это число, которое совместно используются во всех организациях. Общие номера назначаются автоматически при настройке голосовой конференции. Эти общие номера – это платные номера, на которые может взиматься плата за междугородние звонки.

Чтобы найти номер по умолчанию, назначенный мосту конференц-связи, в левой области навигации центра администрирования Microsoft Teams перейдите в **Meetings**  >  **мосты конференций**собраний, а затем найдите номер для ближайшего к вам расположению.

### <a name="get-a-dedicated-number"></a>Получить выделенный номер

Выделенный номер — это число, доступное только для пользователей. Выделенный номер может представлять собой платный номер или бесплатный номер. Чтобы использовать выделенный номер, необходимо сначала получить номер, а затем назначить его мосту конференц-связи.  

Есть несколько способов получить выделенный номер. Вы можете получить номер от корпорации Майкрософт или перевести (за один или несколько портов) от текущего поставщика услуг в корпорацию Майкрософт. Дополнительные сведения о том, как это сделать, можно найти в статье [Получение номеров служб](getting-service-phone-numbers.md).

> [!NOTE]
> Если вы используете бесплатный номер, вы должны сначала назначить лицензию на кредиты для каждого человека, который будет руководит собраниями. Дополнительные сведения можно найти в разделе [Настройка кредитов связи для вашей организации](set-up-communications-credits-for-your-organization.md).

После того как вы захотите свой номер, назначьте его мосту конференц-связи. Для этого воспользуйтесь центром администрирования Microsoft Teams.

1. В левой области навигации центра администрирования Microsoft Teams перейдите к **Meetings**  >  **мостам конференций**для собраний.
2. Нажмите кнопку **Добавить**, а затем выберите **платный номер** или бесплатный **номер**.
3. В области **Добавить номер телефона** выберите номер, а затем нажмите кнопку **Применить**.

## <a name="step-4-assign-a-dial-in-number-to-users-who-lead-meetings"></a>Шаг 4: назначение номера для подключения пользователям, ведущим к собраниям

Назначьте номер для подключения каждому человеку, который будет руководить собраниями. Для этого воспользуйтесь центром администрирования Microsoft Teams.

1. В левой области навигации центра администрирования Microsoft Teams выберите **Пользователи**, щелкните отображаемое имя пользователя и нажмите кнопку **изменить**.
2. Нажмите кнопку **изменить**   рядом с пунктом " **звуковые конференции**", а затем в области " **телеконференции**"   выберите номер в списке **платный**   или бесплатный **Toll-free**   номер, а затем нажмите кнопку **Применить**.

## <a name="step-5-schedule-a-teams-meeting-in-outlook"></a>Шаг 5: планирование собрания Teams в Outlook

Чтобы запланировать собрание, в Outlook перейдите в раздел **Календарь**, а затем нажмите кнопку **создать собрание Teams** . Номера для телефонного подключения, заданные пользователем, и идентификатор конференции автоматически добавляются в приглашение на собрание, отправленное участникам собрания.

Дополнительные сведения можно найти [в разделе Планирование собрания Teams в Outlook](https://support.microsoft.com/office/schedule-a-teams-meeting-from-outlook-883cc15c-580f-441a-92ea-0992c00a9b0f).

> [!NOTE]
> При желании вы можете настроить приглашения на собрание, чтобы добавить логотип компании, ссылки на веб-сайт службы поддержки и юридического лица, а также текстовый нижний колонтитул. См. [Настройка приглашений на собрания](meeting-settings-in-teams.md#customize-meeting-invitations)

## <a name="related-topics"></a>Статьи по теме

- [Аудиоконференции](audio-conferencing-in-office-365.md)
- [Настройка голосовой конференции для групп](set-up-audio-conferencing-in-teams.md)
- [Общие вопросы об аудиоконференциях](audio-conferencing-common-questions.md)
- [Идет загрузка служебных номеров](getting-service-phone-numbers.md)
- [Лицензии на надстройки Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [Назначение лицензий пользователям](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)