---
title: Управление пользовательскими приложениями в Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: joglocke
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
description: В этой статье рассказывается о том, как создавать приложения, созданные в приложении Teams, в среде развертывания.
ms.openlocfilehash: a2896a2aa2b2d9750afd147b113a76637514afb6
ms.sourcegitcommit: b5c747e2daad6dd3c1d91f4e61ae6f26db5c77f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2020
ms.locfileid: "44064534"
---
# <a name="manage-your-custom-apps-in-microsoft-teams"></a><span data-ttu-id="987e8-103">Управление пользовательскими приложениями в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="987e8-103">Manage your custom apps in Microsoft Teams</span></span>

<span data-ttu-id="987e8-104">В этой статье приведены исчерпывающие инструкции по развертыванию приложения Teams на этапе развертывания.</span><span class="sxs-lookup"><span data-stu-id="987e8-104">This article provides end-to-end guidance for how to take your Teams app from development to deployment.</span></span> <span data-ttu-id="987e8-105">Это руководство сосредоточено на аспектах приложения Teams и предназначено для ИТ-специалистов.</span><span class="sxs-lookup"><span data-stu-id="987e8-105">This guidance focuses on the Teams aspects of the app and is intended for IT pros.</span></span> <span data-ttu-id="987e8-106">Дополнительные сведения о разработке приложений Teams можно найти <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">здесь</a>.</span><span class="sxs-lookup"><span data-stu-id="987e8-106">For more information on developing Teams apps, see <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">here</a>.</span></span>

![Общие сведения о приложении в среде разработки для развертывания](media/manage-your-lob-apps.png)

## <a name="getting-started"></a><span data-ttu-id="987e8-108">Начало работы</span><span class="sxs-lookup"><span data-stu-id="987e8-108">Getting started</span></span>

<span data-ttu-id="987e8-109">Для создания и управления пользовательскими приложениями в Teams вам понадобятся два клиента: тестовый клиент для разработки и производственный клиент.</span><span class="sxs-lookup"><span data-stu-id="987e8-109">To create and manage custom apps in Teams, you'll need two tenants: a test tenant for development and a production tenant.</span></span>

> [!NOTE]
> <span data-ttu-id="987e8-110">Если у вас еще нет тестового клиента, вы можете быстро создать его и заполнить данными теста с помощью программы разработчика Office 365.</span><span class="sxs-lookup"><span data-stu-id="987e8-110">If you don't already have a test tenant, you can quickly create one and populate it with test data using the Office 365 Developer Program.</span></span> <span data-ttu-id="987e8-111">Дополнительные <a href="https://developer.microsoft.com/office/dev-program" target="_blank">сведения</a></span><span class="sxs-lookup"><span data-stu-id="987e8-111"><a href="https://developer.microsoft.com/office/dev-program" target="_blank">Learn more here</a>.</span></span>

## <a name="step-1-develop-and-test"></a><span data-ttu-id="987e8-112">Этап 1: Разработка и тестирование</span><span class="sxs-lookup"><span data-stu-id="987e8-112">Step 1: Develop and test</span></span>

### <a name="create-test-users"></a><span data-ttu-id="987e8-113">Создание тестовых пользователей</span><span class="sxs-lookup"><span data-stu-id="987e8-113">Create test users</span></span>

<span data-ttu-id="987e8-114">Убедитесь в том, что у ваших разработчиков есть учетные записи в тестовом клиенте.</span><span class="sxs-lookup"><span data-stu-id="987e8-114">Make sure that your developers, whether in-house or external, have accounts in your test tenant.</span></span> <span data-ttu-id="987e8-115">Дополнительные <a href="https://docs.microsoft.com/office365/admin/add-users/add-users" target="_blank">сведения о добавлении пользователей</a>.</span><span class="sxs-lookup"><span data-stu-id="987e8-115"><a href="https://docs.microsoft.com/office365/admin/add-users/add-users" target="_blank">Learn more about adding users</a>.</span></span>

### <a name="allow-custom-apps-in-the-test-tenant"></a><span data-ttu-id="987e8-116">Разрешить пользовательские приложения в тестовом клиенте</span><span class="sxs-lookup"><span data-stu-id="987e8-116">Allow custom apps in the test tenant</span></span>

