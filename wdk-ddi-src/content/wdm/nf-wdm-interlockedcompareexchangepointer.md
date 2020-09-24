---
UID: NF:wdm.InterlockedCompareExchangePointer
title: InterlockedCompareExchangePointer function (wdm.h)
description: The InterlockedCompareExchangePointer routine performs an atomic operation that compares the input pointer value pointed to by Destination with the pointer value Comperand.
old-location: kernel\interlockedcompareexchangepointer.htm
tech.root: kernel
ms.assetid: 3b96076f-a7f7-4705-bbee-595ee4d9f789
ms.date: 04/30/2018
keywords: ["InterlockedCompareExchangePointer function"]
ms.keywords: InterlockedCompareExchangePointer, InterlockedCompareExchangePointer routine [Kernel-Mode Driver Architecture], k102_ffaadb46-ece2-40fb-9e87-1c7ea3af275e.xml, kernel.interlockedcompareexchangepointer, wdm/InterlockedCompareExchangePointer
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Miniport.h
req.target-type: Desktop
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
req.lib: 
req.dll: 
req.irql: Any level
targetos: Windows
req.typenames: 
f1_keywords:
 - InterlockedCompareExchangePointer
 - wdm/InterlockedCompareExchangePointer
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - InterlockedCompareExchangePointer
---

# InterlockedCompareExchangePointer function (wdm.h)


## -description

The <b>InterlockedCompareExchangePointer</b> routine performs an atomic operation that compares the input pointer value pointed to by <i>Destination</i> with the pointer value <i>Comperand</i>.

## -parameters

### -param Destination 

[in, out]
A pointer to a PVOID value. If (*<i>Destination</i>) = <i>Comperand</i>, then the routine sets (*<i>Destination</i>) to <i>Exchange</i>.

### -param Exchange 

[in]
Specifies the PVOID value to set (*<i>Destination</i>) to.

### -param Comperand

[in]
Specifies the PVOID value to compare with (*<i>Destination</i>).

## -returns

<b>InterlockedCompareExchangePointer</b> returns the original value of the pointer at *<i>Destination</i> (that is, the value of this pointer at entry to the routine).

## -remarks

If <i>Comperand</i> is equal to *<i>Destination</i>, then *<i>Destination</i> is set to equal <i>Exchange</i>. Otherwise, *<i>Destination</i> is unchanged.

<b>InterlockedCompareExchangePointer</b> provides a fast, atomic way to synchronize the testing and updating of a pointer variable that is shared by multiple threads. If the input value pointed to by <i>Destination</i> equals the value of <i>Comperand</i>, the value pointed to by <i>Destination</i> is set to the value of <i>Exchange</i>.

<b>InterlockedCompareExchangePointer</b> is designed for speed and, typically, is implemented inline by a compiler. <b>InterlockedCompareExchangePointer</b> is atomic only with respect to other <b>Interlocked<i>Xxx</i></b> calls. It does not use a spin lock and can be safely used on pageable data.

The <b>InterlockedCompareExchangePointer</b> routine is atomic only with respect to other <b>Interlocked<i>Xxx</i></b> calls.

Interlocked operations cannot be used on non-cached memory.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-interlockedcompareexchange">InterlockedCompareExchange</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-interlockedexchange">InterlockedExchange</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-interlockedexchangepointer">InterlockedExchangePointer</a>