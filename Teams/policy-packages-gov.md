---
title: Пакеты политики Teams для государственных организаций
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: aaglick
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
localization_priority: Normal
search.appverid: MET150
description: Сведения о том, как использовать и управлять пакетами политики Teams для вашей организации для государственных организаций.
ms.openlocfilehash: 738197a82303c1149ebc89a8e3ad7c6b37df90eb
ms.sourcegitcommit: bd13aecbb25c14e17d1b64343df6d80c90b2aa45
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2020
ms.locfileid: "46804043"
---
# <a name="teams-policy-packages-for-government"></a><span data-ttu-id="60466-103">Пакеты политики Teams для государственных организаций</span><span class="sxs-lookup"><span data-stu-id="60466-103">Teams policy packages for government</span></span>

> [!NOTE]
> <span data-ttu-id="60466-104">В настоящее время пакеты политик не поддерживаются в сетях Microsoft 365 для государственных организаций по высококачественной или невысокой развернутости.</span><span class="sxs-lookup"><span data-stu-id="60466-104">Policy packages are currently not available in Microsoft 365 Government GCC High or DoD deployments.</span></span>

## <a name="overview"></a><span data-ttu-id="60466-105">Обзор</span><span class="sxs-lookup"><span data-stu-id="60466-105">Overview</span></span>

<span data-ttu-id="60466-106">[Пакет политики](manage-policy-packages.md) в Microsoft Teams — это набор предопределенных политик и параметров политики, которые можно назначить пользователям, имеющим аналогичные роли в Организации.</span><span class="sxs-lookup"><span data-stu-id="60466-106">A [policy package](manage-policy-packages.md) in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="60466-107">Пакеты политик упрощают, оптимизируют и помогают обеспечивать согласованность при управлении политиками.</span><span class="sxs-lookup"><span data-stu-id="60466-107">Policy packages simplify, streamline, and help provide consistency when managing policies.</span></span> <span data-ttu-id="60466-108">Вы можете настроить параметры политик в пакете в соответствии с потребностями пользователей.</span><span class="sxs-lookup"><span data-stu-id="60466-108">You can customize the settings of the policies in the package to suit the needs of your users.</span></span> <span data-ttu-id="60466-109">При изменении параметров политик в пакете политики все пользователи, которым назначен этот пакет, получают обновленные параметры.</span><span class="sxs-lookup"><span data-stu-id="60466-109">When you change the settings of policies in a policy package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="60466-110">Управление пакетами политики осуществляется с помощью центра администрирования Microsoft Teams или оболочки PowerShell.</span><span class="sxs-lookup"><span data-stu-id="60466-110">You can manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

<span data-ttu-id="60466-111">Пакеты политик предварительно определяют следующие политики в зависимости от пакета:</span><span class="sxs-lookup"><span data-stu-id="60466-111">Policy packages pre-define policies for the following, depending on the package:</span></span>

- <span data-ttu-id="60466-112">Обмен сообщениями</span><span class="sxs-lookup"><span data-stu-id="60466-112">Messaging</span></span>
- <span data-ttu-id="60466-113">Собрания</span><span class="sxs-lookup"><span data-stu-id="60466-113">Meetings</span></span>
- <span data-ttu-id="60466-114">Звонки</span><span class="sxs-lookup"><span data-stu-id="60466-114">Calling</span></span>
- <span data-ttu-id="60466-115">Настройка приложения</span><span class="sxs-lookup"><span data-stu-id="60466-115">App setup</span></span>
- <span data-ttu-id="60466-116">Трансляции</span><span class="sxs-lookup"><span data-stu-id="60466-116">Live events</span></span>

<span data-ttu-id="60466-117">В настоящее время команды включают следующие пакеты политик для государственных организаций.</span><span class="sxs-lookup"><span data-stu-id="60466-117">Teams currently includes the following policy packages for government.</span></span>