<span data-ttu-id="987e8-117">Чтобы предоставить разработчикам доступ, необходимый для тестирования, разрешите всем пользователям в тестовом клиенте загрузить пользовательские приложения (также известные как неопубликованные).</span><span class="sxs-lookup"><span data-stu-id="987e8-117">To give developers the access they need for testing, allow all users in the test tenant to upload custom apps (also known as sideloading).</span></span> <span data-ttu-id="987e8-118">Это позволяет разработчикам загрузить пользовательское приложение, которое будет использоваться отдельно или в тестовом клиенте, не отправляя приложение в магазин приложений Teams.</span><span class="sxs-lookup"><span data-stu-id="987e8-118">This lets developers upload a custom app to be used personally or across the test tenant without having to submit the app to the Teams apps store.</span></span> <span data-ttu-id="987e8-119">Загрузка настраиваемого приложения позволяет разработчикам тестировать приложение до более широкого распространения.</span><span class="sxs-lookup"><span data-stu-id="987e8-119">Uploading a custom app lets developers test an app before you distribute it more widely.</span></span>

<span data-ttu-id="987e8-120">Чтобы разрешить пользователям отправлять пользовательские приложения, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="987e8-120">To allow users to upload custom apps, follow these steps:</span></span>

1. <span data-ttu-id="987e8-121">Включите параметр **Разрешить взаимодействие с пользовательскими приложениями** в масштабе приложения.</span><span class="sxs-lookup"><span data-stu-id="987e8-121">Turn on the **Allow interaction with custom apps** org-wide app setting.</span></span> <span data-ttu-id="987e8-122">Для этого выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="987e8-122">To do this:</span></span>
    1. <span data-ttu-id="987e8-123">В левой области навигации <a href="https://admin.teams.microsoft.com/" target="_blank">центра администрирования Microsoft Teams</a>перейдите в > раздел **приложения Teams\*\*\*\*Управление приложениями**, а затем выберите **Параметры приложения для всей Организации**.</span><span class="sxs-lookup"><span data-stu-id="987e8-123">In the left navigation of the <a href="https://admin.teams.microsoft.com/" target="_blank">Microsoft Teams admin center</a>, go to **Teams apps** > **Manage apps**, and then click **Org-wide app settings**.</span></span>
    2. <span data-ttu-id="987e8-124">В разделе **пользовательские приложения**включите **параметр Разрешить взаимодействие с пользовательскими приложениями**и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="987e8-124">Under **Custom apps**, turn on **Allow interaction with custom apps**, and then click **Save**.</span></span>

    ![Снимок экрана: параметр "Разрешить взаимодействие с пользовательскими приложениями" в масштабе приложения](media/manage-your-lob-apps-org-wide-custom-apps.png)

2. <span data-ttu-id="987e8-126">Включите параметр " **отправлять пользовательские приложения** " в политике настройки глобального приложения.</span><span class="sxs-lookup"><span data-stu-id="987e8-126">Turn on the **Upload custom apps** setting in the global app setup policy.</span></span> <span data-ttu-id="987e8-127">Для этого выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="987e8-127">To do this:</span></span>
    1. <span data-ttu-id="987e8-128">В левой области навигации <a href="https://admin.teams.microsoft.com/" target="_blank">центра администрирования Microsoft Teams</a>перейдите в раздел > **политики настройки** **приложений группы**, а затем выберите **глобальную политику (по умолчанию на уровне Организации)** .</span><span class="sxs-lookup"><span data-stu-id="987e8-128">In the left navigation of the <a href="https://admin.teams.microsoft.com/" target="_blank">Microsoft Teams admin center</a>, go to **Teams apps** > **Setup policies**, and then click the **Global (Org-wide default)** policy.</span></span>
    2. <span data-ttu-id="987e8-129">Включите команду **отправить пользовательские приложения**и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="987e8-129">Turn on **Upload custom apps**, and then click **Save**.</span></span>

    ![Снимок экрана: параметр политики настройки приложения "передача настраиваемых приложений"](media/manage-your-lob-apps-app-setup-custom-apps.png)

