---
title: 'Пример сценария PowerShell: создание групп безопасности для преподавателей и учащихся в вашем учебном заведении'
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: angch
ms.service: msteams
audience: admin
description: Используйте этот сценарий PowerShell для создания групп безопасности, необходимых для управления политиками Teams для преподавателей и учащихся в вашем учебном заведении.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 4b468ae05139571f395962b96f2963c7bb77b2e6
ms.sourcegitcommit: dc3e8ae454c42981f037f4de2e48005428b6078e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/31/2020
ms.locfileid: "46534122"
---
# <a name="powershell-script-sample---create-security-groups-for-educators-and-students-in-your-school"></a><span data-ttu-id="7264c-103">Пример сценария PowerShell: создание групп безопасности для преподавателей и учащихся в вашем учебном заведении</span><span class="sxs-lookup"><span data-stu-id="7264c-103">PowerShell script sample - Create security groups for educators and students in your school</span></span>

<span data-ttu-id="7264c-104">Используйте этот сценарий PowerShell для создания групп безопасности, которые необходимо для управления политиками Microsoft Teams в вашем учебном заведении.</span><span class="sxs-lookup"><span data-stu-id="7264c-104">Use this PowerShell script to create the security groups that you need to manage Microsoft Teams policies in your school.</span></span> <span data-ttu-id="7264c-105">Функция " [Назначение политики для групп](../assign-policies.md#assign-a-policy-to-a-group) " в Teams позволяет назначить политику группе пользователей, например группе безопасности.</span><span class="sxs-lookup"><span data-stu-id="7264c-105">The [policy assignment to groups](../assign-policies.md#assign-a-policy-to-a-group) feature in Teams lets you assign a policy to a group of users, such as a security group.</span></span> <span data-ttu-id="7264c-106">Назначение политики распространяется на пользователей группы в соответствии с правилами приоритета.</span><span class="sxs-lookup"><span data-stu-id="7264c-106">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="7264c-107">Когда участники добавляются в группу или удаляются из нее, их унаследованные назначения политик обновляются соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="7264c-107">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="7264c-108">Этот сценарий PowerShell создает две группы безопасности: для сотрудников и преподавателей, а также для учащихся в вашем учебном заведении на основе типа лицензии.</span><span class="sxs-lookup"><span data-stu-id="7264c-108">This PowerShell script creates two security groups, one for staff and educators and another for students in your school, based on license type.</span></span> <span data-ttu-id="7264c-109">Затем вы можете назначать политики для групп безопасности, которые вы создали.</span><span class="sxs-lookup"><span data-stu-id="7264c-109">You can then assign policies to the security groups that you created.</span></span> <span data-ttu-id="7264c-110">Для получения дополнительных сведений об использовании этого сценария ознакомьтесь с разделом [назначение политик большим наборам пользователей в вашем учебном заведении](../batch-group-policy-assignment-edu.md).</span><span class="sxs-lookup"><span data-stu-id="7264c-110">For more information about using this script, see [Assign policies to large sets of users in your school](../batch-group-policy-assignment-edu.md).</span></span>

<span data-ttu-id="7264c-111">Этот сценарий делает следующее:</span><span class="sxs-lookup"><span data-stu-id="7264c-111">This script does the following:</span></span>

- <span data-ttu-id="7264c-112">Определяет сотрудников и преподавателей, которым назначена SKU факультета, создает группу безопасности, а затем добавляет в нее сотрудников и преподавателей.</span><span class="sxs-lookup"><span data-stu-id="7264c-112">Identifies staff and educators who are assigned a Faculty SKU, creates a security group, and then adds staff and educators  to the group.</span></span>
- <span data-ttu-id="7264c-113">Определяет учащихся, которым назначена SKU учащихся, создает группу безопасности, а затем добавляет учащихся в группу.</span><span class="sxs-lookup"><span data-stu-id="7264c-113">Identifies students who are assigned a Student SKU, creates a security group, and then adds the students to the group.</span></span>
- <span data-ttu-id="7264c-114">Обновляет сведения о членстве в каждой группе безопасности, чтобы добавить или удалить сотрудников, преподавателей и учащихся, в зависимости от того, есть ли у них лицензия.</span><span class="sxs-lookup"><span data-stu-id="7264c-114">Updates the membership of each security group to add or remove staff, educators, and students based on whether they have a license.</span></span>

<span data-ttu-id="7264c-115">Для обеспечения актуальности и актуальности групп безопасности вам потребуется регулярно запускать этот сценарий.</span><span class="sxs-lookup"><span data-stu-id="7264c-115">You'll need to run this script regularly to keep the security groups fresh and up to date.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7264c-116">Важно понимать [правила приоритета](../assign-policies.md#precedence-rules) и [ранжирование назначения групп](../assign-policies.md#group-assignment-ranking) при назначении политик группам.</span><span class="sxs-lookup"><span data-stu-id="7264c-116">It's important to understand [precedence rules](../assign-policies.md#precedence-rules) and [group assignment ranking](../assign-policies.md#group-assignment-ranking) when assigning policies to groups.</span></span> <span data-ttu-id="7264c-117">Убедитесь, что вы прочитали и понимаете принципы, необходимые для [назначения политик группам](../assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups).</span><span class="sxs-lookup"><span data-stu-id="7264c-117">Make sure that you read and understand the concepts in [What you need to know about policy assignment to groups](../assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups).</span></span>

## <a name="before-you-start"></a><span data-ttu-id="7264c-118">Перед началом работы</span><span class="sxs-lookup"><span data-stu-id="7264c-118">Before you start</span></span>

<span data-ttu-id="7264c-119">Скачайте и установите [модуль PowerShell Skype для бизнеса Online](https://www.microsoft.com/download/details.aspx?id=39366), а затем перезагрузите компьютер при появлении соответствующего запроса.</span><span class="sxs-lookup"><span data-stu-id="7264c-119">Download and install the [Skype for Business Online PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366), and then restart your computer if prompted.</span></span>

<span data-ttu-id="7264c-120">Для более рациональной работы ознакомьтесь со статьей [Управление Skype для бизнеса Online в Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell) и [Teams PowerShell overviews](../teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="7264c-120">To lean more, see [Manage Skype for Business Online with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell) and [Teams PowerShell overview](../teams-powershell-overview.md).</span></span>


## <a name="sample-script"></a><span data-ttu-id="7264c-121">Пример сценария</span><span class="sxs-lookup"><span data-stu-id="7264c-121">Sample script</span></span>

```powershell
<#
Script Name:
CreateOrUpdate_SecurityGroup_Per_LicenseType.ps1
Synopsis:
This script is designed to perform following operations:
1. Create a security group for faculty and student members based on the assigned license SKU and add the members accordingly.
2. Update the security group to add/remove teachers and students so that only users who have a valid teacher/student license are present in the group.
The output of the script is written in a log file present at location: C:\results\log.txt
Written By: 
Mihir Roy
Change Log:
Version 1.0, 10/08/2019 - First Draft
#>

#Figure out to determine if the user is using an existing group or creating a new one
param
(
    [string]$teachergroupname,
    [string]$teachergroupdesc,
    [string]$studentgroupname,
    [string]$studentgroupdesc,
    [Guid]$facultyid,
    [Guid]$studentid
)

[bool] $create = $false

if ([string]::IsNullOrEmpty($teachergroupname) -and [string]::IsNullOrEmpty($studentgroupname) -and [string]::IsNullOrEmpty($studentid) -and [string]::IsNullOrEmpty($facultyid)) {
    throw "Please enter valid groupnames to create groups for Teachers and Students. In order to update a group, please enter the teacher and/or student group id's."
}

#Connect to Azure AD
Write-Host "`n"
Write-Host -ForegroundColor Green "Please enter your Global Administrator Username and Password"
Write-Host "`n"
Connect-MsolService

[Guid] $teachergroupid = New-Guid
[Guid] $studentgroupid = New-Guid

if (![string]::IsNullOrEmpty($teachergroupname)) {
    New-MsolGroup -DisplayName $teachergroupname -Description $teachergroupdesc
    $Group = Get-MsolGroup -SearchString $teachergroupname
    $teachergroupid = $Group.ObjectId
    $create = $true
}

if (![string]::IsNullOrEmpty($studentgroupname)) {
    New-MsolGroup -DisplayName $studentgroupname -Description $studentgroupdesc
    $Group = Get-MsolGroup -SearchString $studentgroupname
    $studentgroupid = $Group.ObjectId
    $create = $true
}


#Build the Students Array
$StudentsArray = @()

#Build the Teachers Array
$TeachersArray = @()

#Build the Student Sku Array
$StudentSkus = @()
$AllSkus = Get-AzureADSubscribedSku
$StudentSkuIDs = ($AllSkus | ? {$_.skupartnumber -like "*student*"}).skuid
Write-Host -ForegroundColor Green "The Student Skus identified are listed below:"
Foreach ($Element in $StudentSkuIDs) {
$SkuPart = (Get-AzureADSubscribedSku | ? {$_.SkuID -eq $Element}).SkuPartNumber
Write-Host -ForegroundColor Green "Student SkuID ${Element} for License $SkuPart"
}
Write-Host "`n"

#Build the Teacher Sku Array
$TeacherSkus = @()
$AllSkus = Get-AzureADSubscribedSku
$TeacherSkuIDs = ($AllSkus | ? {$_.skupartnumber -like "*faculty*"}).skuid
Write-Host -ForegroundColor Green "The Teacher Skus identified are listed below:"
Foreach ($Element in $TeacherSkuIDs) {
$SkuPart = (Get-AzureADSubscribedSku | ? {$_.SkuID -eq $Element}).SkuPartNumber
Write-Host -ForegroundColor Green "Teacher SkuID ${Element} for License $SkuPart"
}
Write-Host "`n"

#Get All Users in AAD
Write-Host -ForegroundColor Green "Getting All Users in Azure Active Directory with an assigned license"
Write-Host "`n"
$AllUsers = Get-AzureADUser -All $true | ? {$_.AssignedLicenses -ne $null}

$teacherAdd = $create -and ($teachergroupid -ne $null)
$studentAdd = $create -and ($studentgroupid -ne $null)

#Start foreach loop for all users with student licenses
if ($teacherAdd -or $studentAdd) {
    Foreach ($User in $AllUsers) {
    $ObjectID = $User.ObjectID
    Write-host "`n"
    Write-Host -ForegroundColor Green "Getting Assigned Licenses for $DN"
    $GetUser = Get-AzureADUser -objectid $user.objectid
    $AssignedLicenses = ($GetUser | select -ExpandProperty assignedlicenses).skuid
    Write-Host -ForegroundColor Green "User Assigned License: " $User.Displayname "-" $AssignedLicenses "-" $User.ObjectId


    #Set Variables
    $UPN = $User.userprincipalname
    $DN = $User.Displayname
    $OBJ = $User.ObjectID
    $Age = $User.AgeGroup
    $Consent = $User.ConsentProvidedForMinor
    $Legal = $User.LegalAgeGroupClassification

        #Start foreach loop for all assigned skus
        Foreach ($License in $AssignedLicenses) {

            #Creating new PS Object for each Sku and adding to the array
            If ($TeacherSkuIDs -contains $License) {
                $TeacherObj = New-Object PSObject
                $TeacherObj | Add-Member NoteProperty -Name UserPrincipalName -Value $UPN
                $TeacherObj | Add-Member NoteProperty -Name DisplayName -Value $DN
                $TeacherObj | Add-Member NoteProperty -Name ObjectID -Value $OBJ
                $TeacherObj | Add-Member NoteProperty -Name SkuID -Value $License
                $TeacherObj | Add-Member NoteProperty -Name AgeGroup -Value $Age
                $TeacherObj | Add-Member NoteProperty -Name ConsentProvidedForMinor -Value $Consent
                $TeacherObj | Add-Member NoteProperty -Name LegalAgeGroupClassification -Value $Legal
                $TeachersArray += $TeacherObj
                if ($teachergroupid -ne $null) {
                    Add-MsolGroupMember -GroupObjectId $teachergroupid -GroupMemberType User -GroupMemberObjectId $OBJ
                }
            }
                        
            If ($StudentSkuIDs -contains $License) {
                $StudentObj = New-Object PSObject
                $StudentObj | Add-Member NoteProperty -Name UserPrincipalName -Value $UPN
                $StudentObj | Add-Member NoteProperty -Name DisplayName -Value $DN
                $StudentObj | Add-Member NoteProperty -Name ObjectID -Value $OBJ
                $StudentObj | Add-Member NoteProperty -Name SkuID -Value $License
                $StudentObj | Add-Member NoteProperty -Name AgeGroup -Value $Age
                $StudentObj | Add-Member NoteProperty -Name ConsentProvidedForMinor -Value $Consent
                $StudentObj | Add-Member NoteProperty -Name LegalAgeGroupClassification -Value $Legal
                $StudentsArray += $StudentObj
                if ($studentgroupid -ne $null) {
                    Add-MsolGroupMember -GroupObjectId $studentgroupid -GroupMemberType User -GroupMemberObjectId $OBJ
                }
            }
        }
    }
}

if ((!$teacherAdd) -and ($facultyid -ne $null)) {
    #Users to be Added in the Teacher Group that are not present
    $teacherGrpMembers = Get-MsolGroupMember -GroupObjectId $facultyid
    $teachersToAdd = ($AllUsers | ? {$_.ObjectId -ne $null}).objectid | Where {($teacherGrpMembers | ? {$_.ObjectId -ne $null}).objectid -NotContains $_}
    Foreach ($id in $teachersToAdd) {
        $GetUser = Get-AzureADUser -objectid $id
        $AssignedLicenses = ($GetUser | select -ExpandProperty assignedlicenses).skuid
        Foreach ($License in $AssignedLicenses) {

            #Adding faculty members to the security group
            If ($TeacherSkuIDs -contains $License) {
                Add-MsolGroupMember -GroupObjectId $facultyid -GroupMemberType User -GroupMemberObjectId $id
            }
        }
    }
    
    #Users (Faculty) to be removed from the group that are not in tenant anymore
    $teachersToRemove = ($teacherGrpMembers | ? {$_.ObjectId -ne $null}).objectid | Where {($AllUsers | ? {$_.ObjectId -ne $null}).objectid -NotContains $_}
    if ($teachersToRemove.Count > 0) {
        Foreach ($id in $teachersToRemove) {
            Remove-MsoLGroupMember -GroupObjectId $facultyid -GroupMemberType User -GroupmemberObjectId $id
        }
    }
}

if ((!$studentAdd) -and ($studentid -ne $null)) {
    #Users to be Added in the Student Group that are not present
    $studentGrpMembers = Get-MsolGroupMember -GroupObjectId $studentid
    $studentsToAdd = ($AllUsers | ? {$_.ObjectId -ne $null}).objectid | Where {($studentGrpMembers | ? {$_.ObjectId -ne $null}).objectid -NotContains $_}
    Foreach ($id in $studentsToAdd) {
        $GetUser = Get-AzureADUser -objectid $id
        $AssignedLicenses = ($GetUser | select -ExpandProperty assignedlicenses).skuid
        Foreach ($License in $AssignedLicenses) {

            #Adding student members to the security group
            If ($StudentSkuIDs -contains $License) {
                Add-MsolGroupMember -GroupObjectId $studentid -GroupMemberType User -GroupMemberObjectId $id
            }
        }
    }
    
    #Users (Students) to be removed the group that are not in tenant anymore
    $studentsToRemove = ($studentGrpMembers | ? {$_.ObjectId -ne $null}).objectid | Where {($AllUsers | ? {$_.ObjectId -ne $null}).objectid -NotContains $_}
    if ($studentsToRemove.Count > 0) {
        Foreach ($id in $studentsToRemove) {
            Remove-MsolGroupMember -GroupObjectId $studentid -GroupMemberType User -GroupmemberObjectId $id
        }
    }
}

Start-Transcript -Path "C:\results\log.txt"
if ($facultyid -ne $null) {
    $TeacherGroup = Get-MsolGroupMember -GroupObjectId $facultyid
    Write-Host -ForegroundColor Green "Teacher Group Count:" $TeacherGroup.Count
    Write-Host -ForegroundColor Green "Teacher Group Id:" $facultyid
}
else {
    $TeacherGroup = Get-MsolGroupMember -GroupObjectId $teachergroupid
    Write-Host -ForegroundColor Green "Teacher Group Count:" $TeacherGroup.Count
    Write-Host -ForegroundColor Green "Teacher Group Id:" $teachergroupid
}

if ($studentid -ne $null) {
    $StudentGroup = Get-MsolGroupMember -GroupObjectId $studentid
    Write-Host -ForegroundColor Green "Student Group Count:" $StudentGroup.Count
    Write-Host -ForegroundColor Green "Student Group Id:" $studentid
}
else {
    $StudentGroup = Get-MsolGroupMember -GroupObjectId $studentgroupid
    Write-Host -ForegroundColor Green "Student Group Count:" $StudentGroup.Count
    Write-Host -ForegroundColor Green "Student Group Id:" $studentgroupid
}
Stop-Transcript
```

## <a name="related-topics"></a><span data-ttu-id="7264c-122">См. также</span><span class="sxs-lookup"><span data-stu-id="7264c-122">Related topics</span></span>

[<span data-ttu-id="7264c-123">Назначение политик пользователям в Teams</span><span class="sxs-lookup"><span data-stu-id="7264c-123">Assign policies to your users in Teams</span></span>](../assign-policies.md)