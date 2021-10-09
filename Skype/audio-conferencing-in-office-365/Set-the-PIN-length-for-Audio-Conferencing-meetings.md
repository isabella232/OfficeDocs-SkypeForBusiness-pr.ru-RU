---
title: "Установка длины ПИН-кода для собраний с телефонным подключением"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/15/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- Strat_SB_PSTN
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
description: "Learn the parameters for the length and requirements of a PIN and see how to set the length for meetings in Skype for Business."
---

# Установка длины ПИН-кода для собраний с телефонным подключением

При настройке конференц-связи с телефонным подключением в Skype для бизнеса online, вы получите номера телефонов и мост конференц-связи. Мост для конференц-связи может содержать один или несколько телефонных номеров. Номер телефона, который вы установили, будет включен в приглашение на собрание.
  
Мост для конференц-связи обеспечивает ответ на звонок пользователя, желающего подключиться к собранию по телефону. Он отвечает звонящему и озвучивает голосовые подсказки автосекретаря системы и далее, в зависимости от ваших настроек, может воспроизвести уведомление и попросить звонящих записать их имена. В настройках моста Skype для бизнеса online вы можете менять настройки уведомлений собрания, подключения к собранию и устанавливать длину ПИН-кодов, используемых организаторами собраний. ПИН-коды позволяют организаторам собраний начинать собрания.
  
## Установка длины ПИН-кода

### Установка длины ПИН-кода для организаторов собрания

1. Войдите в Office 365 под своей учебной или рабочей учетной записью.
    
2. Перейдите в раздел **Центр администрирования Office 365** > **Skype для бизнеса**.
    
3. В окне **Центр администрирования Skype для бизнеса**, в левой панели навигации перейдите в **Конференц-связь с телефонным подключением** > **Параметры моста Microsoft**.
    
4. В разделе **Безопасность** > **Длина ПИН-кода** > укажите количество цифр в ПИН-коде, затем нажмите кнопку **Сохранить**.
    
> [!NOTE]
> ПИН-код отличается от идентификатора конференции. Идентификаторы конференции использоваться вызывающими абонентами, присоединяющимися к собранию. Они применяются для идентификации собрания. ПИН-код используется для идентификации звонящего как организатора собрания. 
  
## Дополнительные сведения о параметрах ПИН-кода

- ПИН-коды могут быть от 4 до 12 цифр - по умолчанию это 5. Цифры используются только при создании ПИН-кодов. Буквы и специальные символы не используются.
    
- ПИН-код требуется только организатору собрания, когда пользователь клиента Skype для бизнеса еще не начал собрание. Если кто-либо звонит, чтобы присоединиться к собранию, организатору собрания необходим ПИН-код, чтобы начать собрание.
    
- Параметры безопасности ПИН-кода применяются ко всем телефонным номерам, связанным с мостом Microsoft. Они будут применяться ко всем собраниям, где используются телефонные номера, связанные с данным мостом для аудиоконференций.
    
## Сведения по управлению с помощью Windows PowerShell

- Для экономии времени или автоматизации процесса можно воспользоваться командлетом [Set-CsOnlineDialInConferencingTenantSettings](http://go.microsoft.com/fwlink/?LinkId=715757).
    
- Для установки длины ПИН-кода в 8 цифр:  `Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`
    
- Windows PowerShell дает возможность управлять пользователями, предоставляя им права на определенные действия. С его помощью вы можете управлять Office 365, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.
    
  - [Шесть причин использовать Windows PowerShell для управления Office 365](http://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Лучшие способы управления Office 365 с помощью Windows PowerShell](http://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только центра администрирования Office 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах:
    
  - [Введение в Windows PowerShell и Skype для бизнеса Online](http://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Использование Windows PowerShell для управления Skype для бизнеса Online](http://go.microsoft.com/fwlink/?LinkId=525453)
    
    [Использование Windows PowerShell для управления Skype для бизнеса Online](http://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](http://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Модуль Windows PowerShell для Skype для бизнеса online позволяет запускать удаленные сеансы Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль для 64-разрядных систем можно загрузить из Центра загрузки Microsoft здесь: [Модуль Windows PowerShell для Skype для бизнеса Online](http://go.microsoft.com/fwlink/?LinkId=294688). 
  
## См. Также:

#### 

[Конференц-связь с телефонным подключением в Office 365](../misctopics/dial-in-conferencing-in-office-365.md)
