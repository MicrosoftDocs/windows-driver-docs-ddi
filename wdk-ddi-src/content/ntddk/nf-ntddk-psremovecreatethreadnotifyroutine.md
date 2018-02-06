---
UID: NF:ntddk.PsRemoveCreateThreadNotifyRoutine
title: PsRemoveCreateThreadNotifyRoutine function
author: windows-driver-content
description: The PsRemoveCreateThreadNotifyRoutine routine removes a callback routine that was registered by the PsSetCreateThreadNotifyRoutine routine.
old-location: kernel\psremovecreatethreadnotifyroutine.htm
old-project: kernel
ms.assetid: ef1fd29c-e0ef-4c08-ab3a-b1a3c694c06b
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: PsRemoveCreateThreadNotifyRoutine, ntddk/PsRemoveCreateThreadNotifyRoutine, kernel.psremovecreatethreadnotifyroutine, PsRemoveCreateThreadNotifyRoutine routine [Kernel-Mode Driver Architecture], k108_cfa75911-6de3-4459-8093-855279e0a5f7.xml
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
req.ddi-compliance: 
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
-	PsRemoveCreateThreadNotifyRoutine
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# PsRemoveCreateThreadNotifyRoutine function


## -description


The <b>PsRemoveCreateThreadNotifyRoutine</b> routine removes a callback routine that was registered by the <a href="..\ntddk\nf-ntddk-pssetcreatethreadnotifyroutine.md">PsSetCreateThreadNotifyRoutine</a> routine.


## -syntax


````
NTSTATUS PsRemoveCreateThreadNotifyRoutine(
  _In_ PCREATE_THREAD_NOTIFY_ROUTINE NotifyRoutine
);
````


## -parameters




### -param NotifyRoutine [in]

Pointer to the callback routine that the driver has previously registered through <a href="..\ntddk\nf-ntddk-pssetcreatethreadnotifyroutine.md">PsSetCreateThreadNotifyRoutine</a>. 


## -returns


<b>PsRemoveCreateThreadNotifyRoutine</b> returns STATUS_SUCCESS if it  successfully removes the callback routine, or STATUS_PROCEDURE_NOT_FOUND if the value of <i>NotifyRoutine</i> does not match any registered callback routine.



## -remarks


If the driver's callback routine is currently running, <b>PsRemoveCreateThreadNotifyRoutine</b> waits until the callback routine exits before removing it. Therefore, the callback routine itself must not call <b>PsRemoveCreateThreadNotifyRoutine</b>. 



## -see-also

<a href="..\ntddk\nf-ntddk-pssetcreatethreadnotifyroutine.md">PsSetCreateThreadNotifyRoutine</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PsRemoveCreateThreadNotifyRoutine routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

