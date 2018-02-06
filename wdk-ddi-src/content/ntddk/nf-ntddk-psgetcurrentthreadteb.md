---
UID: NF:ntddk.PsGetCurrentThreadTeb
title: PsGetCurrentThreadTeb function
author: windows-driver-content
description: The PsGetCurrentThreadTeb routine returns the Thread Environment Block (TEB) of the current thread. The call must be made in kernel-mode.
old-location: kernel\psgetcurrentthreadteb.htm
old-project: kernel
ms.assetid: 822B75D4-A825-4BB1-8265-A1389F4982C7
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: PsGetCurrentThreadTeb routine [Kernel-Mode Driver Architecture], ntddk/PsGetCurrentThreadTeb, PsGetCurrentThreadTeb, kernel.psgetcurrentthreadteb
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	PsGetCurrentThreadTeb
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# PsGetCurrentThreadTeb function


## -description


The <b>PsGetCurrentThreadTeb</b> routine returns the Thread Environment Block (TEB) of the current thread. The call must be made in kernel-mode.


## -syntax


````
PVOID  PsGetCurrentThreadTeb(
   void 
);
````


## -parameters








## -returns


A pointer to the thread environment block of the current thread. The TEB should be accessed within a try/catch exception block. 



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff559917">Process and Thread Manager Routines</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PsGetCurrentThreadTeb routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

