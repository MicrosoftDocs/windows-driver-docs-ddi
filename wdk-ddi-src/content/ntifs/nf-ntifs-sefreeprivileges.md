---
UID: NF:ntifs.SeFreePrivileges
title: SeFreePrivileges function
author: windows-driver-content
description: The SeFreePrivileges routine frees a privilege set returned by SeAccessCheck.
old-location: kernel\sefreeprivileges.htm
old-project: kernel
ms.assetid: 5b8ba64e-3147-45b4-9861-da2186c2ba10
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: SeFreePrivileges, SeFreePrivileges routine [Kernel-Mode Driver Architecture], kernel.sefreeprivileges, ntifs/SeFreePrivileges, seref_e40724d7-f170-4dbd-89a6-2cdcdd13e87d.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	SeFreePrivileges
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# SeFreePrivileges function


## -description


The <b>SeFreePrivileges</b> routine frees a privilege set returned by <b>SeAccessCheck</b>.


## -syntax


````
VOID SeFreePrivileges(
  _In_ PPRIVILEGE_SET Privileges
);
````


## -parameters




### -param Privileges [in]

Pointer to the privilege set to be freed.


## -returns



None




## -remarks



For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK. 




## -see-also

<a href="..\wdm\nf-wdm-seaccesscheck.md">SeAccessCheck</a>



<a href="..\wdm\ns-wdm-_privilege_set.md">PRIVILEGE_SET</a>



<a href="..\ntifs\nf-ntifs-seappendprivileges.md">SeAppendPrivileges</a>



<a href="..\ntifs\nf-ntifs-seprivilegecheck.md">SePrivilegeCheck</a>



 

 


