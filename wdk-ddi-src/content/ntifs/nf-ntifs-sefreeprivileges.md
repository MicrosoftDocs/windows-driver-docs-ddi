---
UID: NF:ntifs.SeFreePrivileges
title: SeFreePrivileges function
author: windows-driver-content
description: The SeFreePrivileges routine frees a privilege set returned by SeAccessCheck.
old-location: kernel\sefreeprivileges.htm
old-project: kernel
ms.assetid: 5b8ba64e-3147-45b4-9861-da2186c2ba10
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: SeFreePrivileges, SeFreePrivileges routine [Kernel-Mode Driver Architecture], seref_e40724d7-f170-4dbd-89a6-2cdcdd13e87d.xml, kernel.sefreeprivileges, ntifs/SeFreePrivileges
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
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

<a href="..\ntifs\nf-ntifs-seprivilegecheck.md">SePrivilegeCheck</a>

<a href="..\wdm\nf-wdm-seaccesscheck.md">SeAccessCheck</a>

<a href="..\wdm\ns-wdm-_privilege_set.md">PRIVILEGE_SET</a>

<a href="..\ntifs\nf-ntifs-seappendprivileges.md">SeAppendPrivileges</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20SeFreePrivileges routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

