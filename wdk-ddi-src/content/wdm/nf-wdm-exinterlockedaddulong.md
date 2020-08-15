---
UID: NF:wdm.ExInterlockedAddUlong
title: ExInterlockedAddUlong function (wdm.h)
description: The ExInterlockedAddUlong routine adds an unsigned long value to a given unsigned integer as an atomic operation.
old-location: kernel\exinterlockedaddulong.htm
tech.root: kernel
ms.assetid: c418538a-4041-4ea8-8a4c-1f4d35e434c7
ms.date: 04/30/2018
keywords: ["ExInterlockedAddUlong function"]
ms.keywords: ExInterlockedAddUlong, ExInterlockedAddUlong routine [Kernel-Mode Driver Architecture], k102_bec4a58e-ee68-4f9e-8fac-9ef0c193ef10.xml, kernel.exinterlockedaddulong, wdm/ExInterlockedAddUlong
f1_keywords:
 - "wdm/ExInterlockedAddUlong"
 - "ExInterlockedAddUlong"
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
req.irql: Any level (see Remarks section)
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- ExInterlockedAddUlong
targetos: Windows
req.typenames: 
---

# ExInterlockedAddUlong function


## -description


The <b>ExInterlockedAddUlong</b> routine adds an unsigned long value to a given unsigned integer as an atomic operation.


## -parameters




### -param Addend 
[in, out]
A pointer to an unsigned long integer whose value is to be adjusted by the <i>Increment</i> value.


### -param Increment 
[in]
Specifies an unsigned long integer to be added. 


### -param Lock 
[in, out]
A pointer to a spin lock to be used to synchronize access to the <i>Addend</i>. 


## -returns



<b>ExInterlockedAddUlong </b>returns the original (unsummed) value of the <i>Addend</i>. 




## -remarks



Consider using <b>InterlockedExchangeAdd</b> instead of this routine. <b>InterlockedExchangeAdd</b> can be more efficient because it does not use a spin lock and it is inlined by the compiler.

Support routines that do interlocked operations are assumed to be incapable of causing a page fault. That is, neither their code nor any of the data they touch can cause a page fault without bringing down the system. They use spin locks to achieve atomicity on symmetric multiprocessor machines. The caller must provide resident storage for the <i>Lock</i>, which must be initialized with <b>KeInitializeSpinLock</b> before the initial call to an <b>ExInterlocked<i>Xxx</i></b>.

The <i>Lock</i> passed to <b>ExInterlockedAddULong</b> is used to assure that the add operation on <i>Addend</i> is atomic with respect to any other operations on the same value which synchronize with this same spin lock. 

<b>ExInterlockedAddUlong</b> masks interrupts. Consequently, it can be used for synchronization between an ISR and other driver code, provided that the same <i>Lock</i> is never reused in a call to a routine that runs at IRQL = DISPATCH_LEVEL.

Note that calls to <b>Interlocked<i>Xxx</i></b> are guaranteed to be atomic with respect to other <b>Interlocked<i>Xxx</i></b> calls without caller-supplied spin locks.

Callers of <b>ExInterlockedAddUlong</b> run at any IRQL. The storage for the <i>Addend</i> parameter must be resident at all IRQLs.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545335">ExInterlockedAddLargeInteger</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-interlockeddecrement">InterlockedDecrement</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-interlockedincrement">InterlockedIncrement</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keinitializespinlock">KeInitializeSpinLock</a>
 

 

