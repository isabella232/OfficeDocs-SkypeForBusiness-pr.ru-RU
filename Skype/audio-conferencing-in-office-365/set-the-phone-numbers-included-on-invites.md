---
title: "Определение телефонных номеров для аудиоконференций, которые организаторы собраний могут включить в приглашения"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/21/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
- Strat_SB_PSTN
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
description: "Get the steps to create a default phone number for callers to join a Skype for Business Online meeting. "
---

# Определение телефонных номеров для аудиоконференций, которые организаторы собраний могут включить в приглашения

Аудиоконференция в Office 365 позволяет пользователям вашей организации создавать собрания Skype для бизнеса и Microsoft Teams для подключения к ним пользователей по обычной телефонной связи. В Office 365 имеется возможность использования моста аудиоконференций Майкрософт или моста аудиоконференций сторонних производителей, которые размещены у утвержденного поставщика услуг аудиоконференций.
  
Мост конференц-связи предоставляет вашей организации ряд телефонных номеров для подключения. Все эти номера могут быть использованы для подключения к собраниям, созданным организаторами, однако вы можете выбрать, какие номера будут указаны в приглашениях на собрания.
  
> [!NOTE]
> Организатор собрания может использовать не более одного платного и одного бесплатного телефонного номера в приглашении на собрание, однако также имеется ссылка в нижней части приглашения на собрания, по которой открывается список всех телефонных номеров для подключения к собранию. 
  
## Настройка организатором собрания телефонного номера по умолчанию для подключения

1. Войдите в Office 365 под своей учебной или рабочей учетной записью.
    
2. Выберите **Центры администрирования** > **Skype для бизнеса**.
    
3. Выберите **Пользователи**.
    
    ![In the Skype for Business admin center, choose Users.](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. Выберите, каких пользователей нужно изменить.
    
  - Чтобы выделить одного пользователя, щелкните его имя.
    
  - Чтобы выделить всех пользователей на странице, установите флажок **Отображаемое имя** в верхней части списка.
    
  - Чтобы выделить нескольких пользователей, щелкните каждого из них, удерживая нажатой клавишу CTRL.
    
5. В области справа выберите **Изменить**.
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. В раскрывающемся списке **Поставщики** выберите поставщика для пользователя. В зависимости от выбранного поставщика заполните следующие поля.
    
  - Если **поставщиком является Майкрософт**, используйте списки **Платный номер по умолчанию** и **Бесплатный номер по умолчанию** для выбора номеров по умолчанию для данного пользователя.
    
    > [!NOTE]
    > Прежде чем мост конференц-связи может быть задан как бесплатный номер по умолчанию для пользователей, ему следует назначить хотя бы один бесплатный номер. Чтобы получить бесплатный телефонный номер, ознакомьтесь с разделом [Получение номеров телефонов служб для Skype для бизнеса](../what-is-phone-system-in-office-365/getting-service-phone-numbers-for-skype-for-business-and-microsoft-teams.md). 
  
  - Если применяется **сторонний поставщик**, используйте поля **Платный номер** и **Бесплатный номер** для ввода номеров для данного пользователя.
    
## Сброс номеров доступа к конференции с телефонным подключением

1. В **Центр администрирования Skype для бизнеса**выберите **Аудиоконференция**.
    
2. В верхней части страницы щелкните **Пользователи**.
    
3. Выберите пользователей, параметры которых нужно сбросить, а затем щелкните **Очистить**.
    
    ![Choose Clear to reset phone numbers.](../images/28664b62-0d6f-42e1-960b-fdb1c6c14020.png)
  
По умолчанию при изменении настроек конференц-связи пользователям отправляются сообщения электронной почты. Чтобы изменить это поведение, см. статью [Включение и отключение отправки сообщения электронной почты при изменении параметров аудиоконференций](enable-or-disable-sending-emails-when-audio-conferencing-settings-change.md).
  
> [!IMPORTANT]
> При изменении настроек аудиоконференции необходимо обновить и отправить участникам повторяющиеся и будущие собрания Skype для бизнеса и Microsoft Teams. 
  
## Сведения по управлению с помощью Windows PowerShell

- Для экономии времени или автоматизации процесса можно воспользоваться командлетом [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688).
    
- Используйте командлет [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) для изменения платного или бесплатного номера по умолчанию для определенных пользователей.
    
    Чтобы изменить бесплатный номер по умолчанию для определенного пользователя, выполните командлет
    
  ```
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   +180045551234
  ```

- Используйте командлет **Set-CsOnlineDialInConferencingUserDefaultNumber** для изменения платного или бесплатного номера по умолчанию для пользователей на основе исходного номера по умолчанию, свойственного для местоположения этих пользователей.
    
    > [!NOTE]
    > Чтобы узнать идентификатор BridgeID, используйте командлет **Get-CsOnlineDialInConferencingBridge**.
  
  ```
  
  ```

  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings 
  ```

  - Чтобы задать бесплатный номер +18005551234 в качестве номера по умолчанию для всех пользователей, не имеющих номера по умолчанию, выполните командлет
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>  
  ```

  - Чтобы изменить бесплатный номер по умолчанию для всех пользователей с бесплатным номером по умолчанию +18005551234 на +18005551239, выполните командлет
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id>
  ```

  - Чтобы задать бесплатный номер +18005551234 в качестве номера по умолчанию для всех пользователей, расположенных в США, выполните командлет
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```

  - Чтобы изменить бесплатный номер по умолчанию для всех пользователей с бесплатным номером по умолчанию +18005551234 на +18005551239 и повторно запланировать все собрания с новым бесплатным номером, выполните командлет
    
  -     > [!NOTE]
    > Используемое выше местоположение должно совпадать с контактными данными пользователей, которые указаны в Центре администрирования Office 365. 
  
- Windows PowerShell, дает возможность управлять пользователями, предоставляя им права на определенные действия. С помощью Windows PowerShell вы можете управлять Office 365 и Skype для бизнеса online, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.
    
  - [Введение в Windows PowerShell и Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Шесть причин использовать Windows PowerShell для управления Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центра администрирования Office 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах:
    
  - [Лучшие способы управления Office 365 с помощью Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Использование Windows PowerShell для управления Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## См. также:

[Настройка аудиоконференций в Skype для бизнеса и Microsoft Teams](set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams.md)
  