> [!NOTE]
> <span data-ttu-id="987e8-131">На уровне группы также есть параметр "Отправить настраиваемое приложение".</span><span class="sxs-lookup"><span data-stu-id="987e8-131">There's also an upload custom app setting at the team level.</span></span> <span data-ttu-id="987e8-132">По умолчанию этот параметр включен.</span><span class="sxs-lookup"><span data-stu-id="987e8-132">By default this setting is on.</span></span> <span data-ttu-id="987e8-133">Тем не менее, если разработчикам не удается отправить собственное приложение команде, проверьте этот параметр, выполнив <a href="https://docs.microsoft.com/microsoftteams/teams-custom-app-policies-and-settings#configure-the-team-custom-app-setting" target="_blank">указанные ниже действия.</a></span><span class="sxs-lookup"><span data-stu-id="987e8-133">However, if developers are unable to upload a custom app to a team, check the setting by following the steps <a href="https://docs.microsoft.com/microsoftteams/teams-custom-app-policies-and-settings#configure-the-team-custom-app-setting" target="_blank">here</a>.</span></span>

### <a name="create-your-app"></a><span data-ttu-id="987e8-134">Создание приложения</span><span class="sxs-lookup"><span data-stu-id="987e8-134">Create your app</span></span>

<span data-ttu-id="987e8-135">Теперь разработчики должны иметь необходимые вам возможности для создания приложения.</span><span class="sxs-lookup"><span data-stu-id="987e8-135">Developers should now have what they need to create your app.</span></span> <span data-ttu-id="987e8-136">В этой <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">статье</a> вы найдете рекомендации.</span><span class="sxs-lookup"><span data-stu-id="987e8-136">See <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">here</a> for guidance on that.</span></span>

## <a name="step-2-validate-in-production"></a><span data-ttu-id="987e8-137">Шаг 2: проверка в производстве</span><span class="sxs-lookup"><span data-stu-id="987e8-137">Step 2: Validate in production</span></span>

### <a name="get-the-app-package"></a><span data-ttu-id="987e8-138">Получение пакета приложения</span><span class="sxs-lookup"><span data-stu-id="987e8-138">Get the app package</span></span>

<span data-ttu-id="987e8-139">Когда приложение будет готово к использованию в производстве, разработчик должен создать пакет приложения.</span><span class="sxs-lookup"><span data-stu-id="987e8-139">When the app is ready for use in production, the developer should produce an app package.</span></span> <span data-ttu-id="987e8-140">Для этого они могут использовать <a href="https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio" target="_blank">Приложение App Studio</a> .</span><span class="sxs-lookup"><span data-stu-id="987e8-140">They can use <a href="https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio" target="_blank">App Studio</a> for that.</span></span> <span data-ttu-id="987e8-141">Файлы будут отправлены в формате ZIP.</span><span class="sxs-lookup"><span data-stu-id="987e8-141">They'll send you the file in .zip format.</span></span>

<span data-ttu-id="987e8-142">Корпорация Майкрософт использует <a href="https://docs.microsoft.com/microsoftteams/platform/publishing/office-store-approval" target="_blank">эти рекомендации</a> для обеспечения соответствия приложений стандартам качества и безопасности в магазине глобальных приложений Teams.</span><span class="sxs-lookup"><span data-stu-id="987e8-142">Microsoft uses <a href="https://docs.microsoft.com/microsoftteams/platform/publishing/office-store-approval" target="_blank">these guidelines</a> to ensure apps comply with the quality and security standards of the global Teams apps store.</span></span>

### <a name="allow-trusted-users-to-upload-custom-apps-in-the-production-tenant"></a><span data-ttu-id="987e8-143">Разрешение доверенных пользователей отправлять пользовательские приложения в производственный клиент</span><span class="sxs-lookup"><span data-stu-id="987e8-143">Allow trusted users to upload custom apps in the production tenant</span></span>

