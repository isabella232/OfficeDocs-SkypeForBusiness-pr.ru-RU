---
title: Проверка подлинности в комнатах Microsoft Teams
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-collaboration
description: Сведения о настройке современной проверки подлинности в комнатах Microsoft Teams
ms.openlocfilehash: bef547ab0b9ade2edc433ec64bb1ef61eee4c040
ms.sourcegitcommit: 0fdc60840f45ff5b0a39a8ec4a21138f6cab49c9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/07/2020
ms.locfileid: "43160120"
---
# <a name="authentication-in-microsoft-teams-rooms"></a><span data-ttu-id="13655-103">Проверка подлинности в комнатах Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="13655-103">Authentication in Microsoft Teams Rooms</span></span>

<span data-ttu-id="13655-104">Управление учетными записями в Microsoft Teams комнаты обрабатываются на уровне приложения.</span><span class="sxs-lookup"><span data-stu-id="13655-104">Account management for Microsoft Teams Rooms devices is handled at the application level.</span></span> <span data-ttu-id="13655-105">Приложение подключается к Microsoft Teams, Skype для бизнеса и Exchange, чтобы получить доступ к ресурсам для учетной записи комнаты, чтобы обеспечить возможность звонков и собраний.</span><span class="sxs-lookup"><span data-stu-id="13655-105">The application connects to Microsoft Teams, Skype for Business, and Exchange to get resources for the room account to enable calling and meeting experiences.</span></span> <span data-ttu-id="13655-106">Это устройство остается независимым для обеспечения постоянной поддержки, сценариев вызова (для устройств, настроенных с помощью абонентского плана) и настраиваемых механизмов блокировки, реализованных на этих устройствах.</span><span class="sxs-lookup"><span data-stu-id="13655-106">The device is kept account agnostic to allow for always-on capabilities, calling scenarios (for devices configured with a Calling Plan), and custom lockdown mechanisms implemented on these devices.</span></span> <span data-ttu-id="13655-107">Это означает, что проверка подлинности для этих устройств происходит не так, как для конечных пользователей.</span><span class="sxs-lookup"><span data-stu-id="13655-107">This means that authentication for these devices happen in a different way than for end-user devices.</span></span>  

