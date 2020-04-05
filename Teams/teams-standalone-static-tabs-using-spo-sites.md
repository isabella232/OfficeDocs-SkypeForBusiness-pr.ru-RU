---
title: Создание приложения "портал интрасети" для Рабочей группы на сайте SharePoint Online или на странице
author: LanaChin
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
description: Вы можете использовать существующий сайт или страницу SharePoint Online и создать отдельную статическую вкладку, которая может использоваться в качестве портала интрасети для вашей организации.
localization_priority: Normal
ms.openlocfilehash: 0215a2e1f79627f55bc14c00a099b25d2859b6f9
ms.sourcegitcommit: f0f2fa999c1ca4a1118377c7938a247f79217609
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2020
ms.locfileid: "43106636"
---
# <a name="create-a-teams-intranet-portal-app-from-a-sharepoint-online-site-or-page"></a><span data-ttu-id="887bf-103">Создание приложения "портал интрасети" для Рабочей группы на сайте SharePoint Online или на странице</span><span class="sxs-lookup"><span data-stu-id="887bf-103">Create a Teams 'Intranet Portal app' from a SharePoint Online site or page</span></span>

<span data-ttu-id="887bf-104">Выполните действия, описанные в этой статье, чтобы создать автономное и статическое приложение в Teams, которое ссылается на сайт интрасети для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="887bf-104">Use the steps in this article to create a standalone and static app inside of Teams that links to the intranet site for your org.</span></span>

<span data-ttu-id="887bf-105">Будет создано *личное приложение Teams* вашего сайта SharePoint, и оно появится как вкладка в Teams.</span><span class="sxs-lookup"><span data-stu-id="887bf-105">A *Teams Personal App* of your SharePoint intranet site is created, and will appear as a tab inside of Teams.</span></span> <span data-ttu-id="887bf-106">На этой вкладке могут содержаться сведения, важные для всех пользователей Teams.</span><span class="sxs-lookup"><span data-stu-id="887bf-106">This tab can contain information important to all your Teams users.</span></span> <span data-ttu-id="887bf-107">Это быстрый и удобный способ получить доступ к обновлениям только нажатием клавиши TAB для пользователей Teams.</span><span class="sxs-lookup"><span data-stu-id="887bf-107">It is a quick and convenient way for Teams users to access updates just a tab click away.</span></span>

<span data-ttu-id="887bf-108">Имейте в виду, что процесс, показанный для работы, **должен использовать** *современный* сайт или страницу SharePoint.</span><span class="sxs-lookup"><span data-stu-id="887bf-108">Be aware that the process shown **must use** a *modern* SharePoint site or page to work.</span></span> <span data-ttu-id="887bf-109">Этот процесс недоступен для *классических* сайтов и страниц.</span><span class="sxs-lookup"><span data-stu-id="887bf-109">This process is not available for *classical* sites or pages.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="887bf-110">Убедитесь в том, что для вашего клиента включена параллельная загрузка приложений Teams.</span><span class="sxs-lookup"><span data-stu-id="887bf-110">Make certain that side-loading of Teams apps is enabled for your tenant.</span></span> <span data-ttu-id="887bf-111">В зависимости от того, где находится миграция на портале администрирования Teams, вам может потребоваться включить ее в разделе администратор Teams > или в разделе Параметры администрирования > > службы и надстройки > Microsoft Teams > приложения > внешние приложения в предыдущей версии портала.</span><span class="sxs-lookup"><span data-stu-id="887bf-111">Depending on where you are in the migration process of the Teams Admin portal, you might need to enable it either under Teams > Admin, or under Admin > Settings > Services and Add-ins > Microsoft Teams > Apps > External Apps, in the previous version of the portal!</span></span> 