<span data-ttu-id="987e8-144">Чтобы проверить, правильно ли приложение работает в вашем производственном клиенте, необходимо разрешить себе и/или надежным пользователям в Организации загрузить пользовательские приложения.</span><span class="sxs-lookup"><span data-stu-id="987e8-144">To validate that the app is working correctly in your production tenant, you need to allow yourself and/or trusted users in your organization to upload custom apps.</span></span>  <span data-ttu-id="987e8-145">Как и на предыдущем <a href="https://docs.microsoft.com/microsoftteams/manage-your-lob-apps#allow-custom-apps-in-the-test-tenant" target="_blank">этапе</a>, для этого используются политики настройки приложений.</span><span class="sxs-lookup"><span data-stu-id="987e8-145">Much like in the earlier <a href="https://docs.microsoft.com/microsoftteams/manage-your-lob-apps#allow-custom-apps-in-the-test-tenant" target="_blank">step</a>, you use app setup policies to do this.</span></span>

> [!NOTE]
> <span data-ttu-id="987e8-146">Если вы не можете загрузить приложение в производственный клиент для проверки, даже для себя и для доверенных пользователей, можно пропустить этот шаг и выполнить действия 3 и 4, чтобы загрузить непроверенное приложение в магазин приложений клиента.</span><span class="sxs-lookup"><span data-stu-id="987e8-146">If you're uncomfortable with uploading the app to your production tenant for validation, even for yourself or trusted users, you can skip this step and follow steps 3 and 4 to upload the unvalidated app to your tenant app store.</span></span> <span data-ttu-id="987e8-147">Затем Ограничьте доступ к этому приложению только себе и надежным пользователям.</span><span class="sxs-lookup"><span data-stu-id="987e8-147">Then, restrict access to that app to only yourself and users you trust.</span></span> <span data-ttu-id="987e8-148">Эти пользователи могут затем получить приложение из магазина приложений клиента для выполнения проверки.</span><span class="sxs-lookup"><span data-stu-id="987e8-148">These users can then get the app from the tenant app store to perform validation.</span></span> <span data-ttu-id="987e8-149">После проверки приложения используйте те же политики разрешений, чтобы открыть Access и извлечь приложение для использования на рабочем месте.</span><span class="sxs-lookup"><span data-stu-id="987e8-149">After the app is validated, use the same permission policies to open access and roll the app out for production use.</span></span>

<span data-ttu-id="987e8-150">Чтобы разрешить надежным пользователям загружать пользовательские приложения, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="987e8-150">To allow trusted users to upload custom apps, follow these steps:</span></span>

1. <span data-ttu-id="987e8-151">Включите параметр **Разрешить взаимодействие с пользовательскими приложениями** в масштабе приложения.</span><span class="sxs-lookup"><span data-stu-id="987e8-151">Turn on the **Allow interaction with custom apps** org-wide app setting.</span></span> <span data-ttu-id="987e8-152">Для этого выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="987e8-152">To do this:</span></span>
    1. <span data-ttu-id="987e8-153">В левой области навигации <a href="https://admin.teams.microsoft.com/" target="_blank">центра администрирования Microsoft Teams</a>перейдите в > раздел **приложения Teams\*\*\*\*Управление приложениями**, а затем выберите **Параметры приложения для всей Организации**.</span><span class="sxs-lookup"><span data-stu-id="987e8-153">In the left navigation of the <a href="https://admin.teams.microsoft.com/" target="_blank">Microsoft Teams admin center</a>, go to **Teams apps** > **Manage apps**, and then click **Org-wide app settings**.</span></span>
    2. <span data-ttu-id="987e8-154">В разделе **пользовательские приложения**включите **параметр Разрешить взаимодействие с пользовательскими приложениями**и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="987e8-154">Under **Custom apps**, turn on **Allow interaction with custom apps**, and then click **Save**.</span></span>
