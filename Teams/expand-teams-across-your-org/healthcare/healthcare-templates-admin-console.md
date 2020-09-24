---
title: Использование шаблонов здравоохранения в Teams на консоли администрирования
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Используйте шаблоны Microsoft Teams в консоли администрирования, чтобы быстро и легко создавать группы, предоставляя готовый шаблон параметров, каналов и приложений.
ms.custom: seo-marvel-mar2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 93de98eb61f503467f7b9de218a10982402eeb41
ms.sourcegitcommit: af9f96010460f9323db84912fe143aa0750ac798
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/21/2020
ms.locfileid: "48171093"
---
# <a name="use-teams-healthcare-templates-in-the-admin-console"></a><span data-ttu-id="a563c-103">Использование шаблонов здравоохранения в Teams на консоли администрирования</span><span class="sxs-lookup"><span data-stu-id="a563c-103">Use Teams healthcare templates in the admin console</span></span>

[!INCLUDE [template](../../includes/preview-feature.md)]

<span data-ttu-id="a563c-104">Шаблоны Microsoft Teams позволяют быстро и легко создавать группы, предоставляя готовый шаблон параметров, каналов и предустановленных приложений.</span><span class="sxs-lookup"><span data-stu-id="a563c-104">Microsoft Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="a563c-105">Для организаций здравоохранения шаблоны могут быть особенно мощными, так как они предоставляют структуру для пользователей, с помощью которых лучше эффективно использовать команды.</span><span class="sxs-lookup"><span data-stu-id="a563c-105">For healthcare organizations, templates can be especially powerful, as they provide structure for users to become oriented with how to best leverage Teams effectively.</span></span> <span data-ttu-id="a563c-106">Шаблоны также позволяют администраторам развертывать единообразные команды для разных организаций.</span><span class="sxs-lookup"><span data-stu-id="a563c-106">Templates also allow administrators to deploy consistent teams across their organizations.</span></span> <span data-ttu-id="a563c-107">Эта статья предназначена для вас, если вы несете ответственность за планирование, развертывание и управление несколькими группами в организации здравоохранения.</span><span class="sxs-lookup"><span data-stu-id="a563c-107">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your Healthcare organization.</span></span>

