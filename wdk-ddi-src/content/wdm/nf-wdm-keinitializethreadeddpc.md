---
UID: NF:wdm.KeInitializeThreadedDpc
title: KeInitializeThreadedDpc function (wdm.h)
description: The KeInitializeThreadedDpc routine initializes a threaded DPC object, and registers a CustomThreadedDpc routine for that object.
old-location: kernel\keinitializethreadeddpc.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["KeInitializeThreadedDpc function"]
ms.keywords: KeInitializeThreadedDpc, KeInitializeThreadedDpc routine [Kernel-Mode Driver Architecture], k105_b5df057f-6d75-4a06-ac5f-d99340bdbb21.xml, kernel.keinitializethreadeddpc, wdm/KeInitializeThreadedDpc
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of Windows.
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
targetos: Windows
req.typenames: 
f1_keywords:
 - KeInitializeThreadedDpc
 - wdm/KeInitializeThreadedDpc
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - KeInitializeThreadedDpc
---

# KeInitializeThreadedDpc function


## -description

The <b>KeInitializeThreadedDpc</b> routine initializes a threaded DPC object, and registers a <a href="https://msdn.microsoft.com/library/windows/hardware/ff542976">CustomThreadedDpc</a> routine for that object.

## -parameters

### -param Dpc 

[out]
Pointer to a <a href="/windows-hardware/drivers/kernel/eprocess">KDPC</a> structure that represents the DPC object to initialize. The caller must allocate storage for the structure from resident memory.

### -param DeferredRoutine 

[in]
Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff542976">CustomThreadedDpc</a> routine to associate with the DPC.

### -param DeferredContext 

[in, optional]
Specifies the value to pass as the <i>DeferredContext</i> parameter to <a href="https://msdn.microsoft.com/library/windows/hardware/ff542976">CustomThreadedDpc</a>.

## -remarks

For more information about threaded DPCs, see <a href="/windows-hardware/drivers/kernel/introduction-to-threaded-dpcs">Introduction to Threaded DPCs</a>.

## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff542976">CustomThreadedDpc</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-keinsertqueuedpc">KeInsertQueueDpc</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-keremovequeuedpc">KeRemoveQueueDpc</a>