<span data-ttu-id="13655-108">Современная проверка подлинности рекомендуется для всех пользователей, использующих устройства в Microsoft Teams, с Office 365.</span><span class="sxs-lookup"><span data-stu-id="13655-108">Modern authentication is recommended for all customers using Microsoft Teams Rooms devices with Office 365.</span></span> <span data-ttu-id="13655-109">Если вы используете локальное развертывание Exchange Server или Skype для бизнеса Server, настройте [гибридную современной проверку подлинности](https://docs.microsoft.com/office365/enterprise/hybrid-modern-auth-overview) с помощью Azure Active Directory (Azure AD), чтобы включить использование современной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="13655-109">If you have an on-premises deployment of Exchange server or Skype for Business server, configure [hybrid modern authentication](https://docs.microsoft.com/office365/enterprise/hybrid-modern-auth-overview) with Azure Active Directory (Azure AD) to enable using modern authentication.</span></span>

<span data-ttu-id="13655-110">Современная проверка подлинности поддерживается в комнатах Microsoft Teams версии 4.4.25.0 и более поздних.</span><span class="sxs-lookup"><span data-stu-id="13655-110">Modern authentication is supported on Microsoft Teams Rooms version 4.4.25.0 and later.</span></span>

## <a name="modern-authentication"></a><span data-ttu-id="13655-111">Современная проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="13655-111">Modern authentication</span></span>

<span data-ttu-id="13655-112">При использовании современной проверки подлинности в приложении Microsoft Teams комнаты, Библиотека проверки подлинности Active Directory (ADAL) используется для подключения к Microsoft Teams, Exchange и Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="13655-112">When you use modern authentication with the Microsoft Teams Rooms application, Active Directory Authentication Library (ADAL) is used to connect to Microsoft Teams, Exchange, and Skype for Business.</span></span> <span data-ttu-id="13655-113">Устройство Microsoft Teams является общим устройством и выполняет ночную перезагрузку для обеспечения бесперебойной работы и получения критической операционной системы, драйвера, встроенного по или обновлений приложения.</span><span class="sxs-lookup"><span data-stu-id="13655-113">A Microsoft Teams Rooms device is a shared device and performs a nightly reboot to ensure smooth functioning and to get critical operating system, driver, firmware, or application updates.</span></span> <span data-ttu-id="13655-114">Механизм современной проверки подлинности использует для авторизации учетных данных, предоставленных для [пароля владельца ресурса](https://tools.ietf.org/html/rfc6749#section-1.3.3) , тип Grant в OAuth 2,0, для которого не требуется вмешательство пользователя.</span><span class="sxs-lookup"><span data-stu-id="13655-114">The modern authentication mechanism uses the [resource owner password credentials](https://tools.ietf.org/html/rfc6749#section-1.3.3) authorization grant type in OAuth 2.0, which doesn't require any user intervention.</span></span> <span data-ttu-id="13655-115">Это является одной из основных различий в том, как технология современной проверки подлинности работает для учетных записей пользователей и ресурсов, используемых приложением Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="13655-115">This is one of the key differences between how modern authentication works for user accounts versus resource accounts that are used by the Microsoft Teams Rooms application.</span></span> <span data-ttu-id="13655-116">Из-за этой возможности учетные записи ресурсов в Microsoft Teams не должны быть настроены на использование многофакторной проверки подлинности (MFA), проверки подлинности на основе сертификатов и проверки подлинности клиента (для конечных пользователей).</span><span class="sxs-lookup"><span data-stu-id="13655-116">Because of this, Microsoft Teams Rooms resource accounts shouldn't be configured to use multi-factor authentication (MFA), smart card authentication, or client certificate-based authentication (which are all available for end users).</span></span>

<span data-ttu-id="13655-117">Другие ключевые различия между работой современной проверки подлинности в Microsoft Teams для устройств и конечных пользователей в том, что вы не можете использовать учетную запись ресурса для применения политик условного доступа на уровне устройства, например "требуется ли пометка устройства как жалоб", или "требуется гибридное устройство присоединено к Azure Active Directory" и т. д.</span><span class="sxs-lookup"><span data-stu-id="13655-117">The other key difference between how modern authentication works on Microsoft Teams Rooms devices and end-user devices is that you can't use a resource account to apply device-level conditional access policies such as "Require device to be marked as complaint", or "Require Hybrid Azure AD joined device", and so on.</span></span> <span data-ttu-id="13655-118">Это связано с тем, что понятия уровня устройства не применяются к современной проверке подлинности при использовании на уровне приложения.</span><span class="sxs-lookup"><span data-stu-id="13655-118">This is because device-level concepts don't apply to modern authentication when used at the application level.</span></span> <span data-ttu-id="13655-119">Вместо этого вы можете зарегистрировать устройство в Microsoft Intune и применить политики соответствия, следуя указаниям, [приведенным здесь](https://techcommunity.microsoft.com/t5/intune-customer-success/bg-p/IntuneCustomerSuccess).</span><span class="sxs-lookup"><span data-stu-id="13655-119">Instead, you can enroll a device in Microsoft Intune and apply compliance policies by using the guidance [here](https://techcommunity.microsoft.com/t5/intune-customer-success/bg-p/IntuneCustomerSuccess).</span></span>

## <a name="enable-modern-authentication-on-a-microsoft-teams-rooms-device"></a><span data-ttu-id="13655-120">Включение современной проверки подлинности на устройстве с комнатой Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="13655-120">Enable modern authentication on a Microsoft Teams Rooms device</span></span>

<span data-ttu-id="13655-121">В помещениях Microsoft Teams для использования современной проверки подлинности в Skype для бизнеса и Exchange включите параметр на стороне клиента для современной проверки подлинности на устройстве Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="13655-121">For Microsoft Teams Rooms to use modern authentication with Skype for Business and Exchange, enable the client-side setting for modern authentication on the Microsoft Teams Rooms device.</span></span> <span data-ttu-id="13655-122">Это можно сделать в разделе Параметры устройства или XML-файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="13655-122">You can do this in the device settings or in the XML config file.</span></span>

> [!NOTE]
> <span data-ttu-id="13655-123">Перед включением параметра на стороне клиента для современной проверки подлинности убедитесь, что ваша среда правильно настроена для использования современной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="13655-123">Before you enable the client-side setting for modern authentication, make sure that your environment is set up correctly to use modern authentication.</span></span>

### <a name="using-device-settings"></a><span data-ttu-id="13655-124">Использование параметров устройства</span><span class="sxs-lookup"><span data-stu-id="13655-124">Using device settings</span></span>

1. <span data-ttu-id="13655-125">На устройстве "комнаты группы Microsoft" перейдите на вкладку " **Дополнительно** " (**...**).</span><span class="sxs-lookup"><span data-stu-id="13655-125">On the Microsoft Team Rooms device, go to **More** (**...**).</span></span>
    
2. <span data-ttu-id="13655-126">Выберите **Параметры**, а затем введите имя пользователя и пароль администратора устройства.</span><span class="sxs-lookup"><span data-stu-id="13655-126">Select **Settings**, and then enter the device administrator username and password.</span></span>
3. <span data-ttu-id="13655-127">Перейдите на вкладку **учетная запись** , включите функцию **современной проверки подлинности**, а затем нажмите кнопку **сохранить и выйти**.</span><span class="sxs-lookup"><span data-stu-id="13655-127">Go to the **Account** tab, turn on **Modern Authentication**, and then select **Save and exit**.</span></span>

### <a name="using-the-xml-config-file"></a><span data-ttu-id="13655-128">Использование XML-файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="13655-128">Using the XML config file</span></span>

<span data-ttu-id="13655-129">В файле SkypeSettings. XML установите для современной проверки подлинности XML-элемент **true**, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="13655-129">In your SkypeSettings.xml file, set the modern authentication XML element to **True**, as follows.</span></span>

```
<ModernAuthEnabled>True</ModernAuthEnabled>
```

<span data-ttu-id="13655-130">Чтобы применить этот параметр, в разделе [Управление параметрами консоли Microsoft Teams можно удаленно с помощью XML-файла конфигурации](xml-config-file.md).</span><span class="sxs-lookup"><span data-stu-id="13655-130">To apply the setting, see [Manage a Microsoft Teams Rooms console settings remotely with an XML configuration file](xml-config-file.md).</span></span>

## <a name="prepare-your-environment-for-modern-authentication"></a><span data-ttu-id="13655-131">Подготовка среды для современной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="13655-131">Prepare your environment for modern authentication</span></span>

<span data-ttu-id="13655-132">Прежде чем начать, убедитесь в том, что вы понимаете модели удостоверений, которые нужно использовать с Office 365 и Azure AD.</span><span class="sxs-lookup"><span data-stu-id="13655-132">Before you begin, make sure you understand the identity models to use with Office 365 and Azure AD.</span></span> <span data-ttu-id="13655-133">Дополнительные сведения можно найти в [моделях удостоверений Office 365 и Azure Active Directory](https://docs.microsoft.com/Office365/Enterprise/about-office-365-identity) , а также в [гибридной идентификации и синхронизации каталогов для Office 365](https://docs.microsoft.com/Office365/Enterprise/plan-for-directory-synchronization).</span><span class="sxs-lookup"><span data-stu-id="13655-133">You can find more information at [Office 365 identity models and Azure Active Directory](https://docs.microsoft.com/Office365/Enterprise/about-office-365-identity) and at [Hybrid identity and directory synchronization for Office 365](https://docs.microsoft.com/Office365/Enterprise/plan-for-directory-synchronization).</span></span>

### <a name="enable-modern-authentication-in-office-365"></a><span data-ttu-id="13655-134">Включение современной проверки подлинности в Office 365</span><span class="sxs-lookup"><span data-stu-id="13655-134">Enable modern authentication in Office 365</span></span>

<span data-ttu-id="13655-135">Чтобы включить современной проверки подлинности в Exchange Online, ознакомьтесь со сведениями [Включение современной проверки подлинности в Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).</span><span class="sxs-lookup"><span data-stu-id="13655-135">To turn on modern authentication for Exchange Online, see [Enable modern authentication in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).</span></span> <span data-ttu-id="13655-136">Если вы используете Skype для бизнеса Online, вам также необходимо убедиться, что для Skype для бизнеса Online включена современная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="13655-136">If you use Skype for Business Online, you should also make sure that modern authentication is turned on for Skype for Business Online.</span></span> <span data-ttu-id="13655-137">Дополнительные сведения можно найти в статье [Skype для бизнеса Online: Включите клиент для современной проверки подлинности](https://aka.ms/SkypeModernAuth).</span><span class="sxs-lookup"><span data-stu-id="13655-137">To learn more, see [Skype for Business Online: Enable your tenant for modern authentication](https://aka.ms/SkypeModernAuth).</span></span>

<span data-ttu-id="13655-138">Мы рекомендуем не удалять основные политики проверки подлинности для Exchange Online и не отключать обычную проверку подлинности в клиенте, прежде чем вы проверили, что в Microsoft Teams можно успешно войти в Exchange Online, а также в Skype для бизнеса Online, если включен параметр современной проверки подлинности, а устройства, которые еще не настроены для использования обычной проверки подлинности,</span><span class="sxs-lookup"><span data-stu-id="13655-138">We recommended that you do not remove basic authentication policies for Exchange Online or disable basic authentication for your tenant before you have validated that Microsoft Teams Rooms devices can sign in to Exchange Online and Teams or Skype for Business Online successfully when the modern authentication setting is on and that there are no devices that are still configured to use basic authentication.</span></span>

<span data-ttu-id="13655-139">Дополнительные сведения об отключении обычной проверки подлинности в Exchange Online можно найти [в разделе Отключение обычной проверки подлинности в Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online).</span><span class="sxs-lookup"><span data-stu-id="13655-139">For more information about disabling basic authentication in Exchange Online, see [Disable Basic authentication in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online).</span></span>

## <a name="hybrid-modern-authentication"></a><span data-ttu-id="13655-140">Гибридная современная проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="13655-140">Hybrid modern authentication</span></span>

<span data-ttu-id="13655-141">Чтобы убедиться в успешной проверке подлинности на локальном сервере Exchange Server и (или) Skype для бизнеса, необходимо убедиться, что учетная запись ресурса, используемая в комнатах Microsoft Teams, настроена на получение авторизации из Azure AD.</span><span class="sxs-lookup"><span data-stu-id="13655-141">To ensure successful authentication to your on-premise Exchange server and/or Skype for Business server, you must make sure the resource account that's used with Microsoft Teams Rooms is configured to get authorization from Azure AD.</span></span> <span data-ttu-id="13655-142">Дополнительные сведения о гибридных удостоверениях и методах, которые можно использовать для Организации, читайте в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="13655-142">To learn more about hybrid identity and methods that works for your organization, read the following topics:</span></span> 

- [<span data-ttu-id="13655-143">Что такое синхронизация хэша пароля?</span><span class="sxs-lookup"><span data-stu-id="13655-143">What is password hash sync?</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-phs)
- [<span data-ttu-id="13655-144">Что такое сквозная проверка подлинности?</span><span class="sxs-lookup"><span data-stu-id="13655-144">What is passthrough authentication?</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta)
- [<span data-ttu-id="13655-145">Что такое Федерация?</span><span class="sxs-lookup"><span data-stu-id="13655-145">What is federation?</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-fed)

### <a name="prerequisites-specific-to-microsoft-teams-rooms"></a><span data-ttu-id="13655-146">Предварительные требования для комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="13655-146">Prerequisites specific to Microsoft Teams Rooms</span></span>

<span data-ttu-id="13655-147">Требования, необходимые для включения современной проверки подлинности в гибридной топологии, рассматриваются в [обзорах гибридной современной проверки подлинности и предварительных требованиях для их использования с локальными серверами Skype для бизнеса и Exchange Server](https://docs.microsoft.com/office365/enterprise/hybrid-modern-auth-overview).</span><span class="sxs-lookup"><span data-stu-id="13655-147">The prerequisites to enable modern authentication in your hybrid topology are covered in [Hybrid modern authentication overview and prerequisites for using it with on-premises Skype for Business and Exchange servers](https://docs.microsoft.com/office365/enterprise/hybrid-modern-auth-overview).</span></span> <span data-ttu-id="13655-148">Применимы все предварительные требования, описанные в этой статье.</span><span class="sxs-lookup"><span data-stu-id="13655-148">All the prerequisites discussed in the article apply.</span></span>

<span data-ttu-id="13655-149">Тем не менее, поскольку комнаты Microsoft Teams используют для проверки подлинности [учетных данных владельца ресурсов](https://tools.ietf.org/html/rfc6749#section-1.3.3) и базовые интерфейсы API для оставшейся работы, следует учитывать важные отличия, связанные с комнатами Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="13655-149">However, because Microsoft Teams Rooms uses [resource owner password credentials](https://tools.ietf.org/html/rfc6749#section-1.3.3) authorization and the underlying REST APIs for modern authentication, the following are important differences be aware of that are specific to Microsoft Team Rooms.</span></span>

- <span data-ttu-id="13655-150">У вас должен быть сервер Exchange Server 2016 обновления HF1 или более поздней версии или Exchange Server 2019 CU1 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="13655-150">You must have Exchange server 2016 CU8 or later, or Exchange Server 2019 CU1 or later.</span></span>
- <span data-ttu-id="13655-151">У вас должен быть Skype для бизнеса Server 2015 CU5 или более поздней версии или Skype для бизнеса Server 2019 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="13655-151">You must have Skype for Business Server 2015 CU5 or later, or Skype for Business Server 2019 or later.</span></span>
- <span data-ttu-id="13655-152">MFA не поддерживается вне зависимости от того, какая у вас топология.</span><span class="sxs-lookup"><span data-stu-id="13655-152">MFA isn't supported regardless of the topology you have.</span></span>
- <span data-ttu-id="13655-153">Если вы используете сторонний поставщик проверки подлинности, который поддерживается Azure AD, он должен поддерживать авторизацию учетных данных OAuth и использовать пароль владельца ресурса.</span><span class="sxs-lookup"><span data-stu-id="13655-153">If you use a third-party authentication provider that's supported by Azure AD, it must support OAuth and use  resource owner password credentials authorization.</span></span>
- <span data-ttu-id="13655-154">Не используйте политики условного доступа на уровне устройства для учетной записи ресурсов, настроенной для приложения.</span><span class="sxs-lookup"><span data-stu-id="13655-154">Do not use device-level conditional access policies for a resource account configured with the application.</span></span> <span data-ttu-id="13655-155">Это может привести к сбоям при входе.</span><span class="sxs-lookup"><span data-stu-id="13655-155">Doing so will result in sign-in failures.</span></span> <span data-ttu-id="13655-156">Вместо этого зарегистрируйте устройство в Microsoft Intune и примените политики соответствия, используя руководство, опубликованное [здесь](https://techcommunity.microsoft.com/t5/intune-customer-success/bg-p/IntuneCustomerSuccess).</span><span class="sxs-lookup"><span data-stu-id="13655-156">Instead, enroll a device in Microsoft Intune and apply compliance policies by using the guidance published [here](https://techcommunity.microsoft.com/t5/intune-customer-success/bg-p/IntuneCustomerSuccess).</span></span>

### <a name="configure-exchange-server"></a><span data-ttu-id="13655-157">Настройка сервера Exchange Server</span><span class="sxs-lookup"><span data-stu-id="13655-157">Configure Exchange Server</span></span>

<span data-ttu-id="13655-158">Сведения о включении гибридной современной проверки подлинности в Exchange Server можно узнать в разделе [Настройка локального сервера Exchange Server для использования гибридной современной проверки подлинности](https://docs.microsoft.com/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication).</span><span class="sxs-lookup"><span data-stu-id="13655-158">To enable hybrid modern authentication in Exchange Server, see [How to configure Exchange Server on-premises to use hybrid modern authentication](https://docs.microsoft.com/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication).</span></span>

### <a name="configure-skype-for-business-server"></a><span data-ttu-id="13655-159">Настройка Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="13655-159">Configure Skype for Business Server</span></span>

<span data-ttu-id="13655-160">Для включения гибридной современной проверки подлинности в Skype для бизнеса Server ознакомьтесь со [сведениями о том, как настроить гибридную современной проверки подлинности в локальной среде Skype для бизнеса](https://docs.microsoft.com/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication).</span><span class="sxs-lookup"><span data-stu-id="13655-160">To enable hybrid modern authentication with Skype for Business Server, see [How to configure Skype for Business on-premises to use hybrid modern authentication](https://docs.microsoft.com/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication).</span></span>

### <a name="remove-or-disable-skype-for-business-and-exchange"></a><span data-ttu-id="13655-161">Удаление и отключение Skype для бизнеса и Exchange</span><span class="sxs-lookup"><span data-stu-id="13655-161">Remove or disable Skype for Business and Exchange</span></span>

<span data-ttu-id="13655-162">Если в вашей настройке не разрешена Гибридная современная проверка подлинности или вы хотите удалить или отключить гибридную современной проверки подлинности для Exchange или Skype для бизнеса, ознакомьтесь с разрядом [Удаление и отключение гибридной современной проверки подлинности в Skype для бизнеса и Exchange](https://docs.microsoft.com/Office365/Enterprise/remove-or-disable-hybrid-modern-authentication-from-skype-for-business-and-excha).</span><span class="sxs-lookup"><span data-stu-id="13655-162">If your setup doesn't allow for hybrid modern authentication or you need to remove or disable hybrid modern authentication for Exchange or Skype for Business, see [Removing or disabling hybrid modern authentication from Skype for Business and Exchange](https://docs.microsoft.com/Office365/Enterprise/remove-or-disable-hybrid-modern-authentication-from-skype-for-business-and-excha).</span></span>

### <a name="azure-ad-conditional-access"></a><span data-ttu-id="13655-163">Условный доступ Azure AD</span><span class="sxs-lookup"><span data-stu-id="13655-163">Azure AD conditional access</span></span>

<span data-ttu-id="13655-164">Вы можете настроить учетную запись ресурса, используемую в комнатах Microsoft Teams, для IP и доступа на основе местоположения.</span><span class="sxs-lookup"><span data-stu-id="13655-164">You can configure a resource account used with Microsoft Teams Rooms for IP/location-based access.</span></span> <span data-ttu-id="13655-165">Дополнительные сведения можно найти в разделе [Условный доступ: блокировать доступ по местоположению](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-location).</span><span class="sxs-lookup"><span data-stu-id="13655-165">To learn more, see [Conditional Access: Block access by location](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-location).</span></span>

<span data-ttu-id="13655-166">Другие политики условного доступа не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="13655-166">No other conditional access policies are supported.</span></span> <span data-ttu-id="13655-167">Дополнительные сведения о соответствии устройств можно найти [в руководстве.](https://techcommunity.microsoft.com/t5/intune-customer-success/bg-p/IntuneCustomerSuccess)</span><span class="sxs-lookup"><span data-stu-id="13655-167">For more information about device compliance, see the guidance  [here](https://techcommunity.microsoft.com/t5/intune-customer-success/bg-p/IntuneCustomerSuccess).</span></span>  