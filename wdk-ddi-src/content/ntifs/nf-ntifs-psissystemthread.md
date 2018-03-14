---
UID: NF:ntifs.PsIsSystemThread
title: PsIsSystemThread function
author: windows-driver-content
description: The PsIsSystemThread routine checks whether a given thread is a system thread.
old-location: kernel\psissystemthread.htm
old-project: kernel
ms.assetid: ecbea013-b876-4690-a455-ebe420a4f050
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: PsIsSystemThread, PsIsSystemThread routine [Kernel-Mode Driver Architecture], k108_eacaf1ad-4ab8-49a6-9d43-3aba7821e110.xml, kernel.psissystemthread, ntifs/PsIsSystemThread
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and later versions of Windows.
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	PsIsSystemThread
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# PsIsSystemThread function


## -description


The <b>PsIsSystemThread</b> routine checks whether a given thread is a system thread.


## -syntax


````
BOOLEAN PsIsSystemThread(
  _In_ PETHREAD Thread
);
````


## -parameters




### -param Thread [in]

Pointer to the thread to be checked. 


## -returns



<b>PsIsSystemThread</b> returns <b>TRUE</b> if the specified thread is a system thread, <b>FALSE</b> otherwise.




## -remarks



For more information about using system threads and managing synchronization within a nonarbitrary thread context, see <a href="https://msdn.microsoft.com/fbd8aadd-5a24-48c9-9865-80cc7dc97316">Driver Threads, Dispatcher Objects, and Resources</a>. 




## -see-also

<a href="..\wdm\nf-wdm-psgetcurrentthread.md">PsGetCurrentThread</a>



<a href="..\ntifs\nf-ntifs-ioissystemthread.md">IoIsSystemThread</a>



 

 


