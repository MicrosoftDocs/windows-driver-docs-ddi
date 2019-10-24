---
UID: NF:ntddk.PsGetCurrentThreadId
title: PsGetCurrentThreadId function (ntddk.h)
description: The PsGetCurrentThreadId routine identifies the current thread.
old-location: kernel\psgetcurrentthreadid.htm
tech.root: kernel
ms.assetid: c4da1dcb-435d-4e32-8114-3b0ae4352000
ms.date: 04/30/2018
ms.keywords: PsGetCurrentThreadId, PsGetCurrentThreadId routine [Kernel-Mode Driver Architecture], k108_eae0d8bf-f2fe-49dd-b3b7-6da9114f844a.xml, kernel.psgetcurrentthreadid, ntddk/PsGetCurrentThreadId
ms.topic: function
f1_keywords:
 - "ntddk/PsGetCurrentThreadId"
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
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- PsGetCurrentThreadId
product:
- Windows
targetos: Windows
req.typenames: 
---

# PsGetCurrentThreadId function


## -description


The <b>PsGetCurrentThreadId</b> routine identifies the current thread. 


## -parameters






## -returns



The <b>PsGetCurrentThreadId</b> routine returns the thread ID of the current thread. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kegetcurrentthread">KeGetCurrentThread</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-psgetcurrentprocessid">PsGetCurrentProcessId</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-psgetcurrentthread">PsGetCurrentThread</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pssetcreatethreadnotifyroutine">PsSetCreateThreadNotifyRoutine</a>
 

 

