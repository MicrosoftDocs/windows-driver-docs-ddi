---
UID: NF:ntddk.RtlRunOnceExecuteOnce
title: RtlRunOnceExecuteOnce function (ntddk.h)
description: The RtlRunOnceExecuteOnce performs a one-time initialization.
old-location: kernel\rtlrunonceexecuteonce.htm
tech.root: kernel
ms.assetid: 2769eb2c-33e2-4e3f-a1bf-1ebc9213b224
ms.date: 04/30/2018
ms.keywords: RtlRunOnceExecuteOnce, RtlRunOnceExecuteOnce function [Kernel-Mode Driver Architecture], k109_c1729bff-038f-4714-b422-1b97dd5a9c19.xml, kernel.rtlrunonceexecuteonce, ntddk/RtlRunOnceExecuteOnce
ms.topic: function
f1_keywords:
 - "ntddk/RtlRunOnceExecuteOnce"
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Vista.
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
req.irql: <= APC_LEVEL (See Remarks section.)
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- RtlRunOnceExecuteOnce
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlRunOnceExecuteOnce function


## -description


The <b>RtlRunOnceExecuteOnce</b> performs a one-time initialization.


## -syntax

```cpp
NTSYSAPI NTSTATUS RtlRunOnceExecuteOnce(
  PRTL_RUN_ONCE         RunOnce,
  PRTL_RUN_ONCE_INIT_FN InitFn,
  PVOID                 *Parameter,
  PVOID                 Context
);
```

## -parameters




### -param RunOnce [in, out]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">RTL_RUN_ONCE</a> one-time initialization structure.


### -param InitFn [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nc-ntddk-rtl_run_once_init_fn">RunOnceInitialization</a> routine.

### -param Parameter [in, out]

The value to pass as the <i>Parameter</i> parameter to the <i>RunOnceInitialization</i> routine.

### -param Context [out]

A pointer to a PVOID variable that receives the initialized data.



## -returns



<b>RtlRunOnceExecuteOnce</b> returns STATUS_SUCCESS if the operation succeeds, or the appropriate NTSTATUS error code if the operation fails.




## -remarks



For the first call to <b>RtlRunOnceExecuteOnce</b> for a particular <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">RTL_RUN_ONCE</a> structure, <b>RtlRunOnceExecuteOnce</b> calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nc-ntddk-rtl_run_once_init_fn">RunOnceInitialization</a> routine to initialize the data. Every subsequent call to <b>RtlRunOnceExecuteOnce</b> for that structure supplies the same initialized data. The <i>RunOnceInitialization</i> routine will not be called twice for the same <b>RTL_RUN_ONCE</b> structure.

<b>RtlRunOnceExecuteOnce</b> runs with normal kernel APCs disabled. The routine should not be called within a special kernel APC unless all calls occur at APC_LEVEL.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">RTL_RUN_ONCE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nf-ntddk-rtlrunoncebegininitialize">RtlRunOnceBeginInitialize</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nf-ntddk-rtlrunoncecomplete">RtlRunOnceComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nf-ntddk-rtlrunonceinitialize">RtlRunOnceInitialize</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nc-ntddk-rtl_run_once_init_fn">RunOnceInitialization</a>
 

 