## <a name="use-app-studio-to-create-your-standalone-sharepoint-online-app"></a><span data-ttu-id="887bf-112">Создание автономного приложения SharePoint Online с помощью App Studio</span><span class="sxs-lookup"><span data-stu-id="887bf-112">Use App Studio to create your standalone SharePoint Online app</span></span>
<span data-ttu-id="887bf-113">' ' ' ' Перед тем как приступить к работе:</span><span class="sxs-lookup"><span data-stu-id="887bf-113">''' Before you begin:</span></span>
1. <span data-ttu-id="887bf-114">Вам необходимо знать URL-адрес SharePoint Online с современной связью или сайт группы или страницу.</span><span class="sxs-lookup"><span data-stu-id="887bf-114">You'll need to know the URL of a SharePoint Online modern Communication or Team site, or page.</span></span>
    - <span data-ttu-id="887bf-115">Эти сайты всегда будут содержать */Teams/* или */Sites/* в пути.</span><span class="sxs-lookup"><span data-stu-id="887bf-115">These sites will always have either */teams/* or */sites/* in their paths.</span></span>

2. <span data-ttu-id="887bf-116">Вам необходимо знать поддомен клиента, который будет использоваться в заполнителе **{{поддомен}}**.</span><span class="sxs-lookup"><span data-stu-id="887bf-116">You'll need to know your tenant's subdomain, which will be used in the placeholder **{{subdomain}}**.</span></span>

3. <span data-ttu-id="887bf-117">В этой статье будет использоваться заполнитель **{{siteUrl}}** — *URL-адрес* сайта или страницы, которую вы выбрали.</span><span class="sxs-lookup"><span data-stu-id="887bf-117">This article will use **{{siteUrl}}** placeholder for your the *URL* of the site or page you chose.</span></span>
    - <span data-ttu-id="887bf-118">Примеры *URL-адресов*: https://contoso.sharepoint.com/teams/Contoso *или*   https://contoso.sharepoint.com/sites/Contoso</span><span class="sxs-lookup"><span data-stu-id="887bf-118">Example *URLs*:   https://contoso.sharepoint.com/teams/Contoso   *or* https://contoso.sharepoint.com/sites/Contoso</span></span> 
4. <span data-ttu-id="887bf-119">Кроме того, **{{sitePath}}** будет использоваться для заметок URL *path* -адреса (например:/teams/Contoso).</span><span class="sxs-lookup"><span data-stu-id="887bf-119">Also, **{{sitePath}}** will be used to denote the *path* of the URL (ex: /teams/Contoso).</span></span>
    - <span data-ttu-id="887bf-120">Примеры *путей*:/teams/Contoso *или* /Sites/contoso</span><span class="sxs-lookup"><span data-stu-id="887bf-120">Example *paths*:   /teams/Contoso   *or* /sites/Contoso</span></span> 

<span data-ttu-id="887bf-121">Для начала выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="887bf-121">Begin by following the steps below:</span></span>

1. <span data-ttu-id="887bf-122">Перейдите в магазин Teams.</span><span class="sxs-lookup"><span data-stu-id="887bf-122">Go to the Teams Store.</span></span>

2. <span data-ttu-id="887bf-123">Установите или откройте приложение App Studio.</span><span class="sxs-lookup"><span data-stu-id="887bf-123">Install or open App Studio.</span></span>

3. <span data-ttu-id="887bf-124">Нажмите кнопку **Открыть**рядом с параметром приложение.</span><span class="sxs-lookup"><span data-stu-id="887bf-124">Click **Open**, next to the App option.</span></span>

4. <span data-ttu-id="887bf-125">В открытом приложении App Studio щелкните **редактор манифестов**.</span><span class="sxs-lookup"><span data-stu-id="887bf-125">With App Studio open, click on **Manifest Editor**.</span></span>

5. <span data-ttu-id="887bf-126">**Создайте новое приложение**.</span><span class="sxs-lookup"><span data-stu-id="887bf-126">**Create a new app**.</span></span>

6. <span data-ttu-id="887bf-127">Заполните все **сведения о приложении**.</span><span class="sxs-lookup"><span data-stu-id="887bf-127">Fill in all **App Details**.</span></span>

7. <span data-ttu-id="887bf-128">Щелкните **вкладки** в разделе "возможности".</span><span class="sxs-lookup"><span data-stu-id="887bf-128">Click on **Tabs** under Capabilities.</span></span>

8. <span data-ttu-id="887bf-129">Нажмите кнопку **Добавить** на вкладке Личные.</span><span class="sxs-lookup"><span data-stu-id="887bf-129">Click **Add** under Personal Tab.</span></span>

9. <span data-ttu-id="887bf-130">Введите **имя** и выберите **новый уникальный идентификатор сущности**.</span><span class="sxs-lookup"><span data-stu-id="887bf-130">Fill in the **Name** and choose **a new unique Entity ID**.</span></span>

10. <span data-ttu-id="887bf-131">Заполните **URL-адрес contentURL и веб-сайта**.</span><span class="sxs-lookup"><span data-stu-id="887bf-131">Fill in the **contentURL and Website URL**.</span></span> 

- <span data-ttu-id="887bf-132">**contentUrl**: {{siteUrl}}/_layouts/15/teamslogon.aspx? SPFX = true&dest = {{sitePath}}</span><span class="sxs-lookup"><span data-stu-id="887bf-132">**contentUrl**: {{siteUrl}}/_layouts/15/teamslogon.aspx?SPFX=true&dest={{sitePath}}</span></span>  
- <span data-ttu-id="887bf-133">**web'iteUrl**: {{siteUrl}} ' ' пример **contentURL**:https://contoso.sharepoint.com/sites/ContosoHub/_layouts/15/teamslogon.aspx?SPFX=true&dest=/sites/ContosoHub</span><span class="sxs-lookup"><span data-stu-id="887bf-133">**web'iteUrl**: {{siteUrl}} ''   Example **contentURL**: https://contoso.sharepoint.com/sites/ContosoHub/_layouts/15/teamslogon.aspx?SPFX=true&dest=/sites/ContosoHub</span></span> 

11. <span data-ttu-id="887bf-134">Перейдите в раздел **домены и Permissi'ns**.</span><span class="sxs-lookup"><span data-stu-id="887bf-134">Navigate to **Domains and Permissi'ns**.</span></span> <span data-ttu-id="887bf-135">Убедитесь, что в разделе Допустимые домены указаны доменные имена SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="887bf-135">Make sure the valid domains section contains your SharePoint online domain name.</span></span>
<span data-ttu-id="887bf-136">"Пример: contoso.sharepoint.com</span><span class="sxs-lookup"><span data-stu-id="887bf-136">'' Example: contoso.sharepoint.com</span></span>

12. <span data-ttu-id="887bf-137">Добавьте следующие свойства **единого входа для** веб-приложения: "пример: ' '" **идентификатор приложения AAD**: 00000003-0000-0ff1-ce00-000000000000 **Resource URL**: {{поддомен}}. SharePoint. com "" " ![веб-приложение единого входа, с идентификатором и URL-адресом.](media/personal-app.png)</span><span class="sxs-lookup"><span data-stu-id="887bf-137">Add the following web app **single sign-on** properties:  ''  Example:''''  **AAD application ID**: 00000003-0000-0ff1-ce00-000000000000  **Resource Url**: {{subdomain}}.sharepoint.com' '' ![Web app single sign-on, with ID and URL.](media/personal-app.png)</span></span>