<span data-ttu-id="a563c-108">В настоящее время мы предлагаем два основного шаблона здравоохранения, которые можно использовать в различных ситуациях.</span><span class="sxs-lookup"><span data-stu-id="a563c-108">We currently offer two first-party healthcare templates that you can leverage for a variety of situations.</span></span> <span data-ttu-id="a563c-109">Дополнительные сведения о шаблонах групп можно найти в разделе [Приступая к работе с шаблонами групп на консоли администрирования](../../get-started-with-teams-templates-in-the-admin-console.md).</span><span class="sxs-lookup"><span data-stu-id="a563c-109">To learn more about team templates in general, please see [Get started with Teams templates in the admin console](../../get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="collaborate-on-patient-care"></a><span data-ttu-id="a563c-110">Совместная работа над уходом пациента</span><span class="sxs-lookup"><span data-stu-id="a563c-110">Collaborate on patient care</span></span>

 <span data-ttu-id="a563c-111">Рационализация общения и совместной работы в любой среде, а также в других модулях или в сфере.</span><span class="sxs-lookup"><span data-stu-id="a563c-111">Streamline healthcare communication and collaboration within a ward, pod, or department.</span></span> <span data-ttu-id="a563c-112">Шаблон можно использовать для упрощения управления пациентами, а также для выполнения производственных задач.</span><span class="sxs-lookup"><span data-stu-id="a563c-112">The template can be used to facilitate patient management, as well as the operational needs of a ward.</span></span>

| <span data-ttu-id="a563c-113">Тип базового шаблона</span><span class="sxs-lookup"><span data-stu-id="a563c-113">Base template type</span></span> |<span data-ttu-id="a563c-114">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="a563c-114">baseTemplateId</span></span>| <span data-ttu-id="a563c-115">Свойства, которые поставляются с этим базовым шаблоном</span><span class="sxs-lookup"><span data-stu-id="a563c-115">Properties that come with this base template</span></span> |
| ------------------ |---|----------------------------------------------------- |
| <span data-ttu-id="a563c-116">Совместная работа над уходом пациента</span><span class="sxs-lookup"><span data-stu-id="a563c-116">Collaborate on patient care</span></span> |`healthcareWard` | <span data-ttu-id="a563c-117">Дистрибутор</span><span class="sxs-lookup"><span data-stu-id="a563c-117">Channels:</span></span><ul><li><span data-ttu-id="a563c-118">Общий</span><span class="sxs-lookup"><span data-stu-id="a563c-118">General</span></span></li><li><span data-ttu-id="a563c-119">Обслуживании</span><span class="sxs-lookup"><span data-stu-id="a563c-119">Announcements</span></span></li><li><span data-ttu-id="a563c-120">Huddles</span><span class="sxs-lookup"><span data-stu-id="a563c-120">Huddles</span></span></li><li><span data-ttu-id="a563c-121">До</span><span class="sxs-lookup"><span data-stu-id="a563c-121">Rounds</span></span></li><li><span data-ttu-id="a563c-122">Штата</span><span class="sxs-lookup"><span data-stu-id="a563c-122">Staffing</span></span></li><li><span data-ttu-id="a563c-123">Обучение</span><span class="sxs-lookup"><span data-stu-id="a563c-123">Training</span></span></li></ul> <span data-ttu-id="a563c-124">Приложения</span><span class="sxs-lookup"><span data-stu-id="a563c-124">Apps:</span></span> <ul><li><span data-ttu-id="a563c-125">Узел</span><span class="sxs-lookup"><span data-stu-id="a563c-125">Wiki</span></span></li>|
||||

## <a name="hospital"></a><span data-ttu-id="a563c-126">Больница</span><span class="sxs-lookup"><span data-stu-id="a563c-126">Hospital</span></span>

<span data-ttu-id="a563c-127">Эффективная связь и совместная работа между несколькими приложениями, многими из них и подразделениями в рамках больницы.</span><span class="sxs-lookup"><span data-stu-id="a563c-127">Streamline communication and collaboration between multiple wards, pods, and departments within a hospital.</span></span> <span data-ttu-id="a563c-128">Этот шаблон включает набор базовых каналов для операций, которые могут быть включены в больницы, и может быть саморасширяемым для включения specialtiesных и специальных средств.</span><span class="sxs-lookup"><span data-stu-id="a563c-128">This template includes a set of base channels for hospital operations, and can be self extended to include specialties, ad-hoc.</span></span>

| <span data-ttu-id="a563c-129">Тип базового шаблона</span><span class="sxs-lookup"><span data-stu-id="a563c-129">Base template type</span></span> |<span data-ttu-id="a563c-130">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="a563c-130">baseTemplateId</span></span> | <span data-ttu-id="a563c-131">Свойства, которые поставляются с этим базовым шаблоном</span><span class="sxs-lookup"><span data-stu-id="a563c-131">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="a563c-132">Больница</span><span class="sxs-lookup"><span data-stu-id="a563c-132">Hospital</span></span>|`healthcareHospital`|<span data-ttu-id="a563c-133">Дистрибутор</span><span class="sxs-lookup"><span data-stu-id="a563c-133">Channels:</span></span> <ul><li><span data-ttu-id="a563c-134">Общий</span><span class="sxs-lookup"><span data-stu-id="a563c-134">General</span></span><li><span data-ttu-id="a563c-135">Обслуживании</span><span class="sxs-lookup"><span data-stu-id="a563c-135">Announcements</span></span></li><li><span data-ttu-id="a563c-136">Соответствие требованиям</span><span class="sxs-lookup"><span data-stu-id="a563c-136">Compliance</span></span></li><li><span data-ttu-id="a563c-137">Custodial</span><span class="sxs-lookup"><span data-stu-id="a563c-137">Custodial</span></span></li><li><span data-ttu-id="a563c-138">Человеческие ресурсы</span><span class="sxs-lookup"><span data-stu-id="a563c-138">Human resources</span></span></li><li><span data-ttu-id="a563c-139">Pharmacy</span><span class="sxs-lookup"><span data-stu-id="a563c-139">Pharmacy</span></span></li></ul> <span data-ttu-id="a563c-140">Приложения</span><span class="sxs-lookup"><span data-stu-id="a563c-140">Apps:</span></span> <ul><li><span data-ttu-id="a563c-141">Узел</span><span class="sxs-lookup"><span data-stu-id="a563c-141">Wiki</span></span></li></ul>|
||||

## <a name="related-topics"></a><span data-ttu-id="a563c-142">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="a563c-142">Related topics</span></span>

[<span data-ttu-id="a563c-143">Начало работы с шаблонами Teams</span><span class="sxs-lookup"><span data-stu-id="a563c-143">Get started with Teams templates</span></span>](../../get-started-with-teams-templates-in-the-admin-console.md)