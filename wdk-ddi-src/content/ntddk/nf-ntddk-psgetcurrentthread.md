---
UID: NF:ntddk.PsGetCurrentThread
title: PsGetCurrentThread function
author: windows-driver-content
description: The PsGetCurrentThread routine identifies the current thread.
old-location: kernel\psgetcurrentthread.htm
old-project: kernel
ms.assetid: 132b30fe-21ef-48dc-8c69-02ccac563b87
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: ExGetCurrentResourceThread, PsGetCurrentThread, PsGetCurrentThread routine [Kernel-Mode Driver Architecture], k108_75fb6f47-8a13-4f2c-9b94-a8b7125bbcb6.xml, kernel.psgetcurrentthread, wdm/PsGetCurrentThread
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	PsGetCurrentThread
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
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

<a href="..\ntddk\nf-ntddk-psgetcurrentprocessid.md">PsGetCurrentProcessId</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559933">PsGetCurrentProcess</a>



<a href="..\wdm\nf-wdm-kegetcurrentthread.md">KeGetCurrentThread</a>



<a href="..\ntifs\nf-ntifs-psissystemthread.md">PsIsSystemThread</a>



<a href="..\wdm\nf-wdm-pscreatesystemthread.md">PsCreateSystemThread</a>



 

 


