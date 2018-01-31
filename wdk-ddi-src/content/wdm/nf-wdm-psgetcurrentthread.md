---
UID: NF:wdm.PsGetCurrentThread
title: PsGetCurrentThread function
author: windows-driver-content
description: The PsGetCurrentThread routine identifies the current thread.
old-location: kernel\psgetcurrentthread.htm
old-project: kernel
ms.assetid: 132b30fe-21ef-48dc-8c69-02ccac563b87
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: k108_75fb6f47-8a13-4f2c-9b94-a8b7125bbcb6.xml, PsGetCurrentThread routine [Kernel-Mode Driver Architecture], wdm/PsGetCurrentThread, ExGetCurrentResourceThread, kernel.psgetcurrentthread, PsGetCurrentThread
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.irql: Any level
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	PsGetCurrentThread
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# PsGetCurrentThread function


## -description


The <b>PsGetCurrentThread</b> routine identifies the current thread. 


## -syntax


````
PETHREAD PsGetCurrentThread(void);
````


## -parameters





## -returns


<b>PsGetCurrentThread</b> returns a pointer to the executive thread object that represents the currently executing thread. 



## -remarks


This macro 



## -see-also

<a href="..\ntifs\nf-ntifs-psissystemthread.md">PsIsSystemThread</a>

<a href="..\wdm\nf-wdm-pscreatesystemthread.md">PsCreateSystemThread</a>

<a href="..\ntddk\nf-ntddk-psgetcurrentprocessid.md">PsGetCurrentProcessId</a>

<a href="..\wdm\nf-wdm-kegetcurrentthread.md">KeGetCurrentThread</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff559933">PsGetCurrentProcess</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PsGetCurrentThread routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