2. <span data-ttu-id="987e8-155">Отключите параметр " **отправлять пользовательские приложения** " в политике настройки глобального приложения.</span><span class="sxs-lookup"><span data-stu-id="987e8-155">Turn off the **Upload custom apps** setting in the global app setup policy.</span></span> <span data-ttu-id="987e8-156">Для этого выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="987e8-156">To do this:</span></span>
    1. <span data-ttu-id="987e8-157">В левой области навигации <a href="https://admin.teams.microsoft.com/" target="_blank">центра администрирования Microsoft Teams</a>перейдите в раздел > **политики настройки** **приложений группы**, а затем выберите **глобальную политику (по умолчанию на уровне Организации)** .</span><span class="sxs-lookup"><span data-stu-id="987e8-157">In the left navigation of the <a href="https://admin.teams.microsoft.com/" target="_blank">Microsoft Teams admin center</a>, go to **Teams apps** > **Setup policies**, and then click the **Global (Org-wide default)** policy.</span></span>
    2. <span data-ttu-id="987e8-158">Отключите функцию " **отправить пользовательские приложения**" и нажмите кнопку " **сохранить**".</span><span class="sxs-lookup"><span data-stu-id="987e8-158">Turn off **Upload custom apps**, and then click **Save**.</span></span>
3. <span data-ttu-id="987e8-159">Создайте новую политику настройки приложения, которая позволяет отправлять пользовательские приложения и назначать их набору доверенных пользователей.</span><span class="sxs-lookup"><span data-stu-id="987e8-159">Create a new app setup policy that allows uploading custom apps and assign it to your set of trusted users.</span></span> <span data-ttu-id="987e8-160">Для этого выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="987e8-160">To do this:</span></span>
    1. <span data-ttu-id="987e8-161">В левой области навигации <a href="https://admin.teams.microsoft.com/" target="_blank">центра администрирования Microsoft Teams</a>перейдите в раздел > **политики настройки** **приложений группы**, а затем нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="987e8-161">In the left navigation of the <a href="https://admin.teams.microsoft.com/" target="_blank">Microsoft Teams admin center</a>, go to **Teams apps** > **Setup policies**, and then click the **Add**.</span></span> <span data-ttu-id="987e8-162">Присвойте новой политике имя и описание, включите команду **отправить пользовательские приложения**, а затем нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="987e8-162">Give the new policy a name and description, turn on **Upload custom apps**, and then click **Save**.</span></span>
    2. <span data-ttu-id="987e8-163">Выберите созданную политику и нажмите кнопку **Управление пользователями**.</span><span class="sxs-lookup"><span data-stu-id="987e8-163">Select the new policy you created, and then click **Manage users**.</span></span> <span data-ttu-id="987e8-164">Найдите пользователя, нажмите кнопку **Добавить**, а затем — **Применить**.</span><span class="sxs-lookup"><span data-stu-id="987e8-164">Search for a user, click **Add**, and then click **Apply**.</span></span> <span data-ttu-id="987e8-165">Повторите этот шаг, чтобы назначить политику всем доверенным пользователям.</span><span class="sxs-lookup"><span data-stu-id="987e8-165">Repeat this step to assign the policy to all your trusted users.</span></span>

        ![Снимок экрана: страница "Добавление политики настройки приложений"](media/manage-your-lob-apps-new-app-setup-policy.png)

    <span data-ttu-id="987e8-167">Теперь пользователи могут добавить манифест приложения, чтобы проверить, правильно ли приложение работает в производственном клиенте.</span><span class="sxs-lookup"><span data-stu-id="987e8-167">These users can now upload the app manifest to validate that the app is working correctly in the production tenant.</span></span>

## <a name="step-3-upload-to-the-tenant-app-catalog"></a><span data-ttu-id="987e8-168">Шаг 3: Отправка в каталог приложений клиента</span><span class="sxs-lookup"><span data-stu-id="987e8-168">Step 3: Upload to the tenant app catalog</span></span>

<span data-ttu-id="987e8-169">Чтобы сделать приложение доступным для пользователей в магазине App Store, загрузите приложение.</span><span class="sxs-lookup"><span data-stu-id="987e8-169">To make the app available to users in the tenant app store, upload the app.</span></span> <span data-ttu-id="987e8-170">Это можно сделать на странице [Управление приложениями](manage-apps.md) в центре администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="987e8-170">You can do this on the [Manage apps](manage-apps.md) page of the Microsoft Teams admin center.</span></span>

![Снимок экрана: страница "Управление приложениями" в центре администрирования](media/manage-your-lob-apps-upload-new-app.png)

## <a name="step-4-configure-and-assign-permissions"></a><span data-ttu-id="987e8-172">Действие 4: Настройка и назначение разрешений</span><span class="sxs-lookup"><span data-stu-id="987e8-172">Step 4: Configure and assign permissions</span></span>

