---
UID: NF:wdm.KeInitializeDpc
title: KeInitializeDpc function
author: windows-driver-content
description: The KeInitializeDpc routine initializes a DPC object, and registers a CustomDpc routine for that object.
old-location: kernel\keinitializedpc.htm
old-project: kernel
ms.assetid: 5dd82086-d39c-4ebc-9e2a-73ef504f873c
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: KeInitializeDpc, KeInitializeDpc routine [Kernel-Mode Driver Architecture], k105_069c115c-3a05-442e-8fc4-56dcb635a473.xml, kernel.keinitializedpc, wdm/KeInitializeDpc
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	KeInitializeDpc
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# KeInitializeDpc function


## -description


The <b>KeInitializeDpc</b> routine initializes a DPC object, and registers a <a href="https://msdn.microsoft.com/library/windows/hardware/ff542972">CustomDpc</a> routine for that object.


## -syntax


````
VOID KeInitializeDpc(
  _Out_    PRKDPC             Dpc,
  _In_     PKDEFERRED_ROUTINE DeferredRoutine,
  _In_opt_ PVOID              DeferredContext
);
````


## -parameters




### -param Dpc [out]

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551882">KDPC</a> structure that represents the DPC object to initialize. The caller must allocate storage for the structure from resident memory.


### -param DeferredRoutine [in]

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff542972">CustomDpc</a> routine to associate with the DPC.


### -param DeferredContext [in, optional]

Specifies the value to pass as the <i>DeferredContext</i> parameter to <a href="https://msdn.microsoft.com/library/windows/hardware/ff542972">CustomDpc</a>. 


## -returns



None




## -remarks



The caller can queue an initialized DPC with <a href="..\wdm\nf-wdm-keinsertqueuedpc.md">KeInsertQueueDpc</a>. The caller also can set up a timer object associated with the initialized DPC object and queue the DPC with <a href="..\wdm\nf-wdm-kesettimer.md">KeSetTimer</a>.

Storage for the DPC object must be resident: in the device extension of a driver-created device object, in the controller extension of a driver-created controller object, or in nonpaged pool allocated by the caller.




## -see-also

<a href="..\wdm\nf-wdm-keremovequeuedpc.md">KeRemoveQueueDpc</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542972">CustomDpc</a>



<a href="..\wdm\nf-wdm-keinsertqueuedpc.md">KeInsertQueueDpc</a>



<a href="..\wdm\nf-wdm-kesettimer.md">KeSetTimer</a>



 

 


