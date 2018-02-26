---
UID: NF:wdm.IoGetInitialStack
title: IoGetInitialStack function
author: windows-driver-content
description: The IoGetInitialStack routine returns the base address of the current thread's stack.
old-location: kernel\iogetinitialstack.htm
old-project: kernel
ms.assetid: 0d0d793f-c2c1-48ff-9e7f-ef2697255bfa
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , G, I, IoGetInitialStack, IoGetInitialStack routine [Kernel-Mode Driver Architecture], S, a, c, e, i, k, k104_5e1ac4e5-b51e-4840-86e3-2ce67c634489.xml, kernel.iogetinitialstack, l, n, o, t, wdm/IoGetInitialStack"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlIoApcLte, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<=APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	IoGetInitialStack
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoGetInitialStack function


## -description


The <b>IoGetInitialStack</b> routine returns the base address of the current thread's stack.


## -syntax


````
PVOID IoGetInitialStack(void);
````


## -parameters






## -returns



<b>IoGetInitialStack</b> returns the initial base address of the current thread's stack. 




## -remarks



Highest-level drivers can call this routine, particularly file systems attempting to determine whether they've been passed a pointer to a location on the current thread's stack. 




## -see-also

<a href="..\wdm\nf-wdm-iogetstacklimits.md">IoGetStackLimits</a>



<a href="..\wdm\nf-wdm-iogetremainingstacksize.md">IoGetRemainingStackSize</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoGetInitialStack routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

