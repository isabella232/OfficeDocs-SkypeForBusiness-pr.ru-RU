---
title: Назначение политик в Teams
author: KarliStites
ms.author: kastites
manager: serdars
ms.reviewer: tomkau, saragava, ritikag, jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Узнайте о различных способах назначения политик и пакетов политики пользователям и группам в Microsoft Teams.
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: 00f78b3b134c6741a89c0d7b3f43d32a11c182cc
ms.sourcegitcommit: 2bb8556650120b4f7cf509d8ff93d7e4d058829b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574359"
---
# <a name="assign-policies-in-teams--getting-started"></a>Назначение политик в Teams — начало работы

Администраторы используют политики для управления функциями Teams, доступными пользователям в организации. Например, есть политики звонков, политики собраний и политики обмена сообщениями.

В организациях есть различные типы пользователей с уникальными потребностями. Настраиваемые политики, которые вы создаете и назначаете, по возможности настраивают параметры политики для разных наборов пользователей в зависимости от их потребностей.

Чтобы легко управлять политиками в организации, Teams предлагает несколько способов назначить политики пользователям. Назначьте политику непосредственно пользователям (по отдельности или в масштабе с помощью пакетного назначения) или группе, в которую они в являются участниками. Вы также можете использовать пакеты политик, чтобы назначить предустановленную коллекцию политик пользователям с похожими ролями. Выбор варианта зависит от количества политик, которые вы управляете, и от количества пользователей, которых вы назначаете. Глобальные политики (по умолчанию для всей организации) применяются к наибольшему числу пользователей в организации. Политики нужно назначать только тем пользователям, для кого требуются специализированные политики.

В этой статье описаны различные способы назначения политик пользователям и рекомендуемые сценарии использования.

Подробные сведения о назначении **политик** пользователям и группам см. в сведениях о назначении политик [пользователям и группам.](assign-policies-users-and-groups.md) Подробные сведения о **назначении пакетов политики** см. в [сведениях о назначении пакетов политики.](assign-policy-packages.md)

## <a name="which-policy-takes-precedence"></a>Какая политика имеет приоритет?

У пользователя есть одна эффективная политика для каждого типа политики. Вполне возможно, что пользователю напрямую назначена политика, а также она входит в одну или несколько групп, которые назначены политику того же типа. Какая политика имеет приоритет в подобных сценариях? Эффективная политика пользователя определяется согласно правилам приоритета.

Если пользователю непосредственно назначена политика (по отдельности или через пакетное назначение), она имеет приоритет. В следующем наглядном примере эффективной политикой пользователя является политика собраний По квадрату1, которая непосредственно назначена пользователю.

![Схема, показывающая приоритет непосредственно назначенной политики](media/assign-policies-example-directly-assigned.png)

