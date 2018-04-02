---
UID: NF:ntddk.PsGetCurrentThreadId
title: PsGetCurrentThreadId function
author: windows-driver-content
description: The PsGetCurrentThreadId routine identifies the current thread.
old-location: kernel\psgetcurrentthreadid.htm
old-project: kernel
ms.assetid: c4da1dcb-435d-4e32-8114-3b0ae4352000
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: PsGetCurrentThreadId, PsGetCurrentThreadId routine [Kernel-Mode Driver Architecture], k108_eae0d8bf-f2fe-49dd-b3b7-6da9114f844a.xml, kernel.psgetcurrentthreadid, ntddk/PsGetCurrentThreadId
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h
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
-	PsGetCurrentThreadId
product:
- Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# PsGetCurrentThreadId function


## -description


The <b>PsGetCurrentThreadId</b> routine identifies the current thread. 


## -parameters






## -returns



The <b>PsGetCurrentThreadId</b> routine returns the thread ID of the current thread. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552084">KeGetCurrentThread</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559935">PsGetCurrentProcessId</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559936">PsGetCurrentThread</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559954">PsSetCreateThreadNotifyRoutine</a>
 

 