### <a name="control-access-to-the-app"></a><span data-ttu-id="987e8-173">Управление доступом к приложению</span><span class="sxs-lookup"><span data-stu-id="987e8-173">Control access to the app</span></span>

<span data-ttu-id="987e8-174">По умолчанию все пользователи имеют доступ к этому приложению в магазине "приложения Teams".</span><span class="sxs-lookup"><span data-stu-id="987e8-174">By default, all users have access to this app in the the Teams apps store.</span></span> <span data-ttu-id="987e8-175">Чтобы ограничить круг лиц, имеющих разрешение на использование приложения, и управлять им, вы можете создать и назначить новую политику разрешений для приложений.</span><span class="sxs-lookup"><span data-stu-id="987e8-175">To restrict and control who has permission to use the app, you can create and assign a new app permission policy.</span></span> <span data-ttu-id="987e8-176">Выполните действия, описанные в <a href="https://docs.microsoft.com/microsoftteams/teams-app-permission-policies#create-a-custom-app-permission-policy" target="_blank">этой статье</a>.</span><span class="sxs-lookup"><span data-stu-id="987e8-176">Follow the steps <a href="https://docs.microsoft.com/microsoftteams/teams-app-permission-policies#create-a-custom-app-permission-policy" target="_blank">here</a>.</span></span>

![Снимок экрана: страница "Добавление политики разрешений приложений"](media/manage-your-lob-apps-new-app-permission-policy.png)

### <a name="pin-the-app-for-users-to-discover"></a><span data-ttu-id="987e8-178">Закрепление приложения для пользователей для выяснения</span><span class="sxs-lookup"><span data-stu-id="987e8-178">Pin the app for users to discover</span></span>

<span data-ttu-id="987e8-179">По умолчанию, чтобы пользователи могли найти это приложение, они должны будут перейти в магазин приложений Teams и просмотреть или найти.</span><span class="sxs-lookup"><span data-stu-id="987e8-179">By default, for users to find this app they would have to go to Teams apps store and browse or search for it.</span></span> <span data-ttu-id="987e8-180">Чтобы пользователи могли легко получить доступ к приложению, вы можете закрепить приложение на панели приложения в Teams.</span><span class="sxs-lookup"><span data-stu-id="987e8-180">To make it easy for users to get to the app, you can pin the app to the app bar in Teams.</span></span> <span data-ttu-id="987e8-181">Для этого создайте новую политику настройки приложения и назначьте ее пользователям.</span><span class="sxs-lookup"><span data-stu-id="987e8-181">To do this, create a new app setup policy and assign it to users.</span></span> <span data-ttu-id="987e8-182">Выполните действия, описанные в <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies#create-a-custom-app-setup-policy" target="_blank">этой статье</a>.</span><span class="sxs-lookup"><span data-stu-id="987e8-182">Follow the steps  <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies#create-a-custom-app-setup-policy" target="_blank">here</a>.</span></span>

![Снимок экрана: область "Добавление закрепленных приложений"](media/manage-your-lob-apps-pinned-apps.png)

## <a name="step-5-update-the-app"></a><span data-ttu-id="987e8-184">Шаг 5: обновление приложения</span><span class="sxs-lookup"><span data-stu-id="987e8-184">Step 5: Update the app</span></span>

![Общие сведения о приложении в среде разработки для развертывания](media/manage-your-lob-apps-update.png)