|<span data-ttu-id="60466-118">Имя пакета в центре администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="60466-118">Package name in the Microsoft Teams admin center</span></span>|<span data-ttu-id="60466-119">Кому предназначено</span><span class="sxs-lookup"><span data-stu-id="60466-119">Best used for</span></span>|<span data-ttu-id="60466-120">Описание</span><span class="sxs-lookup"><span data-stu-id="60466-120">Description</span></span> |
|---------|---------|---------|
|<span data-ttu-id="60466-121">Открытый директор по безопасности</span><span class="sxs-lookup"><span data-stu-id="60466-121">Public safety officer</span></span>  |<span data-ttu-id="60466-122">Общедоступные руководителей по безопасности в вашей организации государственных учреждений</span><span class="sxs-lookup"><span data-stu-id="60466-122">Public safety officers in your government organization</span></span>  |<span data-ttu-id="60466-123">Создает набор политик и параметров политики, которые применяются для руководителей общедоступной безопасности в Организации.</span><span class="sxs-lookup"><span data-stu-id="60466-123">Creates a set of policies and policy settings that apply to public safety officers in your organization.</span></span> |
|<span data-ttu-id="60466-124">Менеджер Firstline</span><span class="sxs-lookup"><span data-stu-id="60466-124">Firstline manager</span></span>  |<span data-ttu-id="60466-125">Руководители Firstline в вашей организации правительственных учреждений</span><span class="sxs-lookup"><span data-stu-id="60466-125">Firstline Managers in your government organization</span></span> |<span data-ttu-id="60466-126">Создает набор политик и применяет эти параметры для руководителей Firstline в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="60466-126">Creates a set of policies and applies those settings to Firstline Managers in your organization.</span></span>|
|<span data-ttu-id="60466-127">Firstline рабочий процесс</span><span class="sxs-lookup"><span data-stu-id="60466-127">Firstline worker</span></span>  |<span data-ttu-id="60466-128">Firstline работников в вашей организации государственной власти</span><span class="sxs-lookup"><span data-stu-id="60466-128">Firstline Workers in your government organization</span></span> |<span data-ttu-id="60466-129">Создает набор политик и применяет эти параметры для Firstlineных сотрудников в Организации.</span><span class="sxs-lookup"><span data-stu-id="60466-129">Creates a set of policies and applies those settings to Firstline Workers in your organization.</span></span>|

![Снимок экрана: пакеты политики здравоохранения](media/policy-packages-gov.png)

<span data-ttu-id="60466-131">Каждой отдельной политике назначается имя пакета политики, что позволяет легко определять политики, связанные с пакетом политики.</span><span class="sxs-lookup"><span data-stu-id="60466-131">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span> <span data-ttu-id="60466-132">Например, при назначении общего пакета политики поддиректора безопасности для пользователей в Организации, для каждой политики в пакете создается политика с именем PublicSafety_Officer.</span><span class="sxs-lookup"><span data-stu-id="60466-132">For example, when you assign the Public safety officer policy package to users in your organization, a policy named PublicSafety_Officer is created for each policy in the package.</span></span>

![Снимок экрана: политики в Clinical рабочего пакета здравоохранения](media/policy-packages-public-safety-officer.png)

## <a name="manage-policy-packages"></a><span data-ttu-id="60466-134">Управление пакетами политик</span><span class="sxs-lookup"><span data-stu-id="60466-134">Manage policy packages</span></span>

### <a name="view"></a><span data-ttu-id="60466-135">Просмотр</span><span class="sxs-lookup"><span data-stu-id="60466-135">View</span></span>

<span data-ttu-id="60466-136">Перед назначением пакета просмотрите параметры каждой политики в пакете политики.</span><span class="sxs-lookup"><span data-stu-id="60466-136">View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="60466-137">В левой области навигации центра администрирования Microsoft Teams выберите **пакеты политики**, выберите имя пакета, а затем выберите имя политики.</span><span class="sxs-lookup"><span data-stu-id="60466-137">In the left navigation of the Microsoft Teams admin center, select **Policy packages**, select the package name, and then select the policy name.</span></span>

<span data-ttu-id="60466-138">Определите, являются ли предопределенные значения подходящими для вашей организации, или настройте их так, чтобы они были более строгими или Lenient в зависимости от потребностей Организации.</span><span class="sxs-lookup"><span data-stu-id="60466-138">Decide whether the predefined values are appropriate for your organization or whether you need to customize them to be more restrictive or lenient based on your organization's needs.</span></span>