13. <span data-ttu-id="887bf-138">**Сохраните** эти свойства, а затем перейдите к разделу **Проверка и распространение**.</span><span class="sxs-lookup"><span data-stu-id="887bf-138">**Save** these properties and then navigate to **Test and distribute**.</span></span> 

14. <span data-ttu-id="887bf-139">Установите приложение, чтобы протестировать приложение лично.</span><span class="sxs-lookup"><span data-stu-id="887bf-139">Install the app to test the application personally.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="887bf-140">Если вы не используете приложение Teams Studio, вам потребуется. zip манифест. JSON-файл, который вы только что создали, перейдите в магазин приложений в Teams и щелкните ссылку **Отправить настраиваемое приложение** (в правом нижнем углу магазина приложений).</span><span class="sxs-lookup"><span data-stu-id="887bf-140">If you aren't using Teams App Studio, you will have to .zip the manifest.JSON file you just created, navigate to the App Store in Teams, and click  **upload custom app** link (at the bottom right of the App Store).</span></span> <span data-ttu-id="887bf-141">Это сделает приложение доступным для вас.</span><span class="sxs-lookup"><span data-stu-id="887bf-141">This will make the app available to you.</span></span>

15. <span data-ttu-id="887bf-142">Теперь приложение доступно в виде статической вкладки для загрузки и просмотра в Teams.</span><span class="sxs-lookup"><span data-stu-id="887bf-142">Now the app is available as a static tab for you to load and view in Teams.</span></span>

## <a name="test-and-view-your-new-static-tab"></a><span data-ttu-id="887bf-143">Проверка и просмотр новой статической вкладки</span><span class="sxs-lookup"><span data-stu-id="887bf-143">Test and view your new static tab</span></span>

<span data-ttu-id="887bf-144">Чтобы открыть вкладку Создание на рабочем столе Teams, в левой части панели приложения перейдите на многоточие (**...**).</span><span class="sxs-lookup"><span data-stu-id="887bf-144">To view the new tab on the Teams desktop, navigate to the ellipses (**…**) in the left-hand side of your app bar.</span></span> <span data-ttu-id="887bf-145">Найдите новое приложение, загрузите его и протестируйте автономное приложение в Teams.</span><span class="sxs-lookup"><span data-stu-id="887bf-145">Find your new app, load it, and test your standalone application in Teams.</span></span>

<span data-ttu-id="887bf-146">Если вы хотите сделать новое приложение доступным в меню слева в более высоком положении, необходимо использовать параметр политики приложения для этого.</span><span class="sxs-lookup"><span data-stu-id="887bf-146">If you want to make the new app available in the left menu at a higher position, you must use an app policy setting for this.</span></span> <span data-ttu-id="887bf-147">Этот параметр можно найти в разделе администратор группы > политики приложений > добавить закрепленное приложение.</span><span class="sxs-lookup"><span data-stu-id="887bf-147">This setting can be found under the Team admin section > app policy > add a pinned application.</span></span> <span data-ttu-id="887bf-148">После назначения пользователю политики для тестирования это изменение будет отображаться на 24 часа позже.</span><span class="sxs-lookup"><span data-stu-id="887bf-148">When you assign the policy to a user for testing, the change will appear 24 hours later.</span></span> <span data-ttu-id="887bf-149">В этом случае необходимо решить, где должно отображаться приложение, чтобы избежать задержек.</span><span class="sxs-lookup"><span data-stu-id="887bf-149">With this in mind, please decide where the app should appear at your earliest convenience to help avoid delays.</span></span>

