---
title: Прокси-серверы для Teams или Skype для бизнеса Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: reference
ms.assetid: 7acaf2c2-35fa-490f-84cd-822e446e0fc7
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Optimization
description: В этой статье приводятся сведения об использовании прокси-сервера в Skype для бизнеса.
ms.openlocfilehash: a154b36fc03dc84916d5cb4bd383ff80bef901cd
ms.sourcegitcommit: 2511cd95a186d95f4571afa4212f8e0fc207817d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/08/2020
ms.locfileid: "41863758"
---
# <a name="proxy-servers-for-skype-for-business-online"></a><span data-ttu-id="76903-103">Прокси-серверы Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="76903-103">Proxy servers for Skype for Business Online</span></span>

<span data-ttu-id="76903-104">В этой статье приводятся рекомендации по использованию прокси-сервера в Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="76903-104">This article provides guidance about using a proxy server with Skype for Business.</span></span>
  
## <a name="not-using-a-proxy-server-is-recommended"></a><span data-ttu-id="76903-105">Использовать прокси-сервер не рекомендуется</span><span class="sxs-lookup"><span data-stu-id="76903-105">Not using a proxy server is recommended</span></span>

<span data-ttu-id="76903-p101">Когда речь идет о трафике в Skype для бизнеса через прокси-серверы, корпорация Майкрософт рекомендует обойти прокси-серверы. Прокси-серверы не делают Skype для бизнеса более надежным, так как трафик уже зашифрован.</span><span class="sxs-lookup"><span data-stu-id="76903-p101">When it comes to Skype for Business traffic over proxies, Microsoft recommends bypassing proxies. Proxies don't make Skype for Business more secure because the traffic is already encrypted.</span></span>
  
<span data-ttu-id="76903-p102">А у прокси-сервера могут возникнуть проблемы. Проблемы, связанные с производительностью, могут быть введены в среду с помощью задержки и потери пакетов. Такие проблемы могут привести к негативной работе в таких рабочих группах и сценариях Skype для бизнеса, как звуковые и видеофайлы, где очень важны потоки в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="76903-p102">And having a proxy can cause issues. Performance-related problems can be introduced to the environment through latency and packet loss. Issues such as these will result in a negative experience in such Teams or Skype for Business scenarios as audio and video, where real-time streams are essential.</span></span>
  
## <a name="if-you-need-to-use-a-proxy-server"></a><span data-ttu-id="76903-111">Если нужно использовать прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="76903-111">If you need to use a proxy server</span></span>

<span data-ttu-id="76903-p103">В некоторых организациях нет возможности обойти прокси-сервер в трафике Skype для бизнеса. В этом случае следует обратить внимание на указанные выше проблемы.</span><span class="sxs-lookup"><span data-stu-id="76903-p103">Some organizations have no option to bypass a proxy for Skype for Business traffic. If that's the case for you, the problems mentioned above need to be kept in mind.</span></span>
  
<span data-ttu-id="76903-114">Майкрософт также рекомендует следующее:</span><span class="sxs-lookup"><span data-stu-id="76903-114">Microsoft also strongly recommends:</span></span>
  
- <span data-ttu-id="76903-115">использовать внешнее разрешение DNS;</span><span class="sxs-lookup"><span data-stu-id="76903-115">Using external DNS resolution</span></span>
    
- <span data-ttu-id="76903-116">использовать прямую маршрутизацию по UDP;</span><span class="sxs-lookup"><span data-stu-id="76903-116">Using direct UDP based routing</span></span>
    
- <span data-ttu-id="76903-117">разрешить трафик по UDP;</span><span class="sxs-lookup"><span data-stu-id="76903-117">Allowing UDP traffic</span></span>
    
- <span data-ttu-id="76903-118">Ниже приведены другие рекомендации по работе в сети.</span><span class="sxs-lookup"><span data-stu-id="76903-118">Following the other recommendations in our networking guidelines:</span></span>
    
  - [<span data-ttu-id="76903-119">Качество медиаданных и производительность сетевого подключения в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="76903-119">Media Quality and Network Connectivity Performance in Skype for Business Online</span></span>](media-quality-and-network-connectivity-performance.md)
    
  - [<span data-ttu-id="76903-120">Оптимизация сети для Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="76903-120">Optimizing your network for Skype for Business Online</span></span>](optimizing-your-network.md)
    
<span data-ttu-id="76903-121">Чтобы минимизировать возможные проблемы, следуйте этим рекомендациям.</span><span class="sxs-lookup"><span data-stu-id="76903-121">Following this guidance should minimize potential problems.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="76903-122">См. также</span><span class="sxs-lookup"><span data-stu-id="76903-122">Related topics</span></span>

[<span data-ttu-id="76903-123">Оптимизация сети для Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="76903-123">Optimizing your network for Skype for Business Online</span></span>](optimizing-your-network.md)
 