### <a name="customize"></a><span data-ttu-id="60466-139">Настроить</span><span class="sxs-lookup"><span data-stu-id="60466-139">Customize</span></span>

<span data-ttu-id="60466-140">Настройте параметры политик в пакете политики в соответствии с потребностями Организации.</span><span class="sxs-lookup"><span data-stu-id="60466-140">Customize the settings of policies in the policy package, as needed, to fit the needs of your organization.</span></span> <span data-ttu-id="60466-141">Любые изменения, внесенные в параметры политики, автоматически применяются к пользователям, которым назначен пакет.</span><span class="sxs-lookup"><span data-stu-id="60466-141">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span> <span data-ttu-id="60466-142">Чтобы изменить параметры политики в пакете политики, в центре администрирования Microsoft Teams выберите пакет политики, выберите имя политики, которую вы хотите изменить, и нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="60466-142">To edit the settings of a policy in a policy package, in the Microsoft Teams admin center, select the policy package, select the name of the policy you want to edit, and then select **Edit**.</span></span>

<span data-ttu-id="60466-143">Имейте в виду, что вы также можете изменить параметры политик в пакете после назначения пакета политики.</span><span class="sxs-lookup"><span data-stu-id="60466-143">Keep in mind that you can also change the settings of policies in a package after you assign the policy package.</span></span> <span data-ttu-id="60466-144">Дополнительные сведения можно найти [в разделе Настройка политик в пакете политики](manage-policy-packages.md#customize-policies-in-a-policy-package).</span><span class="sxs-lookup"><span data-stu-id="60466-144">To learn more, see [Customize policies in a policy package](manage-policy-packages.md#customize-policies-in-a-policy-package).</span></span> 

### <a name="assign"></a><span data-ttu-id="60466-145">Присваивают</span><span class="sxs-lookup"><span data-stu-id="60466-145">Assign</span></span>

<span data-ttu-id="60466-146">Назначение пакета политики пользователям.</span><span class="sxs-lookup"><span data-stu-id="60466-146">Assign the policy package to users.</span></span> <span data-ttu-id="60466-147">Чтобы назначить пакет политики для одного или нескольких пользователей, нажмите кнопку **Управление пользователями**.</span><span class="sxs-lookup"><span data-stu-id="60466-147">To assign a policy package to one or multiple users, click **Manage users**.</span></span> <span data-ttu-id="60466-148">Вы также можете [использовать PowerShell](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) для назначения пакета политики большим пакетам пользователей.</span><span class="sxs-lookup"><span data-stu-id="60466-148">You can also [use PowerShell](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) to assign a policy package to large batches of users.</span></span> 

<span data-ttu-id="60466-149">Инструкции по назначению пакета политики с помощью центра администрирования Microsoft Teams или оболочки PowerShell приведены в статье [Назначение пакета политики](manage-policy-packages.md#assign-a-policy-package).</span><span class="sxs-lookup"><span data-stu-id="60466-149">For steps on how to assign a policy package using the Microsoft Teams admin center or PowerShell, see [Assign a policy package](manage-policy-packages.md#assign-a-policy-package).</span></span>

![Снимок экрана: назначение пакета политики в центре администрирования](media/policy-packages-gov-assign.png)

<span data-ttu-id="60466-151">Если пользователю назначена политика, а затем в дальнейшем вы назначаете другую политику, она имеет приоритет.</span><span class="sxs-lookup"><span data-stu-id="60466-151">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

## <a name="related-topics"></a><span data-ttu-id="60466-152">См. также</span><span class="sxs-lookup"><span data-stu-id="60466-152">Related topics</span></span>

[<span data-ttu-id="60466-153">Управление пакетами политик в Teams</span><span class="sxs-lookup"><span data-stu-id="60466-153">Manage policy packages in Teams</span></span>](manage-policy-packages.md)

[<span data-ttu-id="60466-154">Назначение политик пользователям в Teams</span><span class="sxs-lookup"><span data-stu-id="60466-154">Assign policies to your users in Teams</span></span>](assign-policies.md) 