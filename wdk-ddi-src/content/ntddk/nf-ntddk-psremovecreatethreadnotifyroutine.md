---
UID: NF:ntddk.PsRemoveCreateThreadNotifyRoutine
title: PsRemoveCreateThreadNotifyRoutine function (ntddk.h)
description: The PsRemoveCreateThreadNotifyRoutine routine removes a callback routine that was registered by the PsSetCreateThreadNotifyRoutine routine.
old-location: kernel\psremovecreatethreadnotifyroutine.htm
tech.root: kernel
ms.assetid: ef1fd29c-e0ef-4c08-ab3a-b1a3c694c06b
ms.date: 04/30/2018
keywords: ["PsRemoveCreateThreadNotifyRoutine function"]
ms.keywords: PsRemoveCreateThreadNotifyRoutine, PsRemoveCreateThreadNotifyRoutine routine [Kernel-Mode Driver Architecture], k108_cfa75911-6de3-4459-8093-855279e0a5f7.xml, kernel.psremovecreatethreadnotifyroutine, ntddk/PsRemoveCreateThreadNotifyRoutine
f1_keywords:
 - "ntddk/PsRemoveCreateThreadNotifyRoutine"
req.header: ntddk.h
req.include-header: Ntddk.h
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
req.irql: <=APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- PsRemoveCreateThreadNotifyRoutine
product:
- Windows
targetos: Windows
req.typenames: 
---

# PsRemoveCreateThreadNotifyRoutine function


## -description


The <b>PsRemoveCreateThreadNotifyRoutine</b> routine removes a callback routine that was registered by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pssetcreatethreadnotifyroutine">PsSetCreateThreadNotifyRoutine</a> routine.


## -parameters




### -param NotifyRoutine [in]

Pointer to the callback routine that the driver has previously registered through <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pssetcreatethreadnotifyroutine">PsSetCreateThreadNotifyRoutine</a>. 


## -returns



<b>PsRemoveCreateThreadNotifyRoutine</b> returns STATUS_SUCCESS if it  successfully removes the callback routine, or STATUS_PROCEDURE_NOT_FOUND if the value of <i>NotifyRoutine</i> does not match any registered callback routine.




## -remarks



If the driver's callback routine is currently running, <b>PsRemoveCreateThreadNotifyRoutine</b> waits until the callback routine exits before removing it. Therefore, the callback routine itself must not call <b>PsRemoveCreateThreadNotifyRoutine</b>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pssetcreatethreadnotifyroutine">PsSetCreateThreadNotifyRoutine</a>
 

 

