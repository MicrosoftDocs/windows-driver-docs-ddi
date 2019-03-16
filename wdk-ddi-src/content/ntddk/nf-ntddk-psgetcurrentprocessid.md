---
UID: NF:ntddk.PsGetCurrentProcessId
title: PsGetCurrentProcessId function (ntddk.h)
description: The PsGetCurrentProcessId routine identifies the current thread's process.
old-location: kernel\psgetcurrentprocessid.htm
tech.root: kernel
ms.assetid: 9434f740-34c1-4244-813d-3fe9f1ead333
ms.date: 04/30/2018
ms.keywords: PsGetCurrentProcessId, PsGetCurrentProcessId routine [Kernel-Mode Driver Architecture], k108_e38b09ef-d948-4eb9-bfdd-24b25ba55034.xml, kernel.psgetcurrentprocessid, ntddk/PsGetCurrentProcessId
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
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- PsGetCurrentProcessId
product:
- Windows
targetos: Windows
req.typenames: 
---

# PsGetCurrentProcessId function


## -description


The <b>PsGetCurrentProcessId</b> routine identifies the current thread's process. 


## -parameters






## -returns



<b>PsGetCurrentProcessId</b> returns the process ID of the current thread's process. 




## -see-also




[IoGetCurrentProcess](https://msdn.microsoft.com/library/windows/hardware/ff549177)



[PsGetCurrentProcess](https://docs.microsoft.com/windows-hardware/drivers/kernel/mm-bad-pointer#psgetcurrentprocess)



[PsGetCurrentThread](https://msdn.microsoft.com/library/windows/hardware/ff559936)



[PsGetCurrentThreadId](https://msdn.microsoft.com/library/windows/hardware/ff559937)



[PsSetCreateProcessNotifyRoutine](https://msdn.microsoft.com/library/windows/hardware/ff559951)



[PsSetCreateThreadNotifyRoutine](https://msdn.microsoft.com/library/windows/hardware/ff559954)



[PsSetLoadImageNotifyRoutine](https://msdn.microsoft.com/library/windows/hardware/ff559957)
 

 