Если пользователю не назначена непосредственно политика заданного типа, политика, назначенная группе, в которую входит пользователь, имеет приоритет. Если пользователь входит в несколько групп, приоритет имеет политика[](assign-policies-users-and-groups.md#group-assignment-ranking)с наивысшим (ранжированием назначений групп) для данного типа политики.

В этом наглядном примере эффективной политикой пользователя является политика Exec Teams и HD с наивысшим ранжированием назначений по сравнению с другими группами, в которые входит пользователь, и которым назначена политика того же типа политики.  

![Схема, показывающая, как политика, наследуемая от группы, имеет приоритет](media/assign-policies-example-group.png)

Если пользователю не назначена политика напрямую или он не входит в какие-либо группы, ему предоставляется глобальная политика (по умолчанию в организации). Вот наглядный пример.

![Схема, показывающая приоритет глобальной политики](media/assign-policies-example-global.png)

Подробнее см. в[(правилах приоритета).](assign-policies-users-and-groups.md#precedence-rules)

## <a name="ways-to-assign-policies"></a>Способы назначения политик

Ниже представлен обзор способов назначения политик пользователям, а также рекомендуемых сценариев для каждого из них. Пере выберите ссылки, чтобы узнать больше.

Прежде чем назначать политики отдельным пользователям или группам, начните с настройки глобальных (по умолчанию [в организации)](#set-the-global-policies) политик, которые будут применяться к наибольшему числу пользователей в организации.  После того как будут настроены глобальные политики, вам потребуется назначить политики только тем пользователям, для кого требуются специализированные политики.

|Сделайте это  |Если...  | Использование...
|---------|---------|----|
|[Назначение политики отдельным пользователям](assign-policies-users-and-groups.md#assign-a-policy-to-individual-users)   | Вы только начинаете работу с Teams или вам нужно назначить лишь одну или несколько политик небольшому количеству пользователей. |Центр администрирования Microsoft Teams или командлеты PowerShell в модуле Teams PowerShell
|[Назначение политики группе](assign-policies-users-and-groups.md#assign-a-policy-to-a-group) |Назначать политики, основанные на членстве пользователя в группах. Например, назначьте политику всем пользователям в группе безопасности или списке рассылки.| Центр администрирования Microsoft Teams или командлеты PowerShell в модуле Teams PowerShell|
|[Назначение политики для пакета пользователей](assign-policies-users-and-groups.md#assign-a-policy-to-a-batch-of-users)   | Назначать политики большим наборам пользователей. Например, можно назначить политику одновременно сотням или тысячам пользователей в организации. |Центр администрирования Microsoft Teams или командлеты PowerShell в модуле Teams PowerShell|
|[Назначение пакета политики пользователям](assign-policy-packages.md#assign-a-policy-package-to-users)  |Назначьте несколько политик определенным наборам пользователей в организации с одинаковыми или похожими ролями. Например, назначьте пакет политики "Образование (преподаватель)" преподавателям в вашем учебном за учебных заведениях, чтобы предоставить им полный доступ к чатам, звонкам и собраниям. Назначьте пакет политики "Образование (дополнительное учебное заведения)" дополнительным учащимся, чтобы ограничить некоторые возможности, такие как частные вызовы.  |Центр администрирования Microsoft Teams или командлеты PowerShell в модуле Teams PowerShell|
|[Назначение пакета политики группе (в](assign-policy-packages.md#assign-a-policy-package-to-a-group) режиме личной предварительной версии)   |Назначьте несколько политик группе пользователей в организации с одинаковыми или похожими ролями. Например, назначьте пакет политики всем пользователям в группе безопасности или списке рассылки. |Центр администрирования Microsoft Teams (скоро появится) или командлеты PowerShell в модуле Teams PowerShell|
|[Назначение пакета политики пакету пользователей](assign-policy-packages.md#assign-a-policy-package-to-a-batch-of-users)|Назначьте несколько политик пакету пользователей в организации с одинаковыми или похожими ролями. Например, назначьте пакет политики "Образование (преподаватель)" всем преподавателям в учебном за учебных заведениях с помощью пакетного задания, чтобы предоставить им полный доступ к чатам, звонкам и собраниям. Назначьте пакет политики "Образование (дополнительное учебное заведения)" пакету дополнительных учащихся, чтобы ограничить некоторые возможности, такие как частные вызовы.|Командлеты PowerShell в модуле Teams PowerShell|

## <a name="set-the-global-policies"></a>Настройка глобальных политик

Выполните эти действия, чтобы настроить глобальные политики (по умолчанию в организации) для каждого типа политики.

### <a name="using-the-microsoft-teams-admin-center"></a>С помощью Центра администрирования Microsoft Teams

1. В левой области навигации Центра администрирования Microsoft Teams перейдите на страницу политики для типа политики, который вы хотите обновить. Например, политики **Teams** Teams, политики собраний для собраний, политики обмена сообщениями или политики  >     >   **голосовых**   >  **звонков.**
2. Выберите **глобальную политику (по умолчанию** для всей организации), чтобы просмотреть текущие параметры.
3. Обновив политику, выберите **"Применить".**

![Обновление глобальной политики в Центре администрирования Teams](media/assign-globalpolicy.png)

### <a name="using-powershell"></a>С помощью PowerShell

Чтобы настроить глобальные политики с помощью PowerShell, используйте глобальный идентификатор.  Для начала просмотрите текущую глобальную политику, чтобы определить, какой параметр вы хотите изменить.

```powershell
Get-CsTeamsMessagingPolicy -Identity Global
 
Identity                      : Global
Description                   :
AllowUrlPreviews              : True
AllowOwnerDeleteMessage       : False
AllowUserEditMessage          : True
AllowUserDeleteMessage        : True
AllowUserChat                 : True
AllowRemoveUser               : True
AllowGiphy                    : True
GiphyRatingType               : Moderate
AllowMemes                    : True
AllowImmersiveReader          : True
AllowStickers                 : True
AllowUserTranslation          : False
ReadReceiptsEnabledType       : UserPreference
AllowPriorityMessages         : True
ChannelsInChatListEnabledType : DisabledUserOverride
AudioMessageEnabledType       : ChatsAndChannels
Expand (20 lines) Collapse 
```

Затем при необходимости обновим глобальную политику.  Вам нужно только указать значения для параметров, которые вы хотите изменить.

```powershell
Set-CsTeamsMessagingPolicy -Identity Global -AllowUserEditMessage $false
```

## <a name="view-your-policy-assignments-in-the-activity-log"></a>Просмотр назначений политики в журнале действий

При назначении политик пользователям в Центре администрирования Microsoft Teams можно просмотреть состояние этих назначений политики в журнале действий. В журнале действий показаны назначения политик более чем 20 пользователям через Центр администрирования Microsoft Teams за последние 30 дней. Имейте в виду, что в журнале действий не показываются назначения пакетов политики, назначения политик пакетам менее 20 пользователей через Центр администрирования Microsoft Teams или назначения политик через PowerShell.

![Снимок экрана: страница журнала действий](media/activity-log.png)

## <a name="view-your-policy-assignment-activities-in-the-activity-log"></a>Просмотр действий с назначением политики в журнале действий

Чтобы просмотреть назначения политики в журнале действий:

1. В левой области навигации Центра администрирования Microsoft Teams перейдите на панель **мониторинга,** а затем в журнале действий выберите "Просмотреть **сведения".**
2. Вы можете просмотреть все назначения политики или отфильтровать список по статусу, чтобы отфильтровать только те **назначения,** которые не были на запущены, выполнены или **завершены.** Вы увидите следующие сведения о каждом задании:
    - **Name**: имя назначения политики. Щелкните ссылку, чтобы просмотреть дополнительные сведения. Это включает количество пользователей, которые назначены политике, а также количество заданий, которые были выполнены, выполнены, выполнены и не на запущены. Вы также увидите список пользователей в пакете, а также состояние и результат для каждого пользователя. Ниже приводится пример.

        ![Снимок экрана:](media/activity-log-policy-assignment-detail.png)

    - **Отправлено:** дата и время отправки назначения политики.
    - **Время завершения:** дата и время завершения назначения политики.
    - **Влияние на:** количество пользователей в пакете.
    - **Общее состояние:** состояние назначения политики.

> [!NOTE]
> Вы также можете зайти в журнал действий на странице **"Пользователи".** После нажатия **кнопки "Применить"** для отправки задания массовой политики в верхней части страницы вы увидите баннер. Щелкните **ссылку в журнале** действий на баннере.

## <a name="related-topics"></a>Статьи по теме

- [Назначение политик пользователям и группам](assign-policies-users-and-groups.md)
- [Назначение пакетов политики пользователям и группам](assign-policy-packages.md)
- [Управление teams с помощью политик](manage-teams-with-policies.md)
- [Обзор PowerShell в Teams](teams-powershell-overview.md)