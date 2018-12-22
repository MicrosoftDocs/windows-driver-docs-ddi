---
UID: NF:wdm.KeInitializeDpc
title: KeInitializeDpc function
description: The KeInitializeDpc routine initializes a DPC object, and registers a CustomDpc routine for that object.
old-location: kernel\keinitializedpc.htm
tech.root: kernel
ms.assetid: 5dd82086-d39c-4ebc-9e2a-73ef504f873c
ms.date: 04/30/2018
ms.keywords: KeInitializeDpc, KeInitializeDpc routine [Kernel-Mode Driver Architecture], k105_069c115c-3a05-442e-8fc4-56dcb635a473.xml, kernel.keinitializedpc, wdm/KeInitializeDpc
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
product:
- Windows
targetos: Windows
req.typenames: 
---

# KeInitializeDpc function


## -description


The <b>KeInitializeDpc</b> routine initializes a DPC object, and registers a <a href="https://msdn.microsoft.com/library/windows/hardware/ff542972">CustomDpc</a> routine for that object.


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



The caller can queue an initialized DPC with <a href="https://msdn.microsoft.com/library/windows/hardware/ff552185">KeInsertQueueDpc</a>. The caller also can set up a timer object associated with the initialized DPC object and queue the DPC with <a href="https://msdn.microsoft.com/library/windows/hardware/ff553286">KeSetTimer</a>.

Storage for the DPC object must be resident: in the device extension of a driver-created device object, in the controller extension of a driver-created controller object, or in nonpaged pool allocated by the caller.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff542972">CustomDpc</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552185">KeInsertQueueDpc</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553169">KeRemoveQueueDpc</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553286">KeSetTimer</a>
 

 

