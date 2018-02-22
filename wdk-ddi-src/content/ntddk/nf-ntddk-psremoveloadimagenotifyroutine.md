---
UID: NF:ntddk.PsRemoveLoadImageNotifyRoutine
title: PsRemoveLoadImageNotifyRoutine function
author: windows-driver-content
description: The PsRemoveLoadImageNotifyRoutine routine removes a callback routine that was registered by the PsSetLoadImageNotifyRoutine routine.
old-location: kernel\psremoveloadimagenotifyroutine.htm
old-project: kernel
ms.assetid: 5491f9fb-8f87-41ed-9629-18318554ad90
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: kernel.psremoveloadimagenotifyroutine, k108_50aeae5b-9276-4e93-8192-70a51bd87ab4.xml, ntddk/PsRemoveLoadImageNotifyRoutine, PsRemoveLoadImageNotifyRoutine routine [Kernel-Mode Driver Architecture], PsRemoveLoadImageNotifyRoutine
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	PsRemoveLoadImageNotifyRoutine
product: Windows
targetos: Windows
req.typenames: "*PWHEA_RAW_DATA_FORMAT, WHEA_RAW_DATA_FORMAT"
---

# PsRemoveLoadImageNotifyRoutine function


## -description


The <b>PsRemoveLoadImageNotifyRoutine</b> routine removes a callback routine that was registered by the <a href="..\ntddk\nf-ntddk-pssetloadimagenotifyroutine.md">PsSetLoadImageNotifyRoutine</a> routine. 


## -syntax


````
NTSTATUS PsRemoveLoadImageNotifyRoutine(
  _In_ PLOAD_IMAGE_NOTIFY_ROUTINE NotifyRoutine
);
````


## -parameters




### -param NotifyRoutine [in]

Pointer to the callback routine that the driver has previously registered through <a href="..\ntddk\nf-ntddk-pssetloadimagenotifyroutine.md">PsSetLoadImageNotifyRoutine</a>. 


## -returns



<b>PsRemoveLoadImageNotifyRoutine</b> returns STATUS_SUCCESS if it successfully removes the callback routine, or STATUS_PROCEDURE_NOT_FOUND if the value of <i>NotifyRoutine</i> does not match any registered callback routine.




## -remarks



If the driver's callback routine is currently running, <b>PsRemoveLoadImageNotifyRoutine</b> waits until the callback routine exits before removing it. Therefore, the callback routine itself must not call <b>PsRemoveLoadImageNotifyRoutine</b>. 




## -see-also

<a href="..\ntddk\nf-ntddk-pssetloadimagenotifyroutine.md">PsSetLoadImageNotifyRoutine</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PsRemoveLoadImageNotifyRoutine routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