<span data-ttu-id="987e8-186">Чтобы обновить приложение, разработчики должны перейти к [этапу 1](#step-1-develop-and-test) и [действию 2](#step-2-validate-in-production).</span><span class="sxs-lookup"><span data-stu-id="987e8-186">To update an app, developers should continue to follow [step 1](#step-1-develop-and-test) and [step 2](#step-2-validate-in-production).</span></span>

<span data-ttu-id="987e8-187">Вы можете обновить приложение с помощью каталога приложений клиента.</span><span class="sxs-lookup"><span data-stu-id="987e8-187">You can update the app through the tenant app catalog.</span></span> <span data-ttu-id="987e8-188">Для этого в центре администрирования Microsoft Teams перейдите в раздел программы для**управления приложениями** **Teams** > .</span><span class="sxs-lookup"><span data-stu-id="987e8-188">To do this, in the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span> <span data-ttu-id="987e8-189">В списке приложений выберите имя приложения, а затем нажмите кнопку **Обновить**.</span><span class="sxs-lookup"><span data-stu-id="987e8-189">In the list of apps, click the app name, and then click **Update**.</span></span> <span data-ttu-id="987e8-190">Это зазаменяет существующее приложение в каталоге приложений клиента, а все политики разрешений приложений и политики настройки приложений остаются принудительно примененными для обновленного приложения.</span><span class="sxs-lookup"><span data-stu-id="987e8-190">Doing this replaces the existing app in the tenant app catalog, and all app permission policies and app setup policies remain enforced for the updated app.</span></span>

### <a name="end-user-update-experience"></a><span data-ttu-id="987e8-191">Процесс обновления конечных пользователей</span><span class="sxs-lookup"><span data-stu-id="987e8-191">End user update experience</span></span>

<span data-ttu-id="987e8-192">В большинстве случаев после завершения обновления для конечных пользователей будет автоматически отображаться новая версия приложения.</span><span class="sxs-lookup"><span data-stu-id="987e8-192">In most cases, after you complete an app update the new version will automatically appear for end users.</span></span> <span data-ttu-id="987e8-193">Тем не менее, в <a href="https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Манифест Microsoft Teams</a> , для которого требуется принять пользователя, существуют некоторые обновления.</span><span class="sxs-lookup"><span data-stu-id="987e8-193">However, there are some updates to the <a href="https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Microsoft Teams manifest</a> that require user acceptance to complete:</span></span>

* <span data-ttu-id="987e8-194">Добавление или удаление Bot</span><span class="sxs-lookup"><span data-stu-id="987e8-194">A bot was added or removed</span></span>
* <span data-ttu-id="987e8-195">Изменилось свойство "botId" существующей ленты.</span><span class="sxs-lookup"><span data-stu-id="987e8-195">An existing bot's "botId" property changed</span></span>
* <span data-ttu-id="987e8-196">Изменилось свойство "isNotificationOnly" существующей ленты.</span><span class="sxs-lookup"><span data-stu-id="987e8-196">An existing bot's "isNotificationOnly" property changed</span></span>
* <span data-ttu-id="987e8-197">Изменилось свойство "supportsFiles" на Bot</span><span class="sxs-lookup"><span data-stu-id="987e8-197">The bot's "supportsFiles" property changed</span></span>
* <span data-ttu-id="987e8-198">Добавлено или удалено расширение сообщения</span><span class="sxs-lookup"><span data-stu-id="987e8-198">A Messaging extension was added or removed</span></span>
* <span data-ttu-id="987e8-199">Добавлена Новая соединительная линия</span><span class="sxs-lookup"><span data-stu-id="987e8-199">A new connector was added</span></span>
* <span data-ttu-id="987e8-200">Добавлена новая статическая вкладка</span><span class="sxs-lookup"><span data-stu-id="987e8-200">A new static tab was added</span></span>
* <span data-ttu-id="987e8-201">Добавлена новая настраиваемая вкладка</span><span class="sxs-lookup"><span data-stu-id="987e8-201">A new configurable tab was added</span></span>
* <span data-ttu-id="987e8-202">Изменились свойства в "webApplicationInfo"</span><span class="sxs-lookup"><span data-stu-id="987e8-202">Properties inside "webApplicationInfo" changed</span></span>

![Снимок экрана: список приложений, в котором показаны приложения, для которых доступна новая версия](media/manage-your-custom-apps-update1.png)

![Снимок экрана: параметр обновления для приложения](media/manage-your-custom-apps-update2.png)

## <a name="related-apps"></a><span data-ttu-id="987e8-205">Связанные приложения</span><span class="sxs-lookup"><span data-stu-id="987e8-205">Related apps</span></span>

- [<span data-ttu-id="987e8-206">Управление приложениями в центре администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="987e8-206">Manage your apps in the Microsoft Teams admin center</span></span>](manage-apps.md)