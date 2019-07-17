---
UID: NF:ntifs.SePrivilegeCheck
title: SePrivilegeCheck function (ntifs.h)
description: The SePrivilegeCheck routine determines whether a specified set of privileges is enabled in the subject's access token.
old-location: ifsk\seprivilegecheck.htm
tech.root: ifsk
ms.assetid: 707ced39-4153-4a6e-b87d-7e4eb487e738
ms.date: 04/16/2018
ms.keywords: SePrivilegeCheck, SePrivilegeCheck routine [Installable File System Drivers], ifsk.seprivilegecheck, ntifs/SePrivilegeCheck, seref_45aa3a8c-26b9-4bb9-968a-5f7d4a12ca3a.xml
ms.topic: function
f1_keywords:
 - "ntifs/SePrivilegeCheck"
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- SePrivilegeCheck
product:
- Windows
targetos: Windows
req.typenames: 
---

# SePrivilegeCheck function


## -description


The <b>SePrivilegeCheck</b> routine determines whether a specified set of privileges is enabled in the subject's access token. 


## -parameters




### -param RequiredPrivileges [in, out]

Pointer to a PRIVILEGE_SET structure. The <b>Privilege</b> member of this structure is an array of LUID_AND_ATTRIBUTES structures. Before calling <b>SePrivilegeCheck</b>, use the <b>Privilege</b> array to indicate the set of privileges to check. Set the <b>Control</b> member to PRIVILEGE_SET_ALL_NECESSARY if all of the privileges must be enabled; or set it to zero if it is sufficient that any one of the privileges be enabled. 

When <b>SePrivilegeCheck</b> returns, the <b>Attributes</b> member of each LUID_AND_ATTRIBUTES structure is set to SE_PRIVILEGE_USED_FOR_ACCESS if the corresponding privilege is enabled. 


### -param SubjectSecurityContext [in]

Pointer to the subject's captured security context.


### -param AccessMode [in]

The access mode to use for the privilege check. Either <b>UserMode</b> or <b>KernelMode</b>. If <i>AccessMode</i> is set to <b>KernelMode</b>, then all privileges are marked as being possessed by the subject, and <b>SePrivilegeCheck</b> returns <b>TRUE</b>.


## -returns



<b>SePrivilegeCheck</b> returns <b>TRUE</b> if all specified privileges are held by the subject, <b>FALSE</b> otherwise.




## -remarks



An access token contains a list of the privileges held by the account associated with the token. These privileges can be enabled or disabled; most are disabled by default. <b>SePrivilegeCheck</b> checks only for enabled privileges. To get a list of all the enabled and disabled privileges held by an access token, call <b>SeQueryInformationToken</b>. 

For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_luid_and_attributes">LUID_AND_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff551860(v=vs.85)">PRIVILEGE_SET</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">SECURITY_SUBJECT_CONTEXT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-seaccesscheck">SeAccessCheck</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-seappendprivileges">SeAppendPrivileges</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-sefreeprivileges">SeFreePrivileges</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-sequeryinformationtoken">SeQueryInformationToken</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nf-ntddk-sesingleprivilegecheck">SeSinglePrivilegeCheck</a>
 

 

