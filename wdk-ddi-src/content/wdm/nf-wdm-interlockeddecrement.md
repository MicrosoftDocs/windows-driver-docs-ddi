---
UID: NF:wdm.InterlockedDecrement
title: InterlockedDecrement function (wdm.h)
description: The InterlockedDecrement routine decrements a caller-supplied variable of type LONG as an atomic operation.
old-location: kernel\interlockeddecrement.htm
tech.root: kernel
ms.assetid: 06964a2c-f666-44e8-a747-41791f61c67c
ms.date: 04/30/2018
ms.keywords: InterlockedDecrement, InterlockedDecrement routine [Kernel-Mode Driver Architecture], k102_cc85e517-f056-413e-a095-671867632613.xml, kernel.interlockeddecrement, wdm/InterlockedDecrement
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Miniport.h
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
req.lib: OneCoreUAP.lib on Windows 10
req.dll: 
req.irql: Any level
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- OneCoreUAP.lib
- OneCoreUAP.dll
- API-MS-Win-Core-Interlocked-l1-1-0.dll
- API-MS-Win-Core-Interlocked-l1-2-0.dll
- KernelBase.dll
- MinKernelBase.dll
api_name:
- InterlockedDecrement
product:
- Windows
targetos: Windows
req.typenames: 
---

# InterlockedDecrement function


## -description


The <b>InterlockedDecrement</b> routine decrements a caller-supplied variable of type LONG as an atomic operation. 


## -parameters




### -param Addend [in, out]

A pointer to a variable to be decremented. 


## -returns



<b>InterlockedDecrement</b> returns the decremented value.




## -remarks



<b>InterlockedDecrement</b> should be used instead of <b>ExInterlockedDecrementLong</b> because it is both more efficient and faster. 

<b>InterlockedDecrement</b> is implemented inline by the compiler when appropriate and possible. It does not require a spin lock and can therefore be safely used on pageable data.

<b>InterlockedDecrement</b> is atomic only with respect to other <b>Interlocked<i>Xxx</i></b> calls. 

Interlocked operations cannot be used on non-cached memory. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545335">ExInterlockedAddLargeInteger</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545343">ExInterlockedAddUlong</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-interlockedexchange">InterlockedExchange</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-interlockedincrement">InterlockedIncrement</a>
 

 