<span data-ttu-id="887bf-150">Чтобы просмотреть и протестировать новое приложение на мобильном устройстве, откройте денежный ящик приложения, нажав значок шеврона**^**() над панелью вкладок в нижней части экрана.</span><span class="sxs-lookup"><span data-stu-id="887bf-150">To view and test the new app on a mobile device, open the app drawer by tapping on the chevron (**^**) above the tab bar near the bottom of your screen.</span></span> <span data-ttu-id="887bf-151">Найдите свое приложение и перейдите на него на мобильном устройстве.</span><span class="sxs-lookup"><span data-stu-id="887bf-151">Find your app and navigate to it on your mobile device.</span></span>
        
> [!CAUTION]
> <span data-ttu-id="887bf-152">Поддержка мобильных устройств в настоящее время входит в предварительную версию для разработчиков.</span><span class="sxs-lookup"><span data-stu-id="887bf-152">Mobile support is currently in Developer Preview.</span></span> <span data-ttu-id="887bf-153">Чтобы включить предварительный просмотр для разработчика, перейдите к параметрам > о том, а затем включите режим предварительного просмотра разработчика.</span><span class="sxs-lookup"><span data-stu-id="887bf-153">To enable Developer Preview, navigate to Settings > About and then enable Developer Preview mode.</span></span>

## <a name="a-sample-manifestjson-file"></a><span data-ttu-id="887bf-154">Пример файла manifest. JSON</span><span class="sxs-lookup"><span data-stu-id="887bf-154">A Sample Manifest.JSON file</span></span>

<span data-ttu-id="887bf-155">Созданный вами файл JSO будет выглядеть примерно так, как показано на рисунке ниже.</span><span class="sxs-lookup"><span data-stu-id="887bf-155">The JSO        file you generate will look something like the one below.</span></span>

```JSON'
{ 

    "$schema": "https://developer.microsoft.com/en-us/json-schemas/teams/v1.5/MicrosoftTeams.schema.json", 

    "manifestVersion": "1.5", 

    "version": "1.0.0", 

    "id": "33ebded3-931c-4333-b0c5-b51dd8738873", 

    "packageName": "com.contoso.teams.devapp", 

    "developer": { 

        "name": "Contoso", ''

        "websiteUrl": "https://www.contoso.com", 

        "privacyUrl": "https://www.contoso.com/privacy", 

        "termsOfUseUrl": "https://www.contoso.com/terms" 

    }, 

    "icons": { 

        "color": "color.png", 

        "outline": "outline.png" 

    }, 

    "name": { 

        "short": "Contoso Intranet", '

        "full": "Intranet Portal for Contoso" 

    },                     
                        
    "des    ription": {                 

        "short": "Intranet portal for Contoso", 

        "full": "This app is to demonstrate the capabilities of hosting a SharePoint communication and team site as a standalone app in Teams" 

    }, 

    "accentColor": "#FFFFFF", 
''
    "staticTabs": [ 

        { 
                                       
                     "       nti        Id":       "com    unicat    onSi    eTab", 
                                       
            "name": "Contoso Net", 

            "contentUrl": "https://contoso.sharepoint.com/sites/ContosoNet/_layouts/15/teamslogon.aspx?SPFX=true&dest=/sites/ContosoNet/", 

            "websiteUrl": "https://contoso.sharepoint.com/sites/ContosoNet", 

            "scopes": [ 

                "personal" 

            ] 

        }, 

        { 

            "entityId": "teamSiteTab", 

            "name": "Team Contoso", 

            "contentUrl": "https://contoso.sharepoint.com/teams/TeamContoso/_layouts/15/teamslogon.aspx?SPFX=true&dest=/teams/TeamContoso/", 

            "websiteUrl": "https://contoso.sharepoint.com/teams/TeamContoso", 

            "scopes": [ 

                "personal" 

            ] 

        } 

    ], 

    "permissions": [ 

        "identity", 

        "messageTeamMembers" 

    ], 

    "validDomains": [ 

        "contoso.sharepoint.com" 

    ], 

    "webApplicationInfo": { 

        "id": "00000003-0000-0ff1-ce00-000000000000", 

        "resource": "https://contoso.sharepoint.com" 

    } 

}
```