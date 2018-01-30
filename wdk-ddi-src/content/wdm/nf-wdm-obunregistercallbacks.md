---
UID: NF:wdm.ObUnRegisterCallbacks
title: ObUnRegisterCallbacks function
author: windows-driver-content
description: The ObUnRegisterCallbacks routine unregisters a set of callback routines that were registered with the ObRegisterCallbacks routine.
old-location: kernel\obunregistercallbacks.htm
old-project: kernel
ms.assetid: 01121323-da0c-4ae9-b0c0-f6302583237c
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.obunregistercallbacks, k107_f0c1fdd0-3dcc-466c-a7a1-fab0b38e4e88.xml, wdm/ObUnRegisterCallbacks, ObUnRegisterCallbacks routine [Kernel-Mode Driver Architecture], ObUnRegisterCallbacks
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista with Service Pack 1 (SP1), Windows Server 2008, and later versions of the Windows operating system.
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
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	ObUnRegisterCallbacks
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ObUnRegisterCallbacks function


## -description


The <b>ObUnRegisterCallbacks</b> routine unregisters a set of callback routines that were registered with the <a href="..\wdm\nf-wdm-obregistercallbacks.md">ObRegisterCallbacks</a> routine.


## -syntax


````
VOID ObUnRegisterCallbacks(
  _In_ PVOID RegistrationHandle
);
````


## -parameters




### -param RegistrationHandle [in]

A value that identifies the set of callback routines to unregister. The <a href="..\wdm\nf-wdm-obregistercallbacks.md">ObRegisterCallbacks</a> routine provides this value when it originally registered the callback routines.


## -returns


None



## -remarks


A driver that calls the <b>ObRegisterCallbacks</b> routine must call the <b>ObUnRegisterCallbacks</b> routine before the driver is unloaded.



## -see-also

<a href="..\wdm\nf-wdm-obregistercallbacks.md">ObRegisterCallbacks</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ObUnRegisterCallbacks routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

