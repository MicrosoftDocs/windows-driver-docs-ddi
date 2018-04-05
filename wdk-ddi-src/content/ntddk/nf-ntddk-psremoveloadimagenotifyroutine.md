---
UID: NF:ntddk.PsRemoveLoadImageNotifyRoutine
title: PsRemoveLoadImageNotifyRoutine function
author: windows-driver-content
description: The PsRemoveLoadImageNotifyRoutine routine removes a callback routine that was registered by the PsSetLoadImageNotifyRoutine routine.
old-location: kernel\psremoveloadimagenotifyroutine.htm
old-project: kernel
ms.assetid: 5491f9fb-8f87-41ed-9629-18318554ad90
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: PsRemoveLoadImageNotifyRoutine, PsRemoveLoadImageNotifyRoutine routine [Kernel-Mode Driver Architecture], k108_50aeae5b-9276-4e93-8192-70a51bd87ab4.xml, kernel.psremoveloadimagenotifyroutine, ntddk/PsRemoveLoadImageNotifyRoutine
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<=APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	PsRemoveLoadImageNotifyRoutine
product:
- Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# PsRemoveLoadImageNotifyRoutine function


## -description


The <b>PsRemoveLoadImageNotifyRoutine</b> routine removes a callback routine that was registered by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559957">PsSetLoadImageNotifyRoutine</a> routine. 


## -parameters




### -param NotifyRoutine [in]

Pointer to the callback routine that the driver has previously registered through <a href="https://msdn.microsoft.com/library/windows/hardware/ff559957">PsSetLoadImageNotifyRoutine</a>. 


## -returns



<b>PsRemoveLoadImageNotifyRoutine</b> returns STATUS_SUCCESS if it successfully removes the callback routine, or STATUS_PROCEDURE_NOT_FOUND if the value of <i>NotifyRoutine</i> does not match any registered callback routine.




## -remarks



If the driver's callback routine is currently running, <b>PsRemoveLoadImageNotifyRoutine</b> waits until the callback routine exits before removing it. Therefore, the callback routine itself must not call <b>PsRemoveLoadImageNotifyRoutine</b>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff559957">PsSetLoadImageNotifyRoutine</a>
 

 